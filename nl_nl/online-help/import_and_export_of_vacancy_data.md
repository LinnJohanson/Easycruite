# Importeren en exporteren van vacaturegegevens

## Overzicht

Dit hoofdstuk beschrijft de volgende drie webservicemethodes gevonden in de WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyList  - Exporteert een lijst met beschikbare vacatures vanaf EasyCruit.
-   VacancyExport  - Exporteert de vacaturegegevens vanaf EasyCruit.
-   VacancyImport  - Importeert vacaturegegevens in EasyCruit.

## Toegang tot de webservice

Voor toegang tot de EasyCruit-webservice is een geldig EasyCruit-account nodig. Authenticatie gebeurt bij elke aanvraag voor de webservice door het opgeven van een geldige klantidentifier, gebruikersnaam en wachtwoord in de SOAP-header van de aanvraag. De wachtwoorden mogen niet £ of € bevatten.

Daarnaast wordt de toegang tot de individuele webservicemethodes gecontroleerd door een set configuratieopties in EasyCruit voor zowel de klant in zijn geheel als voor elke individuele gebruikersentiteit. Dit wordt gedaan voor maximale controle van wie toegang heeft tot welke gegevens via EasyCruit-webservices. Om toegang te krijgen tot een van de webservicemethodes, moet zowel een klant als een gebruiker geconfigureerd worden met de benodigde bevoegdheden in EasyCruit. Dit kan door een verzoek te sturen naar het EasyCruit Customer Success-team, met vermelding van de benodigde webservicemethodes en van welke gebruikers toegang moeten krijgen tot welke methodes.

Binnen EasyCruit wordt in zowel de configuratie van klanten als van gebruikers naar de export-/importwebservices verwezen als:

-   Toegang tot export van vacaturelijst (VacancyList)
-   Toegang tot export van vacatureomschrijvingsgegevens (VacancyExport)
-   Toegang tot import van vacatureomschrijvingsgegevens (VacancyImport)

## Exporteren van een vacaturelijst

Om een lijst met vacatures op te halen waartoe een bepaalde gebruiker toegang toe heeft in EasyCruit, moet u een SOAP-aanroep doen aan de EasyCruit-webservicemethode genaamd ‘VacancyList’ met de logingegevens van de betreffende gebruiker.

VacancyList kan twee optionele parameters hebben: taal (language) en afdeling (department). Deze parameters kunnen gebruikt worden om de geëxporteerde lijst te filteren op een bepaalde taal en/of afdeling. Als er geen parameters opgegeven zijn, dan wordt een volledige vacaturelijst geretourneerd. De geëxporteerde lijst kan gebruikt worden voor extra aanroepen aan dezelfde methode om de selectie te verfijnen of als input voor andere aanroepen bij de VacancyExport-methode.

De resultatenlijst bevat één Vacancy-element voor elke beschikbare vacature. De ‘id’-parameter van elke vacature is de interne project-id in EasyCruit. Elke vacature (Vacancy) bevat:

-   een Title-element; dit is de projecttitel in EasyCruit.
-   een RefId-element; dit is het externe referentienummer van de klant (mag leeg zijn).
-   een lijst met afdelingen (Departments) waartoe de vacature behoort met afdelings-id’s en -namen.
-   een lijst met talen (Languages) waarin de vacature beschikbaar is.

### XML-schemadefinities

