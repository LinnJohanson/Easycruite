# Kandidat-API-metoder

## En uppsättning metoder som samverkar

EasyCruits webbtjänstgränssnittet består av en uppsättning namngivna metoder. Dessa metoder samverkar. Detta görs på ett sådant sätt att informationen som hämtas genom att anropa en metod kan användas som inmatning till en annan relaterad metod.

Det finns metoder för att hämta projektlistor och kandidatlistor. Detta ger en översikt över tillgängliga uppgifter. Ett visst projekt eller en kandidat kan sedan väljas för en fullständig export. Denna hämtar alla uppgifter som är kopplade till objektet. Denna kombination av omfattande lista och fullständig information gör att en kund kan hämta alla sina uppgifter.

Detta förklaras bäst genom ett exempel. Det finns en metod som kallas CandidateIdList, med vilken en kund kan hämta en lista över kandidatpostidentifierare. All data som lagras för en given kandidat kan sedan hämtas genom att tillhandahålla motsvarande identifierare till en annan metod som kallas CandidateExport.

## Tillgängliga metoder

Det exakta XML-formatet för indata och utdata kan utforskas genom att granska XML-schemafiler. Som referens kan du använda WSDL-filen: WSDL-fil - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Du ska i normala fall inte behöva hantera denna aspekt själv, eftersom dina verktyg bör ta hand om den delen av jobbet.

#### Gemensam autentiseringsparameter

Varje metod kräver att du skickar autentiseringsuppgifter (definierade i SOAP HEAD) tillsammans med din specifika begäran. Ingen förfrågan hanteras om inte autentiseringen och den inkommande förfrågans författare godkänns. Dessa autentiseringsuppgifter består av kundnamn, användarnamn och lösenord. Det här är exakt samma typ av uppgifter som krävs när du loggar in på EasyCruits webbapplikation via inloggningsformuläret. Observera dock att för att få tillgång till webbtjänsten måste du tillhandahålla användaruppgifterna för en webbtjänstanvändare. Observera att lösenord inte kan innehålla £ eller €.

#### CandidateSearch

CandidateSearch ger dig en lista på kandidater inom de angivna sökparametrarna. Listan innehåller en kandidats ID, förnamn, mellannamn, efternamn, registreringsdatum, uppdateringsdatum, anställningsdatum och i vilken kategori (candidate, cv_candidate, cv_prospect, co-worker) han/hon placerats i.

XSD-filer:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateSearchResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parametrar:

DateAddedFrom – ISO-formaterat datum ÅÅÅÅ-MM-DD

DateAddedTo – ISO-formaterat datum ÅÅÅÅ-MM-DD

DateModifiedFrom – ISO-formaterat datum ÅÅÅÅ-MM-DD

DateModifiedTo – ISO-formaterat datum ÅÅÅÅ-MM-DD

Category – Sträng enumeration (candidate, cv_candidate, cv_prospect, co-worker)

#### CandidateExport

CandidateExport returnerar en sträng som är ett teckenenhetskodat XML-dokument. Du måste avkoda detta och översätta XML-dokumentet. Ytterligare beskrivning av XML finns i Candidate.xsd

XSD-filer:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametrar:

CandidateID – heltal [krävs]

Language – två tecken enligt ISO-standard [valfritt]

#### CandidateImport

CandidateImport läser ett teckenenhetskodat XML-dokument som skickas som en sträng och lägger till det i kundens CV-pool.

Ytterligare beskrivning av XML finns i Candidate.xsd

XSD-filer:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateImportRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateImportResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametrar:

Candidate – sträng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  för detaljer) [krävs]

7/14

#### CandidateUpdate

Samma som CandidateImport, men kandidaternas ID krävs i XML-dokumentet.

XSD-filer:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateUpdateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CandidateUpdateResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametrar:

Candidate – sträng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  för detaljer) [krävs]

#### AddCandidateToRecruitingProject

XSD-filer:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/AddCandidateToRecruitingProjectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/AddCandidateToRecruitingProjectResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parametrar:

