# Responsmailer

Responsmailer brukes gjennom hele søknadshåndteringen i EasyCruit, fra en innledende e-post til en kandidat bekrefter sin søknad på en ledig stilling, videre til sending av en jobbkontrakt.

Responsmailer gjør bruk av e-postmaler som kan endres og tilpasses virksomhetens ønsker. Innholdet i e-posten kan endres blant annet ved å skifte variablene som automatisk setter inn søkerens navn. Det kan settes inn en forsinkelse for hvor mange dager det tar før det automatisk sendes en e-post, og om en responsmail automatisk skal inkluderes når det opprettes et rekrutteringsprosjekt.

Maler for responsmail kan konfigureres på bedriftsnivå, avdelingsnivå eller underavdelingsnivå. E-postene er tilgjengelige i standard tekstformat eller i HTML-format.

Som standard er de fleste malene for responsmail fylt ut med generelt innhold.

#### Vise en tilgjengelig responsmail

1.  Fra  verktøylinjen  klikker du på  Innstillinger  for å vise  Innstillinger-siden.
2.  Klikk på  Responsmail  for å vise siden  Standard responsmailer.
3.  Klikk på blyantikonet ved siden av den aktuelle e-posten for å vise e-postinnholdet og innstillingene.
4.  Hvis listen  Velg avdeling  er tilgjengelig, velger du en avdeling som skal vise e-posten ettersom den er konfigurert for den bestemte avdelingen.
5.  Klikk på et flagg for å vise malen på det tilhørende språket.

Hvis en avdelingsspesifikk responsmail finnes fra før, vises en stjerne ved siden av avdelingsnavnet.

#### Endre en responsmail

1.  Fra  verktøylinjen  klikker du på  Innstillinger  for å vise  Innstillinger-siden.
2.  Klikk på  Responsmail  for å vise siden  Standard responsmailer.
3.  Klikk på blyantikonet ved siden av den aktuelle e-posten for å aktivere innholdet og innstillingene som skal endres.
4.  Fra listen  Velg avdeling  velger du avdelingen der du ønsker å bruke den endrede responsmailen.
5.  Velg flagget for det språket som skal endres, hvis aktuelt.
6.  Skriv inn det ønskede innholdet i feltene  Avsender,  Emne,  Innhold  og  Signatur.  
    Variabler kan inkluderes i innholdet for e-postene, slik som {username} og {password}. Se  [E-postvariabler (Flettefelter)](email_variables.htm)  for nærmere informasjon.
7.  Fra listen  Handling  velger du  Send e-post  for å aktivere e-postmalen, slik at den blir tilgjengelig for bruk sammen med rekrutteringsprosjekter og søkere  
    – eller –  
    velg  Ingen e-post  for å deaktivere e-postmalen.
8.  Der det er aktuelt, tilordner du den ønskede tidsperioden eller forsinkelsen til tidsrelaterte alternativer.
9.  Hvis det er aktuelt, merker du av for  Merk her dersom du ønsker å automatisk aktivere denne responsmailen.  
    Enkelte trinn er ikke tilgjengelig for alle responsmailer.
10.  Klikk på  Lagre  for å bekrefte endringene eller på  Avbryt  for å gå tilbake til forrige side uten å lagre.

#### HTML-formaterte responsmailer

I tillegg til standard tekstformatterte responsmailer gir EasyCruit også mulighet til å bruke HTML-formatterte e-poster. Denne funksjonen benytter den velkjente WYSIWYG-editoren som brukes til å utforme annonser, til også å lage HTML-formattert innhold til e-poster.

#### Endre HTML-responsmailer

1.  Fra  verktøylinjen  klikker du på  Innstillinger  for å vise  Innstillinger-siden.
2.  Klikk på  Responsmailer  for å vise siden  Responsmailer.
3.  Klikk på  Endre  for den aktuelle e-posten for å vise siden  Endre e-post.
4.  Endre teksten i feltene  Innhold  og  Signatur  med WYSIWYG-editoren, eller klikk på  [WYSIWYG-/tekst-editor](wysiwyg_text_editor.htm)  for å åpne vinduet HTML-editor.  
    Når du redigerer innhold med HTML-editoren og deretter klikker på  Oppdater, lukkes vinduet og innholdet oppdateres i WYSIWYG-editoren uten at koden vises.  
    Standard HTML-tagger, for eksempel <font/>, <i/>, <li> og <ul>, kan brukes. E-posttaggene utformes slik: {first-name}, {address}, {company}.
5.  Konfigurer alternativene  Handling  og  Forsinkelse  og eventuelle gjenværende innstillinger etter behov, og klikk deretter på  Lagre.

#### Legge til bilder i HTML-e-post

En tilleggsfunksjon som er tilgjengelig i HTML-responsmailer, men som ikke er tilgjengelig via WYSIWYG-editoren, er muligheten til å legge til bilder. Bildetypene som støttes, er blant annet .bmp, .gif, .jpg, .png, og .tiff.

1.  Sett markøren i den delen av e-posten der du ønsker å plassere bildet.
2.  På verktøylinjen til  Innhold- eller  Signatur-delen klikker du på treikonet.
3.  I feltet  Bildets URL  i bildedialogboksen skriver du inn URL-adressen til plasseringen der bildet er lagret, for eksempel  [http://easycruit.com/images/logo1.gif](http://easycruit.com/images/logo1.gif),  
    – eller –  
    klikker på knappen  Bla gjennom  for å vise dialogboksen  Laste opp bilde  og velger et bilde som er lagret på datamaskinen din.
4.  Fyll ut følgende alternativer etter behov:
    -   Bildebeskrivelse  – Dette er en verktøytipstekst som vises når du fører musen over bildet.
    -   Justering  – Brukes til å justere bildets plassering i e-posten.
    -   Dimensjoner  – Denne verdien blir fylt ut automatisk basert på størrelsen på bildet og kan endres hvis det trengs. Størrelsen måles i piksler.
    -   Ramme  – Brukes til å plassere en svart ramme rundt et bilde, målt i piksler.
    -   Vertikal avstand / Horisontal avstand  – Brukes til å angi utfylling rundt et bilde, målt i piksler.
5.  Klikk på  Sett inn. Bildet plasseres i e-posten.

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Søknad lagret](application_saved.htm)
![](../Resources/Images/icon-document-link.png)  [Tilpassede e-postmaler](customizable_email_templates.htm)
![](../Resources/Images/icon-document-link.png)  [Tipse en venn](email_a-friend.htm)
![](../Resources/Images/icon-document-link.png)  [E-postvariabler](email_variables.htm)
![](../Resources/Images/icon-document-link.png)  [Standard responsmailtyper](standard_response_email_types.htm)
![](../Resources/Images/icon-document-link.png)  [Stoppe abonnement på jobbagent](unsubscribe_from_job_agent.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEwOTg3NTUwOV19
-->