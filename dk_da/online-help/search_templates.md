# Søgeskabeloner

Søgeskabeloner gør det muligt for EasyCruit-administratorer at skabe skabeloner, som rekruttører kan bruge til at søge i ansøgerdatabasen. Denne funktion er nyttig for virksomheder, derhar et stort antal registrerede ansøgere, eller når der søges på meget specifikke kompetencer. Afhængigt af muligheden, der er inkluderet i søgeskabelonen, kan værdierne indtastes i fritekstfelter, udvalgt fra udfyldte lister, resultater af spørgsmål og oploadede filer.

Eksempelvis giver afsnittet  Arbejdserfaring  i søgeskabelonerne brugeren mulighed for at vælge i dropdown-lister, dropdown-lister, med flere svar og fritekstfelter.

For oplysninger om at køre søgninger henviser vi til  [Søgning efter kandidater](../getting-started/searching_for_candidates.htm).

![Lukket](../Skins/Default/Stylesheets/Images/transparent.gif)Oprettelse af en søgeskabelon

1.  I  Værktøjslinjen  klikkes på  Indstillinger  og derefter  Søgeskabeloner.
2.  For at oprette en helt ny søgeskabelon skal man sikre, at listen  Vælg søgeskabelon  er indstillet til  Vælg  
    - eller -  
    for at basere søgeskabelonen på en eksisterende skabelon, vælges listen  Vælg søgeskabelon
3.  Indtast navnet på søgeskabelonen i feltet  Gem søgning som.
4.  Klik på pilen ved siden af hver overskrift for at åbne de muligheder, der er tilgængelige i afsnittet.
5.  Vælg de nødvendige værdier til søgeparametrene  
    For hver afsnit, der har søgeparametre valgt, er en rød asterisk placeret i overskriften.
6.  Klik på  Gem skabelon  for at gemme den nye skabelon.

![Lukket](../Skins/Default/Stylesheets/Images/transparent.gif)Redigering af en eksisterende søgeskabelon

1.  I  Værktøjslinjen  klikkes på  Indstillinger  og derefter  Søgeskabeloner.
2.  Vælg den skabelon, der skal redigeres i listen  Vælg søgeskabelon.
3.  Klik på pilen ved siden af hver overskrift for at åbne de muligheder, der er tilgængelige i afsnittet.  
    Søgeskabelonen vises, og den viser det samme afsnit, som blev åbnet, sidste gang den blev gemt.
4.  Vælg de nødvendige værdier til søgeparametrene
5.  Klik på  Opdatér skabeloner  for at gemme ændringerne.

![Lukket](../Skins/Default/Stylesheets/Images/transparent.gif)Sletning af en søgeskabelon

1.  I  Værktøjslinjen  klikkes på  Indstillinger  og derefter  Søgeskabeloner.
2.  Vælg den skabelon, der skal slettes i listen  Vælg søgeskabelon.
3.  Klik på  Slet skabelon  og klik derefter på  OK, når du bliver bedt om at bekræfte sletningen.

![Lukket](../Skins/Default/Stylesheets/Images/transparent.gif)Brug af hurtiglinks til søgning

1.  Fra siden  Start  klikkes på plusikonet for at åbne feltet  Genvej til søg.
2.  Klik på det nødvendige søgepunkt i listen med  Søgeskabeloner  eller  Gemte søgninger  for at vise den avancerede  Kandidatsøgnings-side.
3.  Gennemfør søgning som påkrævet.  
    Muligheden for at søge via hurtiglinks er ikke almindeligvis tilgængelig og skal aktiveres i systemet.

![Lukket](../Skins/Default/Stylesheets/Images/transparent.gif)Søgekriterier, overvejelser og eksempler

Når der opsættes søgetermer for hver søgeskabelon, er der flere overvejelser, der påvirker resultatet. Hvis de forventede søgeresultater ikke vises, kan det skyldes en af følgende årsager:

Søgetermerne skal bestå af minimum tre tegn i længden og specialtegn som eksempelvis ”+” og ”-” er ikke søgbare tegn. De e derfor ikke inkluderet i det absolutte minimum på tre tegn. Eksempelvis kan en programmeringsfærdighed som ”C++” ikke inkluderes i en fritekstsøgning.

-   Almindelige ord så som ”og” eller ”navn” er også udelukket ag søgningen.

Enkelte operatører kan inkluderes i søgningen. Dette hjælper med at muliggøre mere fokuserede søgninger og består af følgende:

+

Et plustegn indikerer, at det følgende ord skal være til stede

-

Et minustegn indikerer, at det følgende ord ikke skal være til stede

()

Parenteser gør det muligt at gruppere ord i underudtryk

*

Asterisken er en joker, der kan tilføjes til slut eller til et søgeord.

"

Et udtryk med dobbelte citationstegn skal matches identisk for at det kan inkluderes i nogen søgeresultater.

For at illustrere ovennævnte oplysninger viser det følgende eksempel, hvordan forskellige søgetermer giver forskellige visningsresultater:

sales dept

Viser resultater, hvor mindst et af de to ord figurerer

+sales +dept

Viser resultater, hvor begge ord findes

+sales dept

Viser resultater, hvor ”sales” findes, men klassificerer resultaterne højere, hvis de også indeholder ordet ”dept”

+sales -dept

Viser resultater, hvor ”sales” findes og ”dept” ikke findes

+sales ~dept

Viser resultater, hvor ”sales” findes, men klassificerer resultaterne lavere, hvis de også indeholder ordet ”dept”

+sales +(>dept <exec)

Viser resultater, der indeholder ordene ”sales” og ”dept” eller ”sales” og ”exec” i vilkårlig rækkefølge, dog klassificeres ”sales dept” højere end ”sales exec”

sales*

Viser resultater, der indeholder ord som ”sales”, ”salesman” eller ”salesperson”

"sales dept"

Viser resultater, der indeholder den præcise term ”sales dept”.

Se også:

![](../Resources/Images/icon-document-link.png)  [Søgning efter kandidater](searching_for_candidates.htm)

![](../Resources/Images/icon-document-link.png)  [Jobkategorier](job_categories.htm)

![](../Resources/Images/icon-document-link.png)  [Yderligere spørgsmål](additional_questions.htm)

![](../Resources/Images/icon-document-link.png)  [Brugere: Opret, Redigér, Slet](users_create_edit_delete.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI0NTE3Njk5M119
-->