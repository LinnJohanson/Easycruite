# Kandidaten-API-methodes

## Een gerelateerde methodeset

De EasyCruit-webservice-interface bestaat uit een set van benoemde methodes. Deze methodes zijn onderling gerelateerd. Dit gebeurt op een dusdanige manier dat de informatie die opgehaald wordt door het aanroepen van één methode gebruikt kan worden als input voor een andere, gerelateerde methode.

Er zijn methodes om lijsten met projecten en lijsten met kandidaten op te halen. Dit geeft een overzicht van de beschikbare gegevens. Een bepaald project of bepaalde kandidaat kan dan geselecteerd worden voor volledige export. Alle gegevens met betrekking tot het item worden dan opgehaald. Deze combinatie van een uitgebreide lijst en volledige details zorgt ervoor dat een klant alle gegevens op kan halen.

Dit kan het beste verduidelijkt worden aan de hand van een voorbeeld. Er is een methode genaamd CandidateIdList en als deze aangeroepen wordt, dan kan een klant een lijst met kandidaatrecordidentifiers ophalen. Alle opgeslagen gegevens voor een bepaalde kandidaat kunnen dan opgehaald worden door de betreffende identifier aan te leveren aan een andere methode, genaamd CandidateExport.

## Beschikbare methodes

Voor het exacte XML-formaat voor input en output kunnen de XML-schemabestanden bestudeerd worden waarnaar verwezen wordt vanaf het WSDL-bestand: WSDL-bestand - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Normaal krijgt u niet zelf met dit aspect te maken aangezien uw tools dit deel van het werk voor u moeten doen.

#### Gemeenschappelijke authenticatieparameter

Voor elke methode moet u authenticatiegegevens (gedefinieerd in de SOAP HEAD) meesturen met uw specifieke aanvraag. Er worden geen aanvragen verwerkt zonder succesvolle authenticatie en autorisatie van de auteur van de inkomende aanvraag. Deze authenticatiegegevens bestaan uit de naam van de klant, de gebruikersnaam en het wachtwoord. Dit zijn exact dezelfde gegevens als voor het inloggen in de EasyCruit-webtoepassing via de inlogpagina. Wij wijzen u er echter op dat voor toegang tot de webservice u de logingegevens van een webservicegebruiker moet aanleveren. De wachtwoorden mogen niet £ of € bevatten.

#### CandidateSearch

CandidateSearch levert een lijst met kandidaten aan binnen de opgegeven zoekparameters. De lijst bevat een kandidaats id, voornaam, tweede voornaam, achternaam, toevoegingsdatum, wijzigingsdatum, indienstnamedatum en het type kandidaat (candidate, cv_candidate, cv_prospect, co-worker).

XSD-bestanden:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parameters:

DateAddedFrom – datum in ISO-notatie JJJJ-MM-DD

DateAddedTo – datum in ISO-notatie JJJJ-MM-DD

DateModifiedFrom – datum in ISO-notatie JJJJ-MM-DD

DateModifiedTo – datum in ISO-notatie JJJJ-MM-DD

Category – tekenreeksopsomming (candidate, cv_candidate, cv_prospect, co-worker)

#### CandidateExport

CandidateExport retourneert een tekenreeks die een tekeneenheidsgecodeerd XML-document is. U moet deze dan decoderen en parseren in XML. Verdere beschrijving van de XML staat in Candidate.xsd

XSD-bestanden:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

CandidateID – geheel getal [verplicht]

Language – twee tekens ISO [optioneel]

#### CandidateImport

CandidateImport leest een tekeneenheidsgecodeerd XML-document verstuurd als een tekenreeks en voegt het toe aan de cv-database / talentpool van de klant.

Verdere beschrijving van de XML staat in Candidate.xsd

XSD-bestanden:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

