# CI/CD

## Wat is CI/CD

CI/CD is het continu testen en updaten van je applicatie.
Hiervoor zijn verschillende systemen.
De bekendste hiervoor zijn de gitlab-runners en github-workflows.
Je kunt met deze systemen de testen van je app automatisch laten uitvoeren.

## Mijn ontwikkeling

Voor dit semester had ik nog nooit met iets van CI/CD gewerkt.
Dus eerst ben ik op onderzoek uitgegaan wat er allemaal bij kwam kijken.
Omdat ik eerst op de gitlab van school werkte ben ik aan de gang gegaan met het opzetten van een runner.
Deze draait nu op mijn PC.
Om dit te testen ben ik begonnen met een proef project waar de runner alleen wat zinnen deed printen.

```yml
build-job:
  stage: build
  script:
    - echo "Hello, $GITLAB_USER_LOGIN!"

test-job1:
  stage: test
  script:
    - echo "This job tests something"

test-job2:
  stage: test
  script:
    - echo "This job tests something, but takes more time than test-job1."
    - echo "After the echo commands complete, it runs the sleep command for 20 seconds"
    - echo "which simulates a test that runs 20 seconds longer than test-job1"
    - sleep 20

deploy-prod:
  stage: deploy
  script:
    - echo "This job deploys something from the $CI_COMMIT_BRANCH branch."
```

Uiteindelijk heb ik de testjobs aangepast zodat ze iets gingen doen met de testen van mijn project.
Bij de frond-end was het het runnen van de node tests van mijn react project:

```yml
npm-test:
  stage: test
  script:
    - npm install
    - npm test
```

Voor de npm zie je dat ik eerst alle dependencies van het project op haal en installeer.
De runner weet welke het zijn door de ``package.json`` file die in het project zit.

Maar ook de back-end moest worden getest.
Aangezien deze werkt met spring boot en maven moesten dus de maven tests worden gebruikt:

```yml
test_job:
  stage: test
  script:
    - pwd
    - mvn clean
    - mvn compile
    - mvn test
```

Op bovenstaande manieren werd alle code getest.
Hiervoor waren wel testen aanwezig in de programma's die ik aan het maken ben.

Uiteindelijk ben ik overgestapt van de school gitlab naar github om mijn projecten verder te bouwen.
Dit leverde ook een verandering in de CI/CD op, aangezien github weer net iets anders werkt.
Mijn github workflow

```yml
name: Build
on:
  push:
    branches:
      - dev
  pull_request:
    types: [opened, synchronize, reopened]
jobs:
  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: Set up JDK 11
        uses: actions/setup-java@v1
        with:
          java-version: 11
      - name: Cache SonarCloud packages
        uses: actions/cache@v1
        with:
          path: ~/.sonar/cache
          key: ${{ runner.os }}-sonar
          restore-keys: ${{ runner.os }}-sonar
      - name: Cache Maven packages
        uses: actions/cache@v1
        with:
          path: ~/.m2
          key: ${{ runner.os }}-m2-${{ hashFiles('**/pom.xml') }}
          restore-keys: ${{ runner.os }}-m2
      - name: Build and analyze
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # Needed to get PR information, if any
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
          DATABASE_HOST: ${{ secrets.DATABASE_HOST }}
          DATABASE_NAME: ${{ secrets.DATABASE_NAME }}
          DATABASE_USERNAME: ${{ secrets.DATABASE_USERNAME }}
          DATABASE_PASSWORD: ${{ secrets.DATABASE_PASSWORD }}
        run: mvn -B verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar
```

Ook hier wordt de code opnieuw gestest.
De verandering is dat voor kwaliteit er nu ook sonarqube is toegevoegd.
Hierdoor krijg ik extra info over de kwaliteit van de code.

Uiteindelijk moest de backend ook als image worden gepubliceerd naar dockerHub.
Om te beginnen moest ik dus een dockerfile maken zodat ik een docker image kon maken van het project.

```dockerfile
FROM openjdk:11
MAINTAINER firestationquiz
COPY target/game-data-service-0.0.1.jar data-service-0.0.1.jar
ENTRYPOINT ["java","-jar","/data-service-0.0.1.jar"]
```

Deze zou gerund moeten worden op de master branch van mijn project om deze naar dockerHub te krijgen.
Om dit te doen heb ik een nieuwe flow gemaakt voor de master branch met als belangrijkste taken het builden en de gegevens opslaan als artifact:

```yml
 build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Set up JDK 11
        uses: actions/setup-java@v2
        with:
          java-version: '11'
          distribution: 'adopt'


      - name: Build with Maven
        run: |
          mvn -B package --file pom.xml
          mkdir staging && cp target/*.jar staging
      - name: Cache Maven packages
        uses: actions/cache@v1
        with:
          path: ~/.m2
          key: ${{ runner.os }}-m2-${{ hashFiles('**/pom.xml') }}
          restore-keys: ${{ runner.os }}-m2

      - name: Persist workflow data as artifact
        uses: actions/upload-artifact@v1
        with:
          name: github-action-artifact
          path: staging
```

En het publiceren van de image naar docker:

```yml
docker:
    name: Docker
    runs-on: ubuntu-latest
    needs:
      - analyse
      - build
    steps:
      - uses: actions/checkout@v1

      - name: Download workflow data
        uses: actions/download-artifact@v1
        with:
          name: github-action-artifact
          path: target/

      - name: Build and Push Docker Image
        uses: mr-smithers-excellent/docker-build-push@v5
        with:
           image: piet2001/game-data-service
           registry: docker.io
           username: ${{ secrets.DOCKER_USERNAME }}
           password: ${{ secrets.DOCKER_PASSWORD }}
```

## Bronnen

- [gitlab runner](https://docs.gitlab.com/runner/)
- [dockerizing-spring-boot-application](https://www.baeldung.com/dockerizing-spring-boot-application)
