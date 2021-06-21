# Login Systeem

## Hoofdvraag

Hoe kan ik een login systeem op mijn app zetten?

## Reden van het onderzoek

Graag wil ik dat mijn app alleen gebruikt kan worden door specifieke mensen.
Daarom wil ik graag mijn app beveiligen, zodat niet iedereen er in kan.

## Hoe ga ik het onderzoek doen

Bij het DOT-Framework zijn er verschillende manieren voor het doen van research.
Je kunt door deze methode goed research doen op verschillende vlakken van je vraag.
Ook kom je hierdoor vaak op een betere oplossing voor je probleem.  
Binnen het DOT-Framework heb je de volgende strategieën:

| Strategie                                                                                                      | Beschrijving                                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Library ![library](https://ictresearchmethods.nl/images/thumb/8/87/Logo-library.png/75px-Logo-library.png)     | Onderzoek doen op basis van bestaande bronnen en onderzoeken.                                                                                                                                   |
| Field ![Field](https://ictresearchmethods.nl/images/thumb/d/d4/Logo-field.png/75px-Logo-field.png)             | Onderzoek de meningen van mogelijke gebruikers. Je gaat kijken hoe je je kennis kunt verbreden. Vaak gebruik je in dit onderzoek een enquête om ook de meningen van andere te kunnen gebruiken. |
| LAB ![lab](https://ictresearchmethods.nl/images/thumb/a/ac/Logo-lab.png/75px-Logo-lab.png)                     | Hierbij ga je zaken vergelijken en testen met bijv. unit tests.                                                                                                                                 |
| Showroom ![showroom](https://ictresearchmethods.nl/images/thumb/2/22/Logo-showroom.png/75px-Logo-showroom.png) | Hierbij ga je meerdere producten met elkaar vergelijken. Je bekijkt dan welke het beste bij jou applicatie werkt.                                                                               |
| Workshop ![workshop](https://ictresearchmethods.nl/images/thumb/e/ea/Logo-workshop.png/75px-Logo-workshop.png) | Hierbij maak je een prototype/proof of concept om te kijken hoe het werkt.                                                                                                                      |

Per vraag zal ik gaan kijken welke strategie het beste is.
Er wordt per vraag aangeven welke strategie daar is aangegeven.

## Deelvragen

### Wat is een login systeem

Een login systeem is een beveiliging op je applicatie.
Door middel van dit systeem zorg je dat niet iedereen gebruik kan maken van functionaliteiten van je applicatie.
Gebruikers die het willen gebruiken hebben een account nodig.
Deze kunnen ze zelf aanmaken, of de beheerder van de app moet ze aanmaken voor de personen.
Hier kan de developer zelf voor kiezen.
Wanneer een gebruiker een account heeft kan deze door middel van een gebruikersnaam en wachtwoord inloggen in het systeem.
De ingevulde gegevens worden door het systeem gecontroleerd en wanneer deze correct zijn kan de gebruiker gebruik maken van de app.
Wanneer de gegevens niet correct zijn, zal een nieuwe login poging gedaan moeten worden.
Door deze controle weet je zeker dat niet iedereen gebruik zal maken van je applicatie aangezien mensen zonder account er dan niet bij kunnen.

#### Gebruikte strategie

![library](https://ictresearchmethods.nl/images/thumb/8/87/Logo-library.png/75px-Logo-library.png)  

- Literature study

### Waarom zou ik een opensource systeem gebruiken

Een inlog systeem kun je zelf maken, maar inmiddels zijn er ook verschillende bedrijven die een "plug and play" versie hebben die je kunt gebruiken.
Je moet dus wanneer je een login systeem gaat integreren goed nadenken over wat je wil.
Wanneer je zelf een systeem maakt weet je exact hoe het werkt, maar is de beveiliging dan ook goed geregeld?
Bij een opensource management systeem weet je zeker dat er veel mensen naar kijken.
Hier zijn bedrijven die het voor je maken.
Ook wordt dit gecontroleerd door vele mensen.
Een mogelijk lek zal dus spoedig hersteld worden.
Echter doordat het opensource is krijgen enkele wel de gedachten dat het daardoor minder veilig zou zijn.
De systemen die je kunt krijgen zijn allemaal veilig.
Het enige nadeel is dat je voor de werking even goed de tijd moet nemen, zodat je weet hoe het werkt.
Dus de keuze is belangrijk, waar kies je voor.
Zelf iets maken zodat je alles weet.
Of een systeem wat door veel mensen word onderhouden en je dus zeker weet dat het veilig is.

#### Gebruikte strategie

![library](https://ictresearchmethods.nl/images/thumb/8/87/Logo-library.png/75px-Logo-library.png)

- Community research

### Welke bestaande systemen kan ik gebruiken

Er zijn vele bestaande systemen die je kunt gebruiken voor je project.
Deze kun je vinden in gratis versies tot betaalde.
Veelal kun je met de gratis versies al ver komen.
Bekende tools die ik kan gebruiken zijn: Auth0, keycloak, Okta.
Ieder systeem heeft zijn voor en nadelen.
Het is dus vooral zaak dat je vooraf bekijkt welke zaken belangrijk zijn voor jou app en welke tool jou dit kan bieden.
Een belangrijk voorbeeld van waar je voor kan kiezen is of je wil dat gebruikers met bijv. een facebook of google account kunnen inloggen.

#### Gebruikte strategie

![showroom](https://ictresearchmethods.nl/images/thumb/2/22/Logo-showroom.png/75px-Logo-showroom.png)

- Benchmark-test

### Wat doet een authenticatie service

Na het inloggen moet je een bepaald ID hebben zodat de app kan weten dat je een ingelogde gebruiker bent.
Hiervoor ontvang je een unieke token.
D.m.v. deze token kun je op verschillende pagina's komen.
Je kunt deze token dus ziek als een soort sleutel die bijna overal op past.
De app communiceert continu met de service om alles te blijven controleren.
Je weet nu dus zeker dat alleen de mensen met rechten er bij kunnen.
Je hoeft zelf dus niet veel te doen voor je beveiliging.
Alles wordt door de service verzorgd.

#### Gebruikte strategie

![library](https://ictresearchmethods.nl/images/thumb/8/87/Logo-library.png/75px-Logo-library.png)

- Literature study
- Community research

## Conclusie

Met keycloak is het makkelijk om een inlog systeem op je website te krijgen.
Dit kun je in een paar stappen doen:
| Stap                   | Actie                                                             |
| ---------------------- | ----------------------------------------------------------------- |
| Download Keycloak      | In het begin zorg je dat je keycloak hebt geïnstalleerd.          |
| Start Keycloak         | Start de keycloak applicatie                                      |
| Login to admin         | Login op je admin console                                         |
| Maak realm             | Maak een realm voor je app                                        |
| Voer app in            | Voer alle gegevens van je app en en configureer alle instellingen |
| Voeg een gebruiker toe | Maak een gebruiker aan voor je app die kan inloggen               |

#### Gebruikte strategie

![workshop](https://ictresearchmethods.nl/images/thumb/e/ea/Logo-workshop.png/75px-Logo-workshop.png)

- Prototyping

## Bronnen

- [Inloggen Wikipedia](https://nl.wikipedia.org/wiki/Inloggen)
- [Systemen](https://www.saasworthy.com/product-alternative/5998/keycloak)
- [authorization services](https://www.keycloak.org/docs/latest/authorization_services/index.html)
- [Keycloak React](https://www.powerupcloud.com/keycloak-with-java-and-reactjs/)