Candidate – tekenreeks (zie  [https://www.easycruit.com/wsdl/ws/Candidate.xsd] (https://www.easycruit.com/wsdl/ws/Candidate.xsd)  voor details) [verplicht]

7 / 14

#### CandidateUpdate

Zelfde als CandidateImport, maar de kandidaat-id is verplicht in het XML-document.

XSD-bestanden:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd] (https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd] (https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd] (https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

Candidate – tekenreeks (zie  [https://www.easycruit.com/wsdl/ws/Candidate.xsd] (https://www.easycruit.com/wsdl/ws/Candidate.xsd)  voor details) [verplicht]

#### AddCandidateToRecruitingProject

XSD-bestanden:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd] (https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd] (https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parameters:

CandidateId – geheel getal [verplicht]

RecruitingProjectId – geheel getal [verplicht]

DepartmentId – geheel getal [verplicht]

RecruiterId – geheel getal [optioneel]

#### DocumentUpload

DocumentUpload kan gebruikt worden om een cv of foto toe te voegen aan een kandidaatrecord. Het bestand mag niet groter zijn dan 2 MB en een bestand van het type CV mag enkel in de volgende formaten zijn:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Een bestand van het type Picture mag enkel in de volgende formaten zijn:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD-bestanden:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd] (https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd] (https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parameters:

CandidateId – geheel getal [verplicht]

DocumentType – tekenreeksopsomming (cv, picture) [verplicht]

DocumentName – tekenreeks [verplicht]

Document – tekenreeks (MIME Base64-gecodeerde versie van het document) [verplicht]

#### DocumentDownload

XSD-bestanden:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd] (https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd] (https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parameters:

CandidateId – geheel getal [verplicht]

DocumentName – tekenreeks [verplicht]

#### CandidateValidateUsername

CandidateValidateUsername wordt gebruikt om te controleren of een gebruikersnaam aanwezig en correct ingedeeld is.

XSD-bestanden:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd] (https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd] (https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parameters:

CandidateUsername – tekenreeks [verplicht]

#### CVSetup

CVSetup retourneert de beschikbare gegevensvelden voor de opgegeven klant; dit kan gebruikt worden om klantspecifieke vragen in te vullen.

Klantspecifieke vraag

XSD-bestanden:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd] (https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd] (https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parameters:

Language

#### Events

Events retourneert beschikbare gebeurtenissen op basis van de opgegeven parameters.

XSD-bestanden:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd] (https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd] (https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parameters:

EventModule – tekenreeks [verplicht] bv. cv

EventClass – tekenreeks [verplicht] bv. hired

HandledByIdentifier – tekenreeks [optioneel] bv. my_web_service_client

HandledByTracked – booleaanse waarde [optioneel] houdt gebeurtenissen bij die u eerder gestuurd heeft.

HandledByStatus – opsomming (all, processed, new) [optioneel] wat weergegeven moet worden, standaard is new.

#### VOORBEELD MONO .NET C#

using System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "klant";

Service.AuthHeaderValue.Username = "gebruikersnaam";

Service.AuthHeaderValue.Password = "wachtwoord";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

Om het bovenstaande voorbeeld te compileren, moet u het WSDL-bestand downloaden vanaf EasyCruit en het compileren. WSDL-URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl] (https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Voorbeeld van opdrachtregel van compilatie

wsdl EasyCruit.wsdl

mcs /target:library EasyCruit.cs r:System.Web.Services

mcs /r:EasyCruit.dll ec_soap.cs

PERL SOAP::LITE EXAMPLE

my $service = SOAP::Lite>service('[https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl] (https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)');

my $candidate = $service>CandidateExport(SOAP::Data>name('ec:CandidateId',123456789),SOAP::Data>name('ec:Language','gb'),

SOAP::Header>name(

AuthHeader => [

SOAP::Data>name('Customer', 'customer'),

SOAP::Data>name('Username', 'username'),

SOAP::Data>name('Password', 'password')

]

)

);

print ($candidate gt '' ? $candidate : 'Unable to retrieve data..');

VOORBEELD RAW SOAP REQUEST

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema] (http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance] (http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" >

< soap:Header>

< AuthHeader>

< Customer>klant< /Customer>

< Username>gebruikersnaam< /Username>

< Password>wachtwoord< /Password>

< /AuthHeader>

< /soap:Header>

< soap:Body>

< CandidateExport>

< Language>no< /Language>< CandidateId>123456789< /CandidateId>

< /CandidateExport>

< /soap:Body>

< /soap:Envelope>

VOORBEELD RAW SOAP RESPONSE

<?xml version="1.0" encoding="UTF8"?>

< soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)">

< soap:Body>

 CandidateExportResponse >

< Candidate>DATA< /Candidate>

< /CandidateExportResponse>

< /soap:Body>

< /soap:Envelope>

De DATA voor dit voorbeeld moeten gedecodeerd worden en de daaruit resulterende XML is gebaseerd op het onderstaande schema:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

##### Zie ook:

![](../Resources/Images/icon-document-link.png)  [Importeren en exporteren van vacaturegegevens](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Vacature-XML-feed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Integratie / API's](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Voorbeeld Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Rapportages](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4MTExNjQ3Ml19
-->