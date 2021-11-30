# Import og eksport af rekrutteringsprojektdata

## Oversigt

Denne artikel beskriver de følgende tre internetservicemetoder fundet i WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyList  - Eksporterer en liste over tilgængelige rekrutteringsprojekter fra EasyCruit.
-   VacancyExport  - Eksporterer rekrutteringsprojekdata fra EasyCruit.
-   VacancyImport  - Importerer rekrutteringsprojekdata fra EasyCruit..

## Aktivering af internetserviceadgang

Adgang til EasyCruits internetservice kræver en gyldig EasyCruit-konto. Autentificering foretages på hver anmodning i forhold til internetservice ved at give en gyldig kundeidentifikation, brugernavn og adgangskode i SOAP-overskriften af anmodningen. Bemærk, at adgangskoder ikke må indeholde £ eller €.

Derudover styres adgangen til de forskellige internetservicemetoder af et sæt konfigurationsmuligheder i EasyCruit til både kunden som helhed og til hver individuel kundeindtastning. Dette gøres for at opnå maksimal kontrol med, hvem der har tilladelse til at se data via EasyCruits internetservicer. For at få adgang til en af internetservicemetoderne skal både kunden og brugeren konfigureres med de nødvendige privilegier i EasyCruit. Dette kan gøres ved at sende en anmodning til EasyCruits Customer Success-teamet, hvori du specificerer, hvilke internetservicemetoder der er behov for, og hvilke brugere der skal have adgang til hvilke metoder.

I EasyCruit i både kunde- og brugeropsætningen henvises til eksport/import-internetservicerne på følgende måde:

-   Adgang til eksport af rekrutteringsoversigt (VacancyList)
-   Adgang til eksport af beskrivelsesdata for rekrutteringsdata (VacancyExport)
-   Adgang til import af beskrivelsesdata for rekrutteringsdata (VacancyImport)

## Eksport af rekrutteringsprojektliste

For at få en liste over rekrutteringsprojekter, som en given bruger har adgang til i EasyCruit, skal man foretage et SOAP-opkald i EasyCruit-hjemmesideservicemetoden, der hedder ”VacancyList” ved hjælp af de særlige brugeroplysninger til login.

VacancyList kan anvende to valgfrie parametre: sprog og afdeling. Disse parametre kan anvendes til at filtrere den eksporterede liste på et givent sprog og/eller en afdeling. Hvis der ikke angives nogen parametre, vises en komplet liste af rekrutteringsprojekter. Den eksporterede liste kan anvendes til yderligere opkald til den samme metode for at indsnævre udvalget eller som input til yderligere opkald i forhold til VacancyExport-metoden.

Den liste, der fremkommer, indeholder et rekrutteringsprojektelement for hvert tilgængeligt rekrutteringsprojekt. ”Id”-parametret i hvert rekrutteringsprojekt er det interne projekt i EasyCruit. Hvert rekrutteringsprojekt indeholder:

-   et titelelement, der er projekttitlen i EasyCruit.
-   et RefId-element, der er kundens eksterne reference (dette kan være tomt).
-   en liste over afdelinger som rekrutteringsprojektet tilhører med afdelings-id og navne,
-   en liste over sprog som rekrutteringsprojekt er tilgængeligt på.

### XML-skemadefinitioner

