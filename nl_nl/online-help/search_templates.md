# Zoektemplates

Met behulp van zoektemplates kunnen EasyCruit-administrators templates aanmaken die recruiters kunnen gebruiken voor het zoeken in de sollicitantendatabase. Deze functie is handig voor organisaties met een grote hoeveelheid geregistreerde sollicitanten of voor het zoeken naar zeer specifieke vaardigheden. Afhankelijk van de optie die toegevoegd is in de zoektemplate, kunnen de waarden ingevoerd worden in vrijetekstvelden en geselecteerd worden uit vooraf ingevulde lijsten, de resultaten van vragen en geüploade bestanden.

In het gedeelte  Werkervaring  van de zoektemplates bijvoorbeeld, kan de gebruiker één keuze maken in vervolgkeuzelijsten, meerdere keuzes maken in vervolgkeuzelijsten en vrije tekst invoeren.

Voor meer informatie over zoeken, zie  [Zoeken naar kandidaten](../getting-started/searching_for_candidates.htm).

#### Aanmaken van een zoektemplate

1.  Klik in de  Taakbalk  op de optie  Instellingen  en vervolgens op  Talentpoolzoektemplates.
2.  Om een volledig nieuwe zoektemplate te maken, moet de lijst  Selecteer standaardzoekopdracht  ingesteld zijn op  Selecteer.  
    - of -  
    Om de zoektemplate te baseren op een bestaande template, moet deze geselecteerd worden in de lijst  Selecteer standaardzoekopdracht.
3.  Voer een naam in voor de zoektemplate in het veld  Standaardzoekopdracht opslaan als.
4.  Klik op het pijltje naast elk van de titels van de delen om de beschikbare opties binnen dat gedeelte uit te vouwen.
5.  Selecteer de gewenste waarden voor de zoekparameters.  
    Bij elk gedeelte waarin zoekparameters geselecteerd zijn, wordt een rood sterretje geplaatst aan het einde van de regel met de titel.
6.  Klik op  Opslaan  om de nieuwe template op te slaan.

#### Bewerken van een bestaande zoektemplate

1.  Klik in de  Taakbalk  op de optie  Instellingen  en vervolgens op  Talentpoolzoektemplates.
2.  Selecteer de template die bewerkt moet worden in de lijst  Selecteer standaardzoekopdracht.
3.  Klik op het pijltje naast elk van de titels van de delen om de beschikbare opties binnen dat gedeelte uit te vouwen.  
    De zoektemplate verschijnt met hetzelfde gedeelte dat uitgevouwen was toen de laatste keer opgeslagen werd.
4.  Selecteer de gewenste waarden voor de zoekparameters.
5.  Klik op  Update template  om de wijzigingen op te slaan.

#### Verwijderen van een zoektemplate

1.  Klik in de  Taakbalk  op de optie  Instellingen  en vervolgens op  Talentpoolzoektemplates.
2.  Selecteer de template die verwijderd moet worden in de lijst  Selecteer standaardzoekopdracht.
3.  Klik op  Verwijder zoektemplate  en klik vervolgens op  OK  wanneer gevraagd wordt om te bevestigen.

#### Gebruik van links naar zoektemplate

1.  Vouw op de  Startpagina  de optie  Links naar zoektemplate  uit.
2.  Klik op het gewenste zoekitem in de lijst met  Zoektemplates  of  Opgeslagen zoekopdrachten  om de pagina  Talentpool  voor geavanceerd zoeken weer te geven.
3.  Voltooi het zoeken naar behoefte.  
    De optie Links naar zoektemplate is niet standaard beschikbaar en moet ingeschakeld worden in uw systeem.

#### Aandachtspunten voor zoekcriteria en voorbeelden

Bij het configureren van zoektermen voor zoektemplates, zijn er een paar aandachtspunten die de resultaten beïnvloeden. Als de verwachte zoekresultaten niet verschijnen, dan kan dit om een van de volgende redenen zijn:

Zoektermen moeten minimaal drie tekens bevatten en speciale tekens zoals ‘+’ en ‘-’ kunnen niet gezocht worden en tellen dus niet mee voor het minimum van drie tekens. Een programmeervaardigheid zoals ‘C++’ kan bijvoorbeeld niet toegevoegd worden als vrije tekst.

-   Algemene woorden, zoals ‘en’ of ‘naam’, worden ook uitgesloten bij het zoeken.

Er is een aantal operators die toegevoegd kunnen worden aan de zoekcriteria. Deze volgende operators helpen om gerichter te zoeken:

.+ - Een plusteken geeft aan dat het volgende woord aanwezig moet zijn

.- - Een minteken geeft aan dat het volgende woord niet aanwezig mag zijn

() - Met haakjes kunnen woorden gegroepeerd worden in subexpressies

.* - Het sterretje is een jokerteken dat toegevoegd kan worden aan het einde van een zoekwoord.

" - Een woordgroep tussen dubbele aanhalingstekens moet exact overeenkomen om opgenomen te worden in de zoekresultaten.

De volgende voorbeelden laten zien hoe verschillende zoekopdrachten verschillende resultaten retourneren:

**sales dept** - Retourneert resultaten waarbij ten minste één van de twee woorden gevonden is

**+sales +dept** - Retourneert resultaten waarbij beide woorden gevonden zijn

**+sales dept** - Retourneert resultaten waarbij ‘sales’ gevonden is, maar plaatst de resultaten die ook ‘dept’ bevatten hoger

**+sales -dept** - Retourneert resultaten waarbij ‘sales’ wel en ‘dept’ niet gevonden is

**+sales ~dept** - Retourneert resultaten waarbij ‘sales’ gevonden is, maar plaatst de resultaten die ook ‘dept’ bevatten lager

**+sales +(>dept <exec)** - Retourneert resultaten die ‘sales’ en ‘dept’ of ‘sales’ en ‘exec’ bevatten in willekeurige volgorde, maar ‘sales dept" staat hoger dan ‘sales exec’

**sales*** - Retourneert resultaten die woorden bevatten als ‘sales’, ‘salesman’ of ‘salesperson’

**"sales dept"** - Retourneert resultaten die exact de woordgroep ‘sales dept’ bevatten

##### Zie ook:

![](../Resources/Images/icon-document-link.png)  [Zoeken naar kandidaten](searching_for_candidates.htm)
![](../Resources/Images/icon-document-link.png)  [Categorieën](job_categories.htm)
![](../Resources/Images/icon-document-link.png)  [Extra vragen](additional_questions.htm)
![](../Resources/Images/icon-document-link.png)  [Gebruikers: aanmaken, bewerken en verwijderen](users_create_edit_delete.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNTIxNDIwNTRdfQ==
-->