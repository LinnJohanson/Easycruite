# Aandachtspunten voor zoekcriteria en voorbeelden

Bij het configureren van zoektermen voor zoektemplates, zijn er een paar aandachtspunten die de resultaten beïnvloeden. Als de verwachte zoekresultaten niet verschijnen, dan kan dit om een van de volgende redenen zijn:

-   Zoektermen moeten minimaal drie tekens bevatten en speciale tekens zoals ‘+’ en ‘-’ kunnen niet gezocht worden en tellen dus niet mee voor het minimum van drie tekens. Een programmeervaardigheid zoals ‘C++’ kan bijvoorbeeld niet toegevoegd worden als vrije tekst.
-   Algemene woorden, zoals ‘en’ of ‘naam’, worden ook uitgesloten bij het zoeken.

Er is een aantal operators die toegevoegd kunnen worden aan de zoekcriteria. Deze volgende operators helpen om gerichter te zoeken:

+

Een plusteken geeft aan dat het volgende woord aanwezig moet zijn

-

Een minteken geeft aan dat het volgende woord niet aanwezig mag zijn

( )

Met haakjes kunnen woorden gegroepeerd worden in subexpressies

*

Het sterretje is een jokerteken dat toegevoegd kan worden aan het einde van een zoekwoord.

"

Een woordgroep tussen dubbele aanhalingstekens moet exact overeenkomen om opgenomen te worden in de zoekresultaten.

De volgende voorbeelden laten zien hoe verschillende zoekopdrachten verschillende resultaten retourneren:

sales dept

Retourneert resultaten waarbij ten minste één van de twee woorden gevonden is

+sales +dept

Retourneert resultaten waarbij beide woorden gevonden zijn

+sales dept

Retourneert resultaten waarbij ‘sales’ gevonden is, maar plaatst de resultaten die ook ‘dept’ bevatten hoger

+sales -dept

Retourneert resultaten waarbij ‘sales’ wel en ‘dept’ niet gevonden is

+sales ~dept

Retourneert resultaten waarbij ‘sales’ gevonden is, maar plaatst de resultaten die ook ‘dept’ bevatten lager

+sales +(>dept <exec)

Retourneert resultaten die ‘sales’ en ‘dept’ of ‘sales’ en ‘exec’ bevatten in willekeurige volgorde, maar ‘sales dept" staat hoger dan ‘sales exec’

sales*

Retourneert resultaten die woorden bevatten als ‘sales’, ‘salesman’ of ‘salesperson’

"sales dept"

Retourneert resultaten die exact de woordgroep ‘sales dept’ bevatten


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzU3MTY0MDddfQ==
-->