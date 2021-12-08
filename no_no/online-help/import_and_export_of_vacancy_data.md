# Importere og eksportere annonsedata

## Oversikt

Denne artikkelen beskriver følgende tre nettjenestemetoder som finnes i WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyList  – Eksporterer en oversikt over tilgjengelige rekrutteringsprosjekter fra EasyCruit.
-   VacancyExport  – Eksporterer annonsedata fra EasyCruit.
-   VacancyImport  – Importerer annonsedata inn i EasyCruit.

## Tilgang til Web Service

Tilgang til EasyCruit Web Service krever en gyldig EasyCruit-konto. Godkjenningen skjer ved hver forespørsel mot nettjenesten ved å oppgi en gyldig kundeidentifikator, brukernavn og passord i forespørselens SOAP-hode. Passord kan ikke inneholde tegnene £ eller €.

Tilgang til de enkelte nettjenestemetodene styres av et sett med konfigurasjonsalternativer i EasyCruit for både kunden i sin helhet og for hver enkelt brukerenhet. Dette gjøres for å ha maksimal kontroll over hvem som får tilgang til ulike data via EasyCruit Web Service. For å få tilgang til nettjenestemetodene må både kunder og brukere konfigureres med de nødvendige rettighetene i EasyCruit. Dette kan gjøres ved å sende en forespørsel til vårt EasyCruit Customer Success Team og oppgi hvilke nettjenestemetoder som trengs, og hvilke brukere som bør ha tilgang til de ulike metodene.

I både kunde- og brukeroppsettet i EasyCruit refereres det til nettjenestene for eksport/import på følgende måte:

-   Tilgang til eksport av rekrutteringsoversikt (VacancyList)
-   Tilgang til eksport av annonsebeskrivelsedata (VacancyExport)
-   Tilgang til import av annonsebeskrivelsedata (VacancyImport)

## Eksport av rekrutteringsoversikt

Hvis du vil hente en liste over rekrutteringsprosjekter som en bruker har tilgang til i EasyCruit, må du sende en SOAP-forespørsel til nettjenestemetoden «VacancyList» og bruke den bestemte brukerens innloggingsdetaljer.

Det kan brukes to valgfrie parametere med VacancyList: language og department. Disse parameterne kan brukes til å filtrere den eksporterte listen etter det oppgitte språket og/eller avdelingen. Hvis ingen parametere spesifiseres, returneres en fullstendig liste over rekrutteringsprosjekter. Den eksporterte listen kan brukes til ytterligere forespørsler til den samme metoden for å snevre inn utvalget eller som inndata til ytterligere forespørsler mot VacancyExport-metoden.

Listen dette resulterer i, inneholder ett annonseelement for hver tilgjengelige annonse. «id»-parameteren for hver annonse er den interne prosjekt-ID-en i EasyCruit. Hver annonse vil inneholde:

-   et Title-element, som er prosjekttittelen i EasyCruit
-   et RefId-element, som er kundens eksterne referanse (dette kan være tomt)
-   en liste over avdelinger som annonsen tilhører, med avdelingenes ID-er og navn
-   en liste over språkene som annonsen er tilgjengelig på

### XML-skjemadefinisjoner

