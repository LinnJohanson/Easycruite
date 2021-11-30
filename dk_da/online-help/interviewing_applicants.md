# Samtale med ansøgere

Efter at have evalueret en ansøgers ansøgning, kan de personer, der har de nødvendige færdigheder, inviteres til en samtale. Dette kan være et telefoninterview, en personlig samtale eller en gruppesamtale og kunne være det første skridt mod, at denne kandidat bliver valgt til rekrutteringsprojektet.

#### Invitation til samtale til ansøgere

1.  Vælg hurtigtlinket  Rekrutteringsoversigt  for at vise siden  Rekrutteringsoversigt.
2.  Vælg  Titlen  på det rekrutteringsprojekt, du gerne vil planlægge samtaler til for at vise siden  Ansøgningshåndtering.
3.  I afsnittet  Oversigt  vælges  Alle ansøgninger  for at vise listen over ansøgere.
4.  Vælg afkrydsningsfelt for den ønskede ansøger og vælg derefter i listen  Videre behandling  Indkald til samtale  og klik på  Udfør.
5.  Vælg  Type af samtale,  Medvirkende rekruttør(er),  Dato,  Tid  og  Varighed  og klik derefter på  Næste.
6.  Bekræft, at alle oplysningerne er korrekte, før e-mailen sendes til ansøgeren og klik derefter på  Send.  
    Sørg for at muligheden  Handling  er indstillet til  Send e-mail  for at ansøgerne kan modtage e-mailnotifikationer om deres samtale. Overvej også at vælge muligheden for linkbekræftelse for at gøre ansøgeren i stand til at bekræfte mødet.
7.  Du sendes tilbage til siden  Ansøgninger  og ansøgerens status opdateres for at angive, at vedkommende er blevet inviteret til samtale.

#### Overvejelser ved bekræftelseslink

Inkludering af  {confirmlink}-variablen i en e-mail sikrer, at kandidaten kan reagere hurtigt på en invitation til en samtale.

Muligheden  Vil du inkludere et link  ... Garanterer, at bekræftelseslinket implementeres i e-mailen. Om denne mulighed er valgt som standard afhænger af visse af de følgende kriterier:

E-mailen er sendt til en enkelt kandidat

-   Hvis afsnittet  Indhold  i e-mailen indeholder  {confirmlink}, er muligheden ikke valgt.
-   Hvis afsnittet  Indhold  i e-mailen ikke indeholder  {confirmlink}, er muligheden valgt som standard.

E-mailen sendes til flere kandidater, der taler forskellige sprog

-   Hvis afsnittet  Indhold  i e-mailen i hver sprogvariant indeholder  {confirmlink}, er muligheden ikke valgt.
-   Hvis afsnittet  Indhold  i e-mailen i hver sprogvariant ikke indeholder  {confirmlink}, er muligheden valgt som standard.

#### Afsendelse af påmindelser om samtale

Påmindelser om samtale opsættes på den samme side, som du bruger til at sende en invitation til samtale til en kandidat.

1.  Vælg hurtigtlinket  Rekrutteringsoversigt  for at vise siden  Rekrutteringsoversigt.
2.  Vælg  Titlen  på det rekrutteringsprojekt, du gerne vil planlægge samtaler til for at vise siden  Ansøgningshåndtering.
3.  I afsnittet  Oversigt  vælges  Alle ansøgninger  for at vise listen over ansøgere.
4.  Vælg afkrydsningsfelt for den ønskede ansøger og vælg derefter i listen  Videre behandling  Indkald til samtale  og klik på  Udfør.
5.  Vælg  Type af samtale,  Medvirkende rekruttør(er),  Dato,  Tid  og  Varighed  og klik derefter på  Næste.
6.  Gennemgå oplysningerne for samtaleinvitationen herunder  Afsenderadresse,  Emne,  Indhold.  
    Hvis du ikke ønsker at sende en kandidat en invitation til samtale, men blot en påmindelse, indstilles samtaleinvitationen til  ingen e-mail.
