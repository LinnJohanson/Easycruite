# Sökmallar

Sökmallar gör det möjligt för administratörer i EasyCruit att skapa mallar som rekryterare kan använda för att söka i klientdatabasen. Den här funktionaliteten är användbar för företag som har många registrerade kandidater eller om du vill söka efter en mycket specifik kompetens. Beroende på vilket alternativ som ingår i sökmallen kan värdena anges i fria textfält, väljas från ifyllda listor, resultatet av frågor eller uppladdade filer.

Till exempel förser sektionen  Erfarenhet  i sökmallen användaren med möjlighet att söka i en listruta, flervals listrutor och fritextfält.

För information om hur du gör sökningar, se  [Söka efter kandidater](../getting-started/searching_for_candidates.htm).

#### Skapa en sökmall

1.  I  Verktygsfältet  klickar du på  Inställningar  och sedan  Sökmallar.
2.  För att skapa en helt ny sökmall, se till att listan  Välj sökmall  är inställd på  Välj  
    - eller -  
    för att basera sökmallen på en befintlig sökmall, väljer du den från listan  Välj sökmall.
3.  Ange ett namn för sökmallen i fältet  Spara sökning som.
4.  Klicka på pilen bredvid var och en av rubrikerna för att se vilka alternativ som är tillgängliga i den sektionen.
5.  Markera de värden som du vill ska ingå i sökparametrarna.  
    Varje sektion som innehåller en markerad sökparameter, får en röd asterisk i rubrikraden.
6.  Klicka på  Spara mall  för att spara den nya mallen.

#### Redigera en befintlig sökmall

1.  I  Verktygsfältet  klickar du på  Inställningar  och sedan  Sökmallar.
2.  Välj den mall som ska redigeras från listan  Välj sökmall.
3.  Klicka på pilen bredvid var och en av rubrikerna för att se vilka alternativ som är tillgängliga i den sektionen.  
    Sökmallen visas och samma sektion som hade öppnats sist den sparades visas.
4.  Markera de värden som du vill ska ingå i sökparametrarna.
5.  Klicka på  Uppdatera mall  för att spara ändringarna.

#### Radera en sökmall

1.  I  Verktygsfältet  klickar du på  Inställningar  och sedan  Sökmallar.
2.  Välj den mall som ska raderas från listan  Välj sökmall.
3.  Klicka på  Radera mall  och klicka sedan på  OK  när du uppmanas att bekräfta din åtgärd.

#### Använda snabblänkar för att söka

1.  På  Startsidan  klickar du på + -ikonen för att öppna  Snabblänkarna till Sökrutan.
2.  Klicka på önskat sökobjekt i listan med  Sökmallar  eller  Sparade sökningar  för att visa sidan avancerad  Sök.
3.  Fyll i sökalternativen efter behov.  
    Snabblänkar till sökmallar är en tilläggsfunktion som måste aktiveras i ditt system.

#### Sökkriterier – Överväganden och exempel

När du anger sökorden för sökmallar finns det ett antal faktorer som påverkar resultaten, som du behöver ta hänsyn till. Om det förväntade sökresultatet inte visas, kan det bero på följande problem:

Sökord måste bestå av minst tre tecken och specialtecken som ”+” och ”-” är inte sökbara tecken, så de ingår inte i minimiantalet på tre tecken. Till exempel kan inte kunskaper i programmeringsspråk som ”C++” ingå i en fritextsökning.

-   Vanliga ord som ”och” eller ”namn” utesluts också från sökningar.

Det finns ett antal operatorer som kan ingå i sökkriterierna. Dessa hjälper till att begränsa sökningar och består av följande:

+

Ett plustecken anger att följande ord måste finnas

-

Ett minustecken anger att följande ord inte får finnas

()

Parenteser gör att ord kan grupperas i deluttryck

*

Asterisken är ett jokertecken som kan läggas till i slutet eller i ett sökord.

"

En fras mellan dubbla citattecken måste matchas identiskt för att den ska ingå i ett sökresultat.

För att illustrera ovanstående informationen visar följande exempel hur olika söktermer ger olika resultat:

försäljning avd

Visar sökresultat där minst ett av de två orden hittades

+försäljning +avd

Visar sökresultat där båda orden hittades

+försäljning avd

Visar sökresultat där ”försäljning” hittades, men rankar resultat högre om de också innehåller ”avd”

+försäljning -avd

Visar sökresultat där ”försäljning” hittades men inte ”avd”

+försäljning ~avd

Visar sökresultat där ”försäljning” hittades, men rankar resultat lägre om de också innehåller ”avd”

+försäljning +(>avd <chef)

Visar sökresultat som innehåller ”försäljning” och ”avd” eller ”försäljning” och ”chef”, i vilken som helst ordning, men "försäljningsavdelning" skulle rankas högre än "försäljningschef"

försäljning*

Visar sökresultat som innehåller ord som ”försäljning”, ”försäljningschef” eller ”försäljningspersonal”

”försäljning avd”

Visar sökresultat som innehåller den exakta frasen ”försäljning avd”

##### Se även:

![](../Resources/Images/icon-document-link.png)  [Söka efter kandidater](searching_for_candidates.htm)
![](../Resources/Images/icon-document-link.png)  [Jobbkategorier](job_categories.htm)
![](../Resources/Images/icon-document-link.png)  [Övriga frågor](additional_questions.htm)
![](../Resources/Images/icon-document-link.png)  [Användare: Skapa, Redigera, Radera](users_create_edit_delete.htm)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MzgwNTI5ODZdfQ==
-->