XML-skjema for VacancyList request:  [https://www.easycruit.com/wsdl/ws/VacancyListRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML-skjema for VacancyList response:  [https://www.easycruit.com/wsdl/ws/VacancyListResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML-eksempler

#### VacancyList SOAP request-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header>

<urn:AuthHeader>

<Customer>?</Customer>

<Username>?</Username>

<Password passwordEncoding="?">

<passwordString>?</passwordString>

</Password>

<!--Valgfritt:-->

<Version>?</Version>

</urn:AuthHeader>

</soapenv:Header>

<soapenv:Body>

<urn:VacancyList>

<urn:Vacancy language="?" department="?"/>

</urn:VacancyList>

</soapenv:Body>

</soapenv:Envelope>

#### VacancyList SOAP response-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header/>

<soapenv:Body>

<urn:VacancyListResponse>

<VacancyList ContentLanguage="?">

<!--Null eller flere repetisjoner:-->

<Vacancy id="?">

<!--Du kan angi de 4 følgende elementene i vilkårlig rekkefølge-->

<Title>?</Title>

<RefId>?</RefId>

<Departments>

<!--1 eller flere repetisjoner:-->

<Department id="?">?</Department>

</Departments>

<Languages>

<!--1 eller flere repetisjoner:-->

<Language iso="?">?</Language>

</Languages>

</Vacancy>

</VacancyList>

</urn:VacancyListResponse>

</soapenv:Body>

</soapenv:Envelope>

.NET C#-eksempel

using System;

class ECVacancyList

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

## Eksport av annonsedata

Hvis du vil eksportere annonsedata fra EasyCruit, må du sende en SOAP-forespørsel til nettjenestemetoden «VacancyExport». Denne metoden kan ta fire valgfrie parametere: id (rekrutteringsprosjektets ID i EasyCruit), language, department id og allowXMLTags.

Hvis ikke du spesifiserer en prosjekt-ID, returneres alle annonser som en gitt bruker har tilgang til. Derfor bør du først bruke nettjenesten VacancyList som filter for å redusere mengden data som eksporteres. Enhver annonse kan være på ett eller flere språk (hvilke språk som er tilgjengelig, kan variere fra annonse til annonse). Hvis du vil hente en annonse på norsk, må du angi «nb» i language-parameteren. Hvis du vil hente alle annonser for en gitt kundeavdelingen, må du spesifisere avdelings-ID-en i department-parameteren (avdelings-ID-er og annonse-ID-er kan hentes fra nettjenesten VacancyList). AllowXMLTags brukes til å spesifisere om annonseteksten skal returneres som rådata, eller om HTML-tagger osv. skal fjernes fra teksten før eksport.

Listen dette resulterer i, inneholder ett annonseelement for hver eksporterte annonse. «id»-parameteren for hver annonse er den interne prosjekt-ID-en i EasyCruit, og language-parameteren spesifiserer språket som annonsen er publisert på. Hver annonse inneholder følgende elementer:

-   ProjectTitle, som er tittelen på prosjektet i EasyCruit
-   RefId, som er kundens eksterne referanse-ID

Vacancy id, vacancy language, ProjectTitle og RefId brukes som intern referanse og er ikke beregnet på publisering.

Følgende elementer brukes til publisering:

-   TitleHeading: Overskriften over stillingstittelen.
-   Title: Stillingstittelen.
-   CompanyName: Navnet på selskapet slik det vises i annonsen.
-   Body: Annonseteksten (enten rådata eller renset for HTML-tagger, avhengig av allow MLTags-parameteren).
-   Deadline: Søknadsfristen (ikke nødvendigvis en dato eller et tidspunkt).
-   Engagement: Tiltredelse (ikke nødvendigvis en dato eller et tidspunkt).
-   Location: Geografisk sted for stillingen.
-   CompanyInformation: Virksomhetselementet har tre underelementer: Department, About og Homepage. Dette er navnet på, beskrivelsen av og hjemmesiden til kundens avdeling som skal ansette. Hvis stillingen gjelder mer enn én avdeling, gjentas denne informasjon for hver enkelt avdeling.
-   Contacts: Liste over kontaktpersoner som er inkludert i annonsen, og hvilke avdelinger de tilhører.

### XML-skjemadefinisjoner

XML-skjema for VacancyExport request:  [https://www.easycruit.com/wsdl/ws/VacancyExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-skjema for VacancyExport response:  [https://www.easycruit.com/wsdl/ws/VacancyExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-eksempler

#### VacancyExport SOAP request-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

 < !--Valgfritt:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

 < urn:VacancyExport>

< urn:Vacancy id="?" department="?" language="?" allowMLTags="?"/>

< /urn:VacancyExport>

< /soapenv:Body>

< /soapenv:Envelope>

## VacancyExport SOAP response-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyExportResponse>

< VacancyList>

< !--Null eller flere repetisjoner:-->

< Vacancy id="?" language="?">

< !--Du kan angi de 13 følgende elementene i vilkårlig rekkefølge-->

< ProjectTitle>?</P rojectTitle>

< refId>?< /refId>

< TitleHeading>?< /TitleHeading>

< Title>?< /Title>

< CompanyName >?< /CompanyName>

< Body>?< /Body>

< Deadline>?< /Deadline>

< Engagement>?< /Engagement>

 < Location>?< /Location>

< DailyHours>?< /DailyHours>

< Contacts>

< !--Null eller flere repetisjoner:-->

< Contact>

< !--Du kan angi de 5 følgende elementene i vilkårlig rekkefølge-->

< Name> ?< /Name>

< EmailAddress>?< /EmailAddress>

< TelephoneOffice>?< /TelephoneOffice>

< TelephoneMobile>?< /TelephoneMobile>

< Department id="?">?< /Department>

< /Contact>

< /Contacts>

< Questions>?< /Questions>

< CompanyInformation>

< !--Null eller flere repetisjoner:-->

< Company>

 < !--Du kan angi de 3 følgende elementene i vilkårlig rekkefølge-->

< Department>?< /Department>

< About>?</ About>

 < Homepage>?< /Homepage>

< /Company>

< /CompanyInformation>

< /Vacancy>

< /VacancyList>

< /urn:VacancyExportResponse>

< /soapenv:Body>

< /soapenv:Envelope>

.NET C#-eksempel:

using System;

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

## Import av annonsedata

Hvis du vil importere annonsedata fra EasyCruit, må du sende en SOAP-forespørsel til nettjenestemetoden «VacancyImport».

Følgende data kan importeres:

-   Title: Stillingstittel.
-   TitleHeading: Overskrift over stillingstittelen.
-   Body: Annonsetekst.
-   Deadline: Søknadsfrist.
-   Engagement: Tiltredelse.
-   Location: Geografisk sted for stillingen.

Det er to obligatoriske parametere som må spesifiseres:

-   Language-parameteren på Version-elementet spesifiserer hvilket språk annonsen er på.
-   RefId-parameteren på Vacancy-elementet er kundens interne referanse for annonsen.

De importerte dataene blir tilgjengelig og kan velges fra en rullegardinmeny i EasyCruit når en bruker oppretter et nytt rekrutteringsprosjekt.

### XML-skjemadefinisjoner

XML-skjema for VacancyExport request:  [https://www.easycruit.com/wsdl/ws/VacancyExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-skjema for VacancyExport response:  [https://www.easycruit.com/wsdl/ws/VacancyExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-eksempler

#### VacancyImport SOAP request-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Valgfritt:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyImport>

< !--1 eller flere repetisjoner:-->
 
< urn:Vacancy RefId="?">

 < !--1 eller flere repetisjoner:-->

 < urn:Version Language="?">

< --Du kan angi de 8 følgende elementene i vilkårlig rekkefølge-->

< urn:Title>? /urn:Title>

< !--Valgfritt:-->

< urn:TitleHeading>?< /urn:TitleHeading>

< !--Valgfritt:-->

 < urn:Body>? </ urn:Body>

< !--Valgfritt:-->

< urn:Deadline>?< /urn:Deadline>

< !--Valgfritt:-->

< urn:Engagement>?< /urn:Engagement>

< !--Valgfritt:-->

< urn:Location>?< /urn:Location>

< !--Valgfritt:-->

< urn:DailyHours>?< /urn:DailyHours>

< !--Valgfritt:-->

< urn:Questions>?< /urn:Questions>

< /urn:Version>

< /urn:Vacancy>

< /urn:VacancyImport>

< /soapenv:Body>

< /soapenv:Envelope>

#### VacancyImport SOAP response-eksempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

 < urn:VacancyImportResponse>

< !--Valgfritt:-->

< Status>?< /Status>

< /urn:VacancyImportResponse>

< /soapenv:Body>

< /soapenv:Envelope>

#### .NET C#-eksempel

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

Version.TitleHeading = "Systemutviklere";

Version.Body = "Dette er annonseteksten";

Version.Deadline

Version.Engagement = "1. august 2008";

Version.Location = "Oslo";

MessageVacancyImportResponse result = Service.VacancyImport(Vacancy);

Console.WriteLine(result.Status);

}

}

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Kandidatrelaterte API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [XML annonsefeed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Integrasjon/API-er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Eksempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwNDkyODcwMl19
-->