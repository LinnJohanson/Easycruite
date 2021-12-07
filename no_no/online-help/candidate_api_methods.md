# Kandidatrelaterte API-metoder

## Et interrelatert sett av metoder

EasyCruits Web Service-grensesnitt består av et sett med navngitte metoder. Disse metodene er innbyrdes sammenhengende eller interrelaterte. Dette er gjort på en slik måte at informasjon som hentes ved å aktivere en metode, kan brukes som inndata til en annen, relatert metode.

Det finnes metoder for å hente prosjektlister og kandidatlister. Dette gir en oversikt over de tilgjengelige dataene. Et bestemt prosjekt eller en kandidat kan deretter velges for full eksport. Dette henter alle data tilknyttet elementet. Denne kombinasjonen av omfattende lister og fullstendige detaljer sørger for at kundene kan hente ut alle sine data.

Det enkleste er å forklare dette med et eksempel. En av metodene kalles CandidateIdList. Ved å aktivere denne kan en kunde hente en liste over kandidatpostidentifikatorer. Alle data som er lagret for en gitt kandidat, kan deretter hentes ved å mate den tilsvarende identifikatoren til en annen metode kalt CandidateExport.

## Tilgjengelige metoder.

Det nøyaktige XML-formatet inndata og utdata kan utforskes ved å studere XML-skjemafilene det refereres til fra WSDL-filen: WSDL-file – https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Normalt skal du ikke behøve å håndtere dette selv, da verktøyene dine skal ta seg av dette.

#### Felles godkjenningsparameter

Alle metodene krever at du sender godkjenningsdata (definert i SOAP HEAD) sammen med den bestemte forespørselen. Ingen forespørsler håndteres uten godkjenning og autorisering av den innkommende forespørselens opphavsperson. Godkjenningsdataene består av kundens navn, brukernavn og passord. Dette er samme type data som kreves ved innlogging på den nettbaserte EasyCruit-programvaren via innloggingsskjemaet. For at du skal få tilgang til Web Service-grensesnittet må du oppgi innloggingsdetaljene til en Web Service-bruker. Passord kan ikke inneholde tegnene £ eller €.

#### CandidateSearch

CandidateSearch gir deg en liste over kandidater innenfor søkeparameterne som er oppgitt. Listen inneholder kandidatens ID, fornavn, mellomnavn, etternavn, dato lagt til, dato endret, dato ansatt og kategorien (candidate, cv_candidate, cv_prospect, co-worker) han eller hun er plassert i.

XSD-filer:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parametere:

DateAddedFrom – ISO-formatert dato ÅÅÅÅ-MM-DD

DateAddedTo – ISO-formatert dato ÅÅÅÅ-MM-DD

DateModifiedFrom – ISO-formatert dato ÅÅÅÅ-MM-DD

DateModifiedTo – ISO-formatert dato ÅÅÅÅ-MM-DD

Category – Opplisting av strenger (candidate, cv_candidate, cv_prospect, co-worker)

#### CandidateExport

CandidateExport returnerer en streng som er et tegnenhetskodet XML-dokument. Du er nødt til å dekode og tolke XML-dokumentet. Du finner mer informasjon om XML-dokumentet i Candidate.xsd

XSD-filer:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametere:

CandidateID – heltall [obligatorisk]

Language – ISO-kode på to tegn [valgfritt]

#### CandidateImport

CandidateImport leser et tegnenhetskodet XML-dokument sendt som en streng og legger det til i kundens CV-base.

Du finner mer informasjon om XML-dokumentet i Candidate.xsd

XSD-filer:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateImportRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateImportResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametere:

Candidate – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for mer informasjon) [obligatorisk]

7 / 14

#### CandidateUpdate

Samme som CandidateImport, men kandidatens ID er obligatorisk i XML-dokumentet.

XSD-filer:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateUpdateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateUpdateResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametere:

Candidate – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for mer informasjon) [obligatorisk]

#### AddCandidateToRecruitingProject

XSD-filer:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/AddCandidateToRecruitingProjectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/AddCandidateToRecruitingProjectResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parametere:

CandidateId – heltall [obligatorisk]

RecruitingProjectId – heltall [obligatorisk]

DepartmentId – heltall [obligatorisk]

RecruiterId – heltall [valgfritt]

#### DocumentUpload

DocumentUpload kan brukes til å legge ved en CV eller et bilde i en kandidatpost. Filen kan ikke være større en 2 MB, og CV-en kan bare være i et av følgende formater:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Bildefiler kan bare være i et av følgende formater:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD-filer:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentUploadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentUplaodResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parametere:

CandidateId – heltall [obligatorisk]

DocumentType – opplisting av strenger (cv, bilde) [obligatorisk]

DocumentName – streng [obligatorisk]

Document – streng (MIME Base64-kodet versjon av dokumentet) [obligatorisk]

#### DocumentDownload

XSD-filer:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentDownloadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentDownloadResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parametere:

CandidateId – heltall [obligatorisk]

DocumentName – streng [obligatorisk]

#### CandidateValidateUsername

CandidateValidateUsername brukes til å kontrollere om et brukernavn er tilgjengelig og formatert riktig.

XSD-filer:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/CandidateValidateUsernameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/CandidateValidateUsernameResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parametere:

CandidateUsername – streng [obligatorisk]

#### CVSetup

CVSetup returnerer tilgjengelige datafelter for den angitte kunden. Dette kan brukes til å fylle ut

kundespesifikke spørsmål.

XSD-filer:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parametere:

Språk

#### Events

Events returnerer tilgjengelige hendelser basert på bestemte parametere.

XSD-filer:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parametere:

EventModule – streng [obligatorisk] f.eks. cv

EventClass – streng [obligatorisk] f.eks. ansatt

HandledByIdentifier – streng [valgfritt] f.eks. my_web_service_client

HandledByTracked – boolsk [valgfritt] sporer hendelser du har sendt tidligere

HandledByStatus – opplisting (alle, behandlede, nye) [valgfritt] hva som skal vises, nye er standard

#### MONO .NET C#-EKSEMPEL

using System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "kunde";

Service.AuthHeaderValue.Username = "brukernavn";

Service.AuthHeaderValue.Password = "passord";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

Hvis du vil kompilere eksempelet over, må du laste ned WSDL-filen fra EasyCruit og kompilere den. URL til WSDL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Kommandolinjeeksempel på kompilering

wsdl EasyCruit.wsdl

mcs /target:library EasyCruit.cs r:System.Web.Services

mcs /r:EasyCruit.dll ec_soap.cs

PERL SOAP::LITE-EKSEMPEL

my $service = SOAP::Lite>service('[https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)');

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

RAW SOAP REQUEST-EKSEMPEL

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance](http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" >

<soap:Header>

<AuthHeader>

<Customer>kunde</Customer>

<Username>brukernavn</Username>

<Password>passord</Password>

</AuthHeader>

</soap:Header>

<soap:Body>

<CandidateExport>

<Language>no</Language><CandidateId>123456789</CandidateId>

</CandidateExport>

</soap:Body>

</soap:Envelope>

RAW SOAP RESPONSE-EKSEMPEL

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

< soap:Body>

< CandidateExportResponse >

< Candidate>DATA< /Candidate>

< /CandidateExportResponse>

< /soap:Body>

< /soap:Envelope>

DATA i dette eksempelet må dekodes, og den resulterende XML-filen er basert på skjemaet nedenfor:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Importere og eksportere annonsedata](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [XML annonsefeed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Integrasjon/API-er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Eksempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI5NzI5OTMxNSwtMTQwNTU5ODU3NF19
-->