XML-schema voor VacancyList-request:  [https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd] (https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML-schema voor VacancyList-response:  [https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd] (https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML-voorbeelden

#### Voorbeeld VacancyList SOAP-request

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Optioneel:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyList>

< urn:Vacancy language="?" department="?"/>

< /urn:VacancyList>

< /soapenv:Body>

< /soapenv:Envelope>

#### Voorbeeld VacancyList SOAP-response

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyListResponse>

< VacancyList ContentLanguage="?">

< !--Nul of meer herhalingen:-->

< Vacancy id="?">

< !--U kunt de volgende 4 items in elke volgorde invoeren-->

< Title>?< /Title>

< RefId>?< /RefId>

< Departments>

< !--1 of meer herhalingen:-->

< Department id="?">?< /Department>

< /Departments>

< Languages>

< !--1 of meer herhalingen:-->

< Language iso="?">?< /Language>

< /Languages>

< /Vacancy>

< /VacancyList>

< /urn:VacancyListResponse>

< /soapenv:Body>

< /soapenv:Envelope>

Voorbeeld .NET C#

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

## Exporteren van vacaturegegevens

Om vacaturegegevens te exporteren vanaf EasyCruit, moet u een SOAP-aanroep doen aan de EasyCruit-webservice ‘VacancyExport’. Deze methode heeft vier optionele parameters: id (project-id voor de vacature in EasyCruit), taal (language), afdelings-id (department id) en XML-tags toestaan (allowXMLTags).

Als u geen vacature-id opgeeft, dan worden alle vacatures waar een bepaalde gebruiker toegang toe heeft geretourneerd. Het is daarom raadzaam om eerst de VacancyList-webservice te gebruiken als filter om de hoeveelheid geëxporteerde gegevens terug te brengen. Elke vacature kan bestaan in één of meerdere talen (welke talen beschikbaar zijn kan verschillen per vacature). Om een vacature in het Noors op te halen, moet u ‘nb’ opgeven voor de language-parameter. Om alle vacatures op te halen voor een bepaalde afdeling, moet u de afdelings-id opgeven in de department-parameter (afdelings-id's en vacature-id's kunnen overgenomen worden van de VacancyList-webservice). AllowXMLTags bepaalt of de vacaturetekst geretourneerd moet worden als raw data of dat de HTML-tags enzovoort verwijderd moeten worden uit de tekst vóór het exporteren.

De resultatenlijst bevat één Vacancy-element voor elke geëxporteerde vacature. De ‘id’-parameter van elke vacature is de interne project-id in EasyCruit en de language-parameter geeft aan in welke taal de vacature gepubliceerd is. Elke vacature (Vacancy) bevat de volgende elementen:

-   ProjectTitle, de titel van het project in EasyCruit.
-   RefId, de externe referentie-id van de klant.

Vacancy id, vacancy language, ProjectTitle en RefId is voor de interne referentie en is niet bedoeld voor publicatie.

Elementen die gebruikt worden voor publicatie zijn:

-   TitleHeading: De kop boven de vacaturetitel.
-   Title: De vacaturetitel.
-   CompanyName: De naam van het bedrijf zoals weergegeven in de vacature.
-   Body: De vacaturetekst (raw data of gestript voor HTML-codes, afhankelijk van de allowMLTags-parameter).
-   Deadline: De datum (niet noodzakelijkerwijs een datum/tijd-waarde) die de deadline voor solliciteren naar de vacature is.
-   Engagement: De datum (niet noodzakelijkerwijs een datum/tijd-waarde) waarop het bedrijf in dienst wil nemen.
-   Location: Geografische locatie van de functie / positie.
-   CompanyInformation: Het company-element heeft drie subelementen, Department, About en Homepage. Dit is de naam, beschrijving en homepage van de afdeling die in dienst neemt. Als de positie voor meer dan één afdeling is, dan wordt deze informatie herhaald voor elke individuele afdeling.
-   Contacts: Lijst met contactpersonen die toegevoegd zijn aan de vacature en de afdelingen waartoe ze behoren.

### XML-schemadefinities

XML-schema voor VacancyExport-request:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd] (https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-schema voor VacancyExport-response:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd] (https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-voorbeelden

#### Voorbeeld VacancyExport SOAP-request

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

 < urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Optioneel:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyExport>

< urn:Vacancy id="?" department="?" language="?" allowMLTags="?"/>

< /urn:VacancyExport>

< /soapenv:Body>

< /soapenv:Envelope>

## Voorbeeld VacancyExport SOAP-response

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

 < urn:VacancyExportResponse>

 < VacancyList>

< !--Nul of meer herhalingen:-->

< Vacancy id="?" language="?">

< !--U kunt de volgende 13 items in elke volgorde invoeren-->

< ProjectTitle>?< /ProjectTitle>

< refId>?< /refId>

< TitleHeading>?< /TitleHeading>

< Title>?< /Title>

< CompanyName>?< /CompanyName>

< Body>?< /Body>

< Deadline>?< /Deadline>

< Engagement>?< /Engagement>

< Location>?< /Location>

< DailyHours>?< /DailyHours>

< Contacts>

< !--Nul of meer herhalingen:-->

< Contact>

< !--U kunt de volgende 5 items in elke volgorde invoeren-->

< Name>?< /Name>

< EmailAddress>?< /EmailAddress>

< TelephoneOffice>?< /TelephoneOffice>

< TelephoneMobile>?< /TelephoneMobile>

< Department id="?">?< /Department>

< /Contact>

< /Contacts>

< Questions>?< /Questions>

< CompanyInformation>

< !--Nul of meer herhalingen:-->

< Company>

< !--U kunt de volgende 3 items in elke volgorde invoeren-->

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

Voorbeeld .NET C#:

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

## Importeren van vacaturegegevens

Om vacaturegegevens te importeren in EasyCruit, moet u een SOAP-aanroep doen aan de EasyCruit-webservice ‘VacancyImport’.

De volgende gegevens kunnen geïmporteerd worden:

-   Title: Vacaturetitel.
-   TitleHeading: Kop boven vacaturetitel.
-   Body: Vacaturetekst.
-   Deadline: Datum waarvoor de sollicitant moet solliciteren.
-   Engagement: Periode van indienstname.
-   Location: Geografische locatie van functie / positie.

Er zijn twee verplichte parameters die opgegeven moeten worden:

-   De Language-parameter van het Version-element geeft aan in welke taal de vacature is.
-   De RefId-parameter op de Vacancy-elementparameter is het interne referentienummer van de klant voor de vacature.

De geïmporteerde gegevens zijn beschikbaar en selecteerbaar in een vervolgkeuzemenu in EasyCruit als een gebruiker een nieuwe vacature aanmaakt.

### XML-schemadefinities

XML-schema voor VacancyExport-request:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-schema voor VacancyExport-response:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-voorbeelden

#### Voorbeeld VacancyImport SOAP-request

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Optioneel:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyImport>

< !--1 of meer herhalingen:-->

< urn:Vacancy RefId="?">

< !--1 of meer herhalingen:-->

< urn:Version Language="?">

< !--U kunt de volgende 8 items in elke volgorde invoeren-->

< urn:Title>?< /urn:Title>

< !--Optioneel:-->

< urn:TitleHeading>?< /urn:TitleHeading>

< !--Optioneel:-->

< urn:Body>?< /urn:Body>

< !--Optioneel:-->

< urn:Deadline>?< /urn:Deadline>

< !--Optioneel:-->

< urn:Engagement>?< /urn:Engagement>

< !--Optioneel:-->

< urn:Location>?< /urn:Location>

< !--Optioneel:-->

< urn:DailyHours>?< /urn:DailyHours>

< !--Optioneel:-->

< urn:Questions>?< /urn:Questions>

< /urn:Version>

< /urn:Vacancy>

< /urn:VacancyImport>

< /soapenv:Body>

< /soapenv:Envelope>

#### Voorbeeld VacancyImport SOAP-response

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

 < urn:VacancyImportResponse>

< !--Optioneel:-->

< Status>?< /Status>

< /urn:VacancyImportResponse>

< /soapenv:Body>

< /soapenv:Envelope>

#### Voorbeeld .NET C#

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

Version.Body = "Dit is de vacaturetekst";

Version.Deadline

Version.Engagement = "1. august 2008";

Version.Location = "Oslo";

MessageVacancyImportResponse result = Service.VacancyImport(Vacancy);

Console.WriteLine(result.Status);

}

}

##### Zie ook:

![](../Resources/Images/icon-document-link.png)  [Kandidaten-API-methodes](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Vacature-XML-feed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Integratie / API's](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Voorbeeld Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Rapportages](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MzM3NTgxOTIsNjU4MDc2MTIyXX0=
-->