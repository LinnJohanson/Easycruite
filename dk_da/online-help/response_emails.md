# Svarmails

Svarmails anvendes i hele EasyCruits ansøgningsproces lige fra den indledende e-mail til en kandidats bekræftelse af ansøgningen til et rekrutteringsprojekt og endelig til afsendelsen af en jobkontrakt.

Svarmails fungerer ved at anvende brugertilpassede e-mail-skabeloner, der kan redigeres til at imødekomme en virksomheds specifikke krav. Indholdet i e-mailen kan redigeres, så som ændring af variablerne, der automatisk indsætter ansøgerens navn. Andre redigerbare muligheder er indstilling af forsinkelse i det antal dage, det tager at sende en automatisk e-mail, og afgørelse af om en svar-e-mailtype automatisk skal inkluderes, når der oprettes et rekrutteringsprojekt.

Svarmailskabeloner kan konfigureres på virksomheds-, afdelings- og underafdelingsniveau. E-mails er tilgængelige i almindeligt tekstformat eller i HTML-format.

Som udgangspunkt er de fleste svar-e-mailskabeloner blevet udfyldt med generisk indhold.

#### Visning af en tilgængelig svarmail

1.  Fra  Værktøjslinjen  klikkes på  Indstillinger  for at vise siden  indstillinger.
2.  Klik på  Svarmails  for at vise siden  Almindelige svarmails.
3.  Klik på et blyantikon ved siden af den relevante e-mail for at se e-mail-indholdet og indstillingerne.
4.  Hvis det er tilgængeligt vælges i listen  Vælg afdeling  en afdeling til at vise e-mailen, som den er levet konfigureret for den specifikke afdeling.
5.  Klik på landeflag for at vise skabelonen i det tilsvarende sprog.

Hvis der eksisterer en afdelingsspecifik svarmail, vises en asterisk ved siden af afdelingsnavnet.

#### Redigering svarmails

1.  Fra  Værktøjslinjen  klikkes på  Indstillinger  for at vise siden  indstillinger.
2.  Klik på  Svarmails  for at vise siden  Almindelige svarmails.
3.  Klik på et blyantikon ved siden af den relevante e-mail for at aktivere indholdet og de indstillinger, der skal redigeres.
4.  I listen  Vælg afdeling  vælges den afdeling, for hvilken du gerne vil bruge de redigerede svarmails.
5.  Vælg flaget for det sprog, der skal redigeres, hvis det er relevant.
6.  Indtast det ønskede indhold i afsnittene  Fra,  Emne,  Indhold  og  Signatur.  
    Variabler kan inkluderes i indholdet i e-mails som eksempelvis {username} og {password}. Vi henviser til  [E-mail-variabler (flettefelter](email_variables.htm)) for yderligere oplysninger.
7.  Fra listen  Handling  vælges  Send e-mail  for at aktivere e-mailskabelonen og gøre den tilgængelig for brug med rekrutteringsprojekter og ansøgere.  
    - eller -  
    Vælg  ingen e-mail  for at gøre e-mailskabelonen inaktiv.
8.  Når det er relevant, udpeges den nødvendige tidsperiode eller forsinkelsen for den tidsrelaterede mulighed.
9.  Når det er relevant, vælges  Aktiver automatisk svarmail for nye projekter?  
    Visse trin er ikke tilgængelige i alle svar-emial.
10.  Klik på  Gem  for at gemme ændringerne eller på  Anuller  for at vende tilbage til den forrige side unde at gemme.

#### HTML-formatterede svarmails

Udover almindelige tekstformatterede svarmails indeholder EasyCruit også muligheden for, at man kan sende HTML-formatterede e-mails. Denne funktion anvender den velkendte WYSIWYG-redigering, der anvendes ved oprettelse af annoncer til et rekrutteringsprojekt til at aktivere HTML-formatteret indhold, der kan tilføjes i e-mails.

#### Redigering af HTML-svarmails

1.  Fra  Værktøjslinjen  klikkes på  Indstillinger  for at vise siden  indstillinger.
2.  Klik på  Svarmails  for at vise siden  Svarmails.
3.  Klik på  Rediger  i den pågældende e-mail for at vise siden  Rediger e-mail.
4.  Redigér afsnittene  Indhold  og  Signatur  med  [Wysiwyg/tekstredigering](wysiwyg_text_editor.htm), eller klik på html for at åbne HTML Source Editor-vinduet.  
    Når du redigerer indhold med HTML Source Editor, skal du klikke på  Opdatér, vinduet lukker, og indholdet opdateres i WYSIWYG-redigeringen, uden at koden vises.  
    Almindelige HTML-tags, så som <font/>, <i/>, <li> og <ul> kan anvendes. E-mail-tags er formatteret på følgende måde: {first-name}, {address}, {company}.
5.  Konfigurer mulighederne  Handling  og  Forsinkelse  og alle de resterende indstillinger ud fra behov og klik på  Gem.

#### Tilføjelse af billeder i HTML-e-mails

En yderligere funktion, der er tilgængelig i HTML-svar-e-mails, der ikke er tilgængelige via den almindelige WYSIWYG-redigering, er den mulighed, der inkluderes i billederne. Billedtyperne der understøttes inkluderer .bmp, .gif, .jpg, .png, og .tiff.

1.  Placér markøren i den del af e-mailen, hvor billedet skal placeres.
2.  Fra den tilsvarende afsnitsværktøjslinje  Indhold  eller  Signatur  klikkes på ikonet med et træ.
3.  I billeddialogboksen indtastes  Billed-URL  for den placering, hvor billedet gemmes som eksempelvis  [http://easycruit.com/images/logo1.gif](http://easycruit.com/images/logo1.gif)  
    - eller -  
    Klik på knappen  Browse  for at vise dialogboksen  Overfør billede  og vælg et billede, der er lagret på din computer.
4.  Udfyld de følgende muligheder i det omfang, det er nødvendigt:
    -   Billedbeskrivelse  - Dette er tekst til værktøjstip, der vises, når musen holdes over billedet.
    -   Justering  - Anvendes til at justere billedet relativt til det sted, hvor det er blevet indsat i e-mailen.
    -   Dimensioner  - Denne værdi udfyldes automatisk med udgangspunkt i størrelsen af billedet, men den kan om nødvendigt ændres. Den er målt i pixels.
    -   Kant  - Anvendt til at placere en sort kant omkring billedet, målt i pixels.
    -   Vertikalt mellemrum/vandret mellemrum  - Anvendt til at udpege polstring omkring billedet og målt i pixels.
5.  Klik på  Indsæt. Billedet er placeret i e-mailen.

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Ansøgning gemt](application_saved.htm)
![](../Resources/Images/icon-document-link.png)  [Brugertilpassede e-mailskabeloner](customizable_email_templates.htm)
![](../Resources/Images/icon-document-link.png)  [Tip en ven](email_a-friend.htm)
![](../Resources/Images/icon-document-link.png)  [E-mailvariabler](email_variables.htm)
![](../Resources/Images/icon-document-link.png)  [Almindelige svarmailtyper](standard_response_email_types.htm)
![](../Resources/Images/icon-document-link.png)  [Afmeld abonnement på jobagent](unsubscribe_from_job_agent.htm)vvv


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTY3Mzc0MjddfQ==
-->