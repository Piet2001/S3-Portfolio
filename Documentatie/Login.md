# Login Systeem

## Hoofdvraag

Waarom is een login Systeem belangrijk voor je applicatie?

## Reden van het onderzoek

Omdat vele systemen zijn beveiligd met een login systeem wil ik dat ook bij mijn app integreren.
Een belangrijke vraag is dan alleen, waarom is het belangrijk/nodig om je app te beveiligen met zo'n systeem.

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

### Zelf maken of opensource gebruiken

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

### Welke bestaande systemen kan ik gebruiken

Er zijn vele bestaande systemen die je kunt gebruiken voor je project.
Deze kun je vinden in gratis versies tot betaalde.
Veelal kun je met de gratis versies al ver komen.
Bekende tools die ik kan gebruiken zijn: Auth0, keycloak, Okta.
Ieder systeem heeft zijn voor en nadelen.
Het is dus vooral zaak dat je vooraf bekijkt welke zaken belangrijk zijn voor jou app en welke tool jou dit kan bieden.
Een belangrijk voorbeeld van waar je voor kan kiezen is of je wil dat gebruikers met bijv. een facebook of google account kunnen inloggen.

### Wat doet een authenticatie service

Na het inloggen moet je een bepaald ID hebben zodat de app kan weten dat je een ingelogde gebruiker bent.
Hiervoor ontvang je een unieke token.
D.m.v. deze token kun je op verschillende pagina's komen.
Je kunt deze token dus ziek als een soort sleutel die bijna overal op past.
De app communiceert continu met de service om alles te blijven controleren.
Je weet nu dus zeker dat alleen de mensen met rechten er bij kunnen.
Je hoeft zelf dus niet veel te doen voor je beveiliging.
Alles wordt door de service verzorgd.

## Conclusie

Het hebben van een login systeem op je applicatie is voor de veiligheid een belangrijke stap.
Door dit systeem voorkom je dat mensen op pagina's komen waar je eigenlijk niet van wil dat ze er komen.
Ook kun je op deze manier zorgen dat alleen mensen waarvan je wil dat ze je app gebruiken deze kunnen gebruiken.
Het hebben van een inlog systeem is dus zeker aan te raden en daarom zal ik het ook zeker in mijn app verwerken.
Allen geregistreerde mensen kunnen de game spelen.

## Bronnen

- [Inloggen Wikipedia](https://nl.wikipedia.org/wiki/Inloggen)
- [Systemen](https://www.saasworthy.com/product-alternative/5998/keycloak)
- [authorization_services](https://www.keycloak.org/docs/latest/authorization_services/index.html)