7.  Vælg en af de påmindelsesmuligheder
    -   Ingen påmindelse  - der sendes ingen påmindelse
    -   Send e-mailpåmindelse  - der vil blive sendt en påmindelse via e-mail
    -   Send SMS-påmindelse  - der vil blive sendt en SMS med en påmindelse, hvis brugeren, der opretter samtalen, har adgang til SMS. Denne mulighed er ikke synlig for brugere, der ikke har  [adgang til SMS](users_access_controls.htm).
    -   Send SMS- + e-mail-påmindelse  - der sendes både en SMS og en e-mail. Denne mulighed er ikke synlig for brugere, der ikke har adgang til SMS.
8.  Vælg det antal dage inden samtalen, hvor påmindelsen skal sendes.
    
    -   1, 2, 3,5 eller 7 dage
    
    Påmindelser sendes klokken cirka 09:00 CET inden samtalen. Dage er beregnet ud fra hverdage og weekender - hvis en samtale derfor er planlagt til mandag og der sendes en påmindelse 2 dage forinden, sendes påmindelsen om lørdagen klokken 09:00. Der sendes ingen påmindelse, hvis der er færre dage til samtalen, end det antal dage, der er konfigureret for påmindelsen.
9.  Hvis du har valgt at sende en e-mailpåmindelse:
    -   Indtast  Emnet.
    -   Indtast  Indholdet.
    -   Indtast  Signaturen.
10.  Klik på  Send.  
    Der vises en advarsel, hvis du forsøger at sende en SMS-påmindelse til en kandidat, der ikke har indtastet et mobiltelefonnummer.

#### Ansøgere og samtaleprocessen

Når en ansøger er blevet inviteret til en samtale, skal vedkommende svare på mail-invitationen, således at systemet kan opdateres tilsvarende. Den e-mail, som ansøgeren modtager, indeholder de ønskede oplysninger, der automatisk indsættes i e-mail-teksten for at erstatte de variabler, der er inkluderet i e-mailskabelonen.

Når ansøgeren klikker på samtalebekræftelseslinket, føres vedkommende til en anden internetside, hvor vedkommende kan svare, og dermed opdateres statussen i EasyCruit. Den følgende tabel viser, hvad hver bekræftelsesmulighed munder ud i. StatussenAcc.tid  status er angivet i  Rekrutteringskalenderen  og statussen  Rediger mødeinvitation  er angivet på kandidatens side  Ansøgning og CV.

**Bekræftelsesmulighed**
Acc. Status for Tid/Rediger mødeindkaldelsen

**Ja tak, jeg vil gerne deltage**
Accepteret

**Nej tak, jeg ønsker ikke at deltage**
Ikke accepteret

**Kontakt mig for en ny aftale**
Kontakt for nyt tidspkt.

**Annullér min ansøgning**
Ikke relevant. Kandidatens  Status for projektet  opdateres til  Trukket sig.

Afhængigt af ansøgerens svar kan samtalen finde sted og status kan efterfølgende opdateres efter samtalen.

For at få mere at vide om at se samtaler og statussen for invitationer henvises til  [Rekrutteringskalenderen](recruitment_calendar.htm)

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Rekrutteringskalender](recruitment_calendar.htm)
![](../Resources/Images/icon-document-link.png)  [Testintegrationer](test_integrations.htm)
![](../Resources/Images/icon-document-link.png)  [Tilbyde en ansøger job](making_an_offer_to_an_applicant.htm)
![](../Resources/Images/icon-document-link.png)  [Fællesrangering/Panelevaluering](collaborative_rating_panel_review.htm)
![](../Resources/Images/icon-document-link.png)  [Oversigt over siden Ansøgningshåndtering](application_handling_page_overview.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NDYzNDkxMDddfQ==
-->