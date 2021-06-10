# SQL and NoSQl

## Hoofdvraag

Welk type database kan ik het beste gebruiken voor mijn project?

## Reden van het onderzoek

In het project wil ik data op een juiste manier opslaan. Hiervoor wil ik een database gebruiken.  
Nu zijn er verschillende soorten databases met als belangrijkste verschil SQL en NoSQL, daarom ga ik onderzoeken.  
Met dit onderzoek hoop ik duidelijk te krijgen welke data structuur ik voor dit project wil gebruiken, maar natuurlijk ook kennis verzamelen om toe te kunnen passen op volgende projecten.

## Deelvragen

### Wat is het verschil tussen SQL en NoSQL

Het verschil in SQL en NoSQL zit hem in de structuur van de database welke bij SQL aanwezig is en bij NoSQL niet.
Maar ondanks NoSQL minder structuur heeft is deze wel sneller.
Dit is zeker te merken bij projecten met veel data. Dit komt doordat bij NoSQL wordt gezocht op index en niet op gegevens.
Dit heeft dan wel weer als nadeel dat je de index moet weten om gegevens te kunnen vinden.
Terwijl je bij SQL ook op andere gegevens kan zoeken.  
Bij het leggen van koppelingen tussen data kun je weer beter SQL hebben aangezien je daar voor verschillende doelen een tabel kan maken die je dan weer kan koppelen aan gegevens.
Dit is via NoSQL niet direct mogelijk en zal dan dus met een hele omweg gedaan moeten worden.

### Zijn er verschillen in de uitbreidingsmogelijkheden

Voor uitbreidingen op de database is NoSQL in het voordeel, omdat deze makkelijker in capaciteit is op te schalen.
In opslag zit het verschil het meeste in structuur.
Bij SQL heb je alles in tabellen en bij NoSQL heb je alles in een JSON bestand (er zijn bij NoSQL ook andere vormen, maar in de basis zit je veelal in de JSON)

### Welke verschillen zijn er voor toekomst wijzigingen

Bij een SQL database zijn de tabbellen vooraf aangemaakt en dus is de structuur van de data vooraf vastgesteld.
Wanneer je een extra stukje dat wil toevoegen zal dit element dus aan de tabel moeten worden toegevoegd.
Hierdoor word deze `entity` aan alle bestaande gegevens toegevoegd. Bij NoSql worden alleen de gegevens opgeslagen die nodig zijn.
Wanneer je dus een entity maar bij 1 ding wil hebben hoef je hem maar ook alleen op die plek op te slaan.
Wanneer je data per "object" veelvoudig kan gaan verschillen en je toch weinig opslag wil hebben maakt NoSql zeer geschikt.

## Conclusie

Er zijn veel mogelijkheden voor het gebruik van SQL en NoSQL.
Het grootste verschil zit hem in de dataopslag.
Welke database je het best kunt gebruiken hangt dus erg af van je applicatie.
Omdat wij meerdere relaties tussen verschillende tabbellen willen maken, zullen wij voor een rationele(SQL) database gaan.
Wanneer we geen data gaan linken aan elkaar en wanneer snelheid een belangrijk element zou zijn in ons project kunnen we beter kiezen voor NoSQL.

## Bronnen

- [the-sql-vs-nosql-difference](https://www.xplenty.com/blog/the-sql-vs-nosql-difference/)
- [sql vs nosql mongodb](https://www.mongodb.com/nosql-explained/nosql-vs-sql)
