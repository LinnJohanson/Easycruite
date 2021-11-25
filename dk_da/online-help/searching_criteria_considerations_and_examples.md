# Søgekriterier, overvejelser og eksempler

Når der opsættes søgetermer for hver søgeskabelon, er der flere overvejelser, der påvirker resultatet. Hvis de forventede søgeresultater ikke vises, kan det skyldes en af følgende årsager:

-   Søgetermerne skal bestå af minimum tre tegn i længden og specialtegn som eksempelvis ”+” og ”-” er ikke søgbare tegn. De e derfor ikke inkluderet i det absolutte minimum på tre tegn. Eksempelvis kan en programmeringsfærdighed som ”C++” ikke inkluderes i en fritekstsøgning.
-   Almindelige ord så som ”og” eller ”navn” er også udelukket ag søgningen.

Enkelte operatører kan inkluderes i søgningen. Dette hjælper med at muliggøre mere fokuserede søgninger og består af følgende:

.+ : Et plustegn indikerer, at det følgende ord skal være til stede

.- : Et minustegn indikerer, at det følgende ord ikke skal være til stede

( ) : Parenteser gør det muligt at gruppere ord i underudtryk

* : Asterisken er en joker, der kan tilføjes til slut eller til et søgeord.

" : Et udtryk med dobbelte citationstegn skal matches identisk for at det kan inkluderes i nogen søgeresultater.

For at illustrere ovennævnte oplysninger viser det følgende eksempel, hvordan forskellige søgetermer giver forskellige visningsresultater:

sales dept - Viser resultater, hvor mindst et af de to ord figurerer

+sales +dept - Viser resultater, hvor begge ord findes

+sales dept - Viser resultater, hvor ”sales” findes, men klassificerer resultaterne højere, hvis de også indeholder ordet ”dept”

+sales -dept - Viser resultater, hvor ”sales” findes og ”dept” ikke findes

+sales ~dept - Viser resultater, hvor ”sales” findes, men klassificerer resultaterne lavere, hvis de også indeholder ordet ”dept”

+sales +(>dept <exec) - Viser resultater, der indeholder ordene ”sales” og ”dept” eller ”sales” og ”exec” i vilkårlig rækkefølge, dog klassificeres ”sales dept” højere end ”sales exec”

sales* - Viser resultater, der indeholder ord som ”sales”, ”salesman” eller ”salesperson”

"sales dept" - Viser resultater, der indeholder den præcise term ”sales dept”.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MTg1Njk2NzBdfQ==
-->