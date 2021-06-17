# Web Application

## Wat is een webapplicatie

Een webapplicatie een een programma wat je op een website draait.
Echter kun je dit groot pakken.
Er zijn vele vormen als webapplicaties.
Vaak kun je een basis website die je tegen komt al zien als webapp aangezien je veel interactie hebt met de site.
De meeste webapplicaties communiceren met services via een `api`.
Dit is een pagina met data, die beschikbaar is voor andere programma's.

Voorbeeld van een `api`:

```json
{
    "imageUrl": "https://cdn.discordapp.com/attachments/832601082500612137/834368808553545728/Post_Geldrop_19-10-2019.jpg",
    "answer": "Geldrop",
    "option1": "Geldrop",
    "option2": "Eindhoven-Woensel",
    "option3": "Helmond",
    "option4": "Deurne"
}
```

## Mijn ontwikkeling

Voor het leerdoel webapplicatie was het de opdracht om een fullstack webapp te maken.
De belangrijkste eissen hiervoor waren dat de frond-end bestond uit een `Javascript-based framework` en via `api's` kan communiceren met de backend.
Voor de backend waren niet echt eissen. Wel werd `spring boot` aangeraden, omdat deze vele functies bevat om de communicatie mogelijk te maken.
In het begin zat ik er aan de denken om mijn backend in `.NET` te maken, maar omdat ik eigenlijk ook wel iets nieuws er bij wilde leren toch besloten om met `spring boot` aan de gang te gaan.

Om te beginnen ben ik begonnen met het kijken nar de verschillende mogelijkheden voor de frond-end.
Hierbij had ik al snel de keuze gemaakt om react te gaan gebruiken omdat dat qua moeilijkheidsgraad vaak als middelmaat werd gezien.
Eest ben ik begonnen met het maken van een `boter kaas en eieren` spel.
Deze is te vinden in [deze git repo](https://github.com/Piet2001/POC-React-Tic-Tac-Toe).

Vervolgens heb ik om ook nog te leren over de functionele componenten een task-manager app gemaakt in react.
Deze valt te vinden in [deze git repo](https://github.com/Piet2001/react-task-manager).

Door deze projectjes en het groepsproject heb ik voldoende kennis verzameld om zelf een react pagina te kunnen gaan maken voor mijn eigen project.
Dus ben ik begonnen om een pagina te maken voor mijn eigen project.
Deze heb ik opgebouwd uit een game en statustieken component.

Nadat de frond-end stond als een basis ben ik aan de slag gegaan voor de backend.
Ook hier ben ik eerst begonnen met een proef project om te leren.
Ik ben toen direct de microservice wereld in gedoken om te weten hoe ik alles moest maken.
Het proefproject is de vinden in [deze git repo](https://github.com/Piet2001/POC-Movie-Catalog).

Na alle onderzoeken had ik voldoende informatie om mijn eigen project te maken.
Deze bestaat uit 3 onderdelen, waarvan de keycloak service een standaard service is.
Later zullen ook voor de opslag van statistieken nog extra services kunnen worden toegevoegd.

- [Een react view](https://github.com/Piet2001/FirestationQuiz-View)
- [Spring boot backend - Microservice](https://github.com/Piet2001/game-data-service)
- [Keycloak authenticatie service](https://www.keycloak.org/)

## Bronnen

- [React tutorial Tic-tac-toe](https://reactjs.org/tutorial/tutorial.html)
- [React tutorial taks-manager](https://www.youtube.com/watch?v=w7ejDZ8SWv8)
- [Spring boot mircroservices tutorial movie-Catalog](https://www.youtube.com/playlist?list=PLqq-6Pq4lTTZSKAFG6aCDVDP86Qx4lNas)
