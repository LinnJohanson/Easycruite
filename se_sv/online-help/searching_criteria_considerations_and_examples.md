# Sökkriterier – Överväganden och exempel

När du anger sökorden för sökmallar finns det ett antal faktorer som påverkar resultaten, som du behöver ta hänsyn till. Om det förväntade sökresultatet inte visas, kan det bero på följande problem:

-   Sökord måste bestå av minst tre tecken och specialtecken som ”+” och ”-” är inte sökbara tecken, så de ingår inte i minimiantalet på tre tecken. Till exempel kan inte kunskaper i programmeringsspråk som ”C++” ingå i en fritextsökning.
-   Vanliga ord som ”och” eller ”namn” utesluts också från sökningar.

Det finns ett antal operatorer som kan ingå i sökkriterierna. Dessa hjälper till att begränsa sökningar och består av följande:

+Ett plustecken anger att följande ord måste finnas

-Ett minustecken anger att följande ord inte får finnas

( )Parenteser gör att ord kan grupperas i deluttryck

*Asterisken är ett jokertecken som kan läggas till i slutet eller i ett sökord.

"En fras mellan dubbla citattecken måste matchas identiskt för att den ska ingå i ett sökresultat.

För att illustrera ovanstående informationen visar följande exempel hur olika söktermer ger olika resultat:

försäljning avd

Visar sökresultat där minst ett av de två orden hittades

+försäljning +avdVisar sökresultat där båda orden hittades+försäljning avdVisar sökresultat där ”försäljning” hittades, men rankar resultat högre om de också innehåller ”avd”+försäljning -avd

Visar sökresultat där ”försäljning” hittades men inte ”avd”

+försäljning ~avd

Visar sökresultat där ”försäljning” hittades, men rankar resultat lägre om de också innehåller ”avd”

+försäljning +(>avd <chef)Visar sökresultat som innehåller ”försäljning” och ”avd” eller ”försäljning” och ”chef”, i vilken som helst ordning, men "försäljningsavdelning" skulle rankas högre än "försäljningschef"försäljning*

Visar sökresultat som innehåller ord som ”försäljning”, ”försäljningschef” eller ”försäljningspersonal”

”försäljning avd”Visar sökresultat som innehåller den exakta frasen ”försäljning avd”

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbODE5MDgwNTQ2LDEyOTkwMDg4NjRdfQ==
-->