XML-skema til VacancyList-anmodning:  [https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML-skema til VacancyList-svar:  [https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML-eksempler

#### VacancyList SOAP-anmodningseksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header>

<urn:AuthHeader>

<Customer>?</Customer>

<Username>?</Username>

<Password passwordEncoding="?">

<passwordString>?</passwordString>

</Password>

<!--Optional:-->

<Version>?</Version>

</urn:AuthHeader>

</soapenv:Header>

<soapenv:Body>

<urn:VacancyList>

<urn:Vacancy language="?" department="?"/>

</urn:VacancyList>

</soapenv:Body>

</soapenv:Envelope>

#### VacancyList SOAP-svareksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header/>

<soapenv:Body>

<urn:VacancyListResponse>

<VacancyList ContentLanguage="?">

<!--Zero or more repetitions:-->

<Vacancy id="?">

<!--You may enter the following 4 items in any order-->

<Title>?</Title>

<RefId>?</RefId>

<Departments>

<!--1 or more repetitions:-->

<Department id="?">?</Department>

</Departments>

<Languages>

<!--1 or more repetitions:-->

<Language iso="?">?</Language>

</Languages>

</Vacancy>

</VacancyList>

</urn:VacancyListResponse>

</soapenv:Body>

</soapenv:Envelope>

.NET C# example

anvender system;

klasse ECVacancyList

{

public static void Main(string[] args)

{

Service.AuthHeaderValue = new AuthHeader();

p.passwordEncoding = passwordType.SHA1;

p.passwordEncodingSpecified = true;

Service.AuthHeaderValue.Password = p;

VacancyList.Vacancy = new VacancyListVacancy();

VacancyListResponse VacancyListResponse = Service.VacancyList

(VacancyList);

VacancyListDataVacancy[] Vacancy =

VacancyListResponse.VacancyList.Vacancy;

/* Returned object data */

// Vacancy[ i ].Title

// Departments[ j ].Value

}

// Languages[ k ].iso

// Languages[ k ].Value

}

## Eksport af rekrutteringsprojektdata

For at eksportere rekrutteringsprojektdata fra EasyCruit skal du foretage et SOAP-opkald til EasyCruit-internetservicen “VacancyExport”. Denne metode anvender fire obligatoriske parametre: id, (projekt-id for rekrutteringsprojektet i EasyCruit) sprog, afdelings-id og tillad/XML-tags.

Hvis du ikke angiver et rekrutteringsprojekt-id, vises alle de rekrutteringsprojekter, som en given bruger har adgang til. Det er derfor tilrådeligt, at du først bruger VacancyList-internetservicen som et filter til at mindske antallet af eksporterede data. Ethvert rekrutteringsprojekt kan eksisterer på mere end et sprog (disse sprog kan varierer fra projekt til projekt). For at hente et rekrutteringsprojekt på norsk, angives ”nb” i sprogparametreret, For at hente alle rekrutteringsprojekter for en bestemt kundeafdeling, skal du angive afdelingens id i afdelingsparametret (afdelings-id’er og rekrutteringsprojekt-id kan hentes fra VacancyList -internetservicen). AllowXMLTags specificeres, hvis vi skal vise annoncetekst som rådata, eller hvis vi skal fjerne HTML-tags osv. fra teksten inden eksport.

Den liste, der fremkommer, indeholder et rekrutteringsprojektelement for hvert eksporteret rekrutteringsprojekt. ”Id”-parametret på hvert rekrutteringsprojekt er det interne projekt-id i EasyCruit og sprogparametret angiver det sprog, som rekrutteringsprojektet er blevet publiceret på. Hvert rekrutteringsprojekt indeholder de følgende elementer:

-   ProjectTitle, hvilket er titlen på projektet i EasyCruit.
-   RefId, hvilket er kundens eksterne referenceid.

Projekt-id, rekrutteringsprojektsprog, ProjectTitle og RefId er kun til intern reference og skal ikke bruges til publicering:

Elementer til publicering er:

-   TitleHeading: Overskriften over rekrutteringsprojekttitlen.
-   Title: Rekrutteringsprojekttitel.
-   CompanyName: navnet på en virksomhed som det vises i rekrutteringsprojektet.
-   Tekst: annonceteksten (enten som rådata eller uden HTML-indtastninger afhængigt af parametret Tillad MLTags).
-   Deadline: dato (ikke nødvendigvis en dato-/tidsværdi), der er deadline for ansøgning på den ledige stilling.
-   Ansættelse: dato (ikke nødvendigvis en dato-/tidsværdi), hvor virksomheden vil ansætte.
-   Placering: Geografisk placering for jobbet/stillingen.
-   Virksomhedsoplysninger: virksomhedselementet har tre underelementer; afdeling, om og hjemmeside. Dette er navnet, beskrivelsen og hjemmesiden for den ansættende kundeafdeling. Hvis stillingen er til mere end en afdeling, gentages disse oplysninger for hver individuel afdeling.
-   Kontaktpersoner: liste overkontaktpersoner, der er inkluderet i rekrutteringsprojektet, samt den afdeling de tilhører.

### XML-skemadefinitioner

XML-skema til VacancyExport-anmodning:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-skema til VacancyExport-svar:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-eksempler

#### VacancyExport SOAP-anmodningseksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header>

<urn:AuthHeader>

<Customer>?</Customer>

<Username>?</Username>

<Password passwordEncoding="?">

<passwordString>?</passwordString>

</Password>

<!--Optional:-->

<Version>?</Version>

</urn:AuthHeader>

</soapenv:Header>

<soapenv:Body>

<urn:VacancyExport>

<urn:Vacancy id="?" department="?" language="?" allowMLTags="?"/>

</urn:VacancyExport>

</soapenv:Body>

</soapenv:Envelope>

## VacancyExport SOAP-svareksempler

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header/>

<soapenv:Body>

<urn:VacancyExportResponse>

<VacancyList>

<!--Zero or more repetitions:-->

<Vacancy id="?" language="?">

<!--You may enter the following 13 items in any order-->

<ProjectTitle>?</ProjectTitle>

<refId>?</refId>

<TitleHeading>?</TitleHeading>

<Title>?</Title>

<CompanyName>?</CompanyName>

<Body>?</Body>

<Deadline>?</Deadline>

<Engagement>?</Engagement>

<Location>?</Location>

<DailyHours>?</DailyHours>

<Contacts>

<!--Zero or more repetitions:-->

<Contact>

<!--You may enter the following 5 items in any order-->

<Name>?</Name>

<EmailAddress>?</EmailAddress>

< TelephoneOffice>?< /TelephoneOffice>

< TelephoneMobile>?< /TelephoneMobile>

< Department id="?">?< /Department>

< /Contact>

< /Contacts>

< Questions>?< /Questions>

< CompanyInformation>

< !--Zero or more repetitions:-->

< Company>

< !--You may enter the following 3 items in any order-->

< Department>?< /Department>

< About>?< /About>

< Homepage>?< /Homepage>

< /Company>

< /CompanyInformation>

< /Vacancy>

< /VacancyList>

< /urn:VacancyExportResponse>

< /soapenv:Body>

< /soapenv:Envelope>

.NET C# example:

anvender system;

class ECVacancyExport

{

public static void Main(string[] args)

{

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "company";

p.passwordEncoding = passwordType.SHA1;

p.passwordEncodingSpecified = true;

Service.AuthHeaderValue.Password = p;

s.Vacancy = new VacancyExportVacancy();

/* Returned object data */

// vacancy[i].refId

// vacancy[i].TitleHeading

// vacancy[i].Title

// vacancy[i].CompanyName

// vacancy[i].DailyHours

// company[j].About

}

for (int k = 0; k < contacts.Length; k++)

{

// contacts[k].Name

// contacts[k].TelephoneOffice

ContactListContactDepartment department = contacts[k].Department;

// department.Value

}

}

## Import af rekrutteringsprojektdata

For at importere rekrutteringsprojektdata fra EasyCruit skal du foretage et SOAP-opkald til EasyCruit-internetservicen “VacancyImport”.

Følgende data kan importeres:

-   Title: Rekrutteringsprojekttitel.
-   TitleHeading: Overskrift over rekrutteringsprojekttitlen.
-   Body: Tekst i rekrutteringsprojektet.
-   Deadline: Dato som ansøgere skal søge inden.
-   Engagement: Tidspunkt for ansættelse.
-   Placering: Geografisk placering for jobbet/stillingen.

Der er to obligatoriske parametre, der skal specificeres:

-   Sprogparameteret i Versionselementet angiver, hvilket sprog rekrutteringsprojektet er på.
-   RefId-parameteret på rekrutteringsprojektets elementparameter er kundens interne reference til rekrutteringsprojektet.

De importerede data bliver tilgængelige og valgbare via en dropdown-menu i EasyCruit, når en bruger starter et nyt rekrutteringsprojekt.

### XML-skemadefinitioner

XML-skema til VacancyExport-anmodning:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-skema til VacancyExport-svar:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-eksempler

#### VacancyImport SOAP-anmodningseksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Optional:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyImport>

< !--1 or more repetitions:-->

< urn:Vacancy RefId="?">

< !--1 or more repetitions:-->

< urn:Version Language="?">

< !--You may enter the following 8 items in any order-->

< urn:Title>?< /urn:Title>

< !--Optional:-->

< urn:TitleHeading>?< /urn:TitleHeading>

< !--Optional:-->

< urn:Body>?< /urn:Body>

< !--Optional:-->

< urn:Deadline>?< /urn:Deadline>

< !--Optional:-->

< urn:Engagement>?< /urn:Engagement>

< !--Optional:-->

< urn:Location>?< /urn:Location>

< !--Optional:-->

< urn:DailyHours>?< /urn:DailyHours>

< !--Optional:-->

< urn:Questions>?< /urn:Questions>

< /urn:Version>

< /urn:Vacancy>

< /urn:VacancyImport>

< /soapenv:Body>

< /soapenv:Envelope>

#### VacancyImport SOAP-svareksempler

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyImportResponse>

< !--Optional:-->

< Status>?< /Status>

< /urn:VacancyImportResponse>

< /soapenv:Body>

< /soapenv:Envelope>

#### .NET C# example

class ECVacancyImport

{

public static void Main(string[] args)

{

Service.AuthHeaderValue = new AuthHeader();

p.passwordEncoding = passwordType.SHA1;

p.passwordEncodingSpecified = true;

Service.AuthHeaderValue.Password = p;

VacancyImportVacancy[] Vacancy = new VacancyImportVacancy[1];

Version.Language = "nb";

Version.TitleHeading = "Systems Developers";

Version.Body = "This is the vacancy text";

Version.Deadline

Version.Engagement = "1. august 2008";

Version.Location = "Oslo";

MessageVacancyImportResponse result = Service.VacancyImport(Vacancy);

Console.WriteLine(result.Status);

}

}

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Kandidat-API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Rekrutteringsprojekt XML-feed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Integration/API’er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Eksempel på internetservicesvar](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTY3NDk0MzAxXX0=
-->