CandidateId – heltal [krävs]

RecruitingProjectId – heltal [krävs]

DepartmentId – heltal [krävs]

RecruiterId – heltal [valfritt]

#### DocumentUpload

DocumentUpload kan användas för att knyta ett CV eller en bild till en kandidatpost. Filen får inte vara större än 2 MB och en fil med typ CV kan endast vara i följande format:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Fil av typ Bild får bara vara i följande format:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD-filer:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentUploadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentUplaodResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parametrar:

CandidateId – heltal [krävs]

DocumentType – Sträng enumeration (cv, bild) [krävs]

DocumentName – sträng [krävs]

Document – sträng (MIME Base64 kodad version av dokumentet) [krävs]

#### DocumentDownload

XSD-filer:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentDownloadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/DocumentDownloadResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parametrar:

CandidateId – heltal [krävs]

DocumentName – sträng [krävs]

#### CandidateValidateUsername

CandidateValidateUsername används för att kontrollera om ett användarnamn är tillgängligt och korrekt formaterat.

XSD-filer:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/CandidateValidateUsernameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/CandidateValidateUsernameResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parametrar:

CandidateUsername – sträng [krävs]

#### CVSetup

CVSetup returnerar tillgängliga datafält för den angivna kunden, detta kan användas för att fylla i

kundspecifika frågor.

XSD-filer:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parametrar:

Language

#### Events

Events returnerar tillgängliga händelser baserat på de specificerade parametrarna.

XSD-filer:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parametrar:

EventModule – sträng [krävs] t.ex. cv

EventClass – sträng [krävs] t.ex. anställd

HandledByIdentifier – sträng [valfri] t.ex. my_web_service_client

HandledByTracked – boolean [valfri] håller reda på händelser som du har skickat tidigare.

HandledByStatus – enumeration(all,processed,new) [valfritt] vad som ska visas, standard är ny.

#### MONO .NET C# EXEMPEL

using System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "kund";

Service.AuthHeaderValue.Username = "användarnamn";

Service.AuthHeaderValue.Password = "lösenord";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

För att kompilera ovanstående exempel måste du ladda ned WSDL-filen från EasyCruit och kompilera den. WSDL URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Kommandoradsexempel för kompilering

wsdl EasyCruit.wsdl

mcs /target:library EasyCruit.cs r:System.Web.Services

mcs /r:EasyCruit.dll ec_soap.cs

PERL SOAP::LITE EXEMPEL

my $service = SOAP::Lite>service('[https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)');

my $candidate = $service>CandidateExport(SOAP::Data>name('ec:CandidateId',123456789),SOAP::Data>name('ec:Language','gb'),

SOAP::Header>name(

AuthHeader => [

SOAP::Data>name('Kund', 'kund'),

SOAP::Data>name('Användarnamn', 'användarnamn'),

SOAP::Data>name('Lösenord', 'lösenord')

]

)

);

print ($candidate gt '' ? $candidate : 'Kunde inte hämta data..');

RAW SOAP REQUEST EXEMPEL

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance](http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" >

<soap:Header>

<AuthHeader>

<Customer>kund</Customer>

<Username>användarnamn</Username>

<Password>lösenord</Password>

</AuthHeader>

</soap:Header>

<soap:Body>

<CandidateExport>

<Language>sv</Language><CandidateId>123456789</CandidateId>

</CandidateExport>

</soap:Body>

</soap:Envelope>

RAW SOAP RESPONSE EXEMPEL

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

<soap:Body>

<CandidateExportResponse >

<Candidate>DATA</Candidate>

</CandidateExportResponse>

</soap:Body>

</soap:Envelope>

DATA i detta exempel måste avkodas och det resulterande XML är baserat på nedanstående schema:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

##### Se även:

![](../Resources/Images/icon-document-link.png)  [Import och export av annonsdata](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Annons XML-flöde](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer – Integration/API:er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Exempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer - Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MzIyNzE3MDNdfQ==
-->