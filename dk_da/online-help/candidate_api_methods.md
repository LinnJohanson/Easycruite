# Kandidat-API-metoder

## Et sammenhængende sæt metoder

EasyCruits internetservicegrænseflade består af et sæt navngivne metoder. Disse metoder er sammenhængende. Det gøres på en sådan måde, at de oplysninger, der indhentes ved at anvende en af metoderne, kan anvendes som input til en anden relateret metode.

Der er metoder til at indhente projekter og kandidatlister. Dette giver et overblik over de tilgængelige data. Derefter kan der vælges et særligt projekt eller en kandidat til en fuld eksport. Denne henter alle de data, der er forbundet med punktet. Denne kombination af en omfattende liste og alle oplysninger sikrer, at en kunde kan hente alle sine data.

Dette belyses bedst i form af et eksempel: Der er en metode, der hedder CandidateIdList, med hvilken en kunde kan hente en liste over kandidatregisteridentifikatorer. Alle de data, der er gemt for en bestemt kandidat, kan efterfølgende hentes ved at tilføje den tilsvarende identifikator til en anden metode, der hedder CandidateExport.

## Tilgængelige metoder

Det præcise XML-format til input og output kan udforskes ved at undersøge XML-skemafilerne, der er henvist til fra WSDL-filen: WSDL-fil - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Under normale omstændigheder bør du ikke skulle håndtere dette aspekt selv, da dine værktøjer bør klare den del af arbejdet.

#### Almindeligt godkendelsesparameter

Hver eneste metode kræver, at se sender godkendelsesdata (defineret i SOAP, HEAD) sammen med din specifikke anmodning. Ingen anmodning håndteres uden succesfuld autentificering og godkendelse af forfatteren til den indkomne anmodning. Disse autentificeringsdata består af kundenavn, brugernavn og adgangskode. Dette er præcis den samme type data, som kræves ved login på EasyCruits internetapplikation via login-formularen. Bemærk dog, at for at få adgang til internetservicen, skal du oplyse brugeroplysninger på en bruger af internetservicen. Bemærk, at adgangskoder ikke må indeholde £ eller €.

#### CandidateSearch

CandidateSearch viser dig en liste over kandidater inden for de anførte søgeparametre. Listen indeholder en kandidats id, fornavn, mellemnavn, efternavn, dato for tilføjelse, dato for ændring, dato for ansættelse og hvilken kategori (kandidat, CV-kandidat, CV-kandidatemne, medarbejder) vedkommende er placeret i.

XSD-filer:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parametre:

DateAddedFrom – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateAddedTo – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateModifiedFrom – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateModifiedTo – ISO-formateret dato date ÅÅÅÅ-MM-DD

Kategori – strengopregning (kandidat, CV-kandidat, CV-kandidatemne, Medarbejder)

#### CandidateExport

CandidateExport viser en streng, der er et karakterhelhedskodet XML-dokument. Du skal afkode dette og fortolke XML Yderligere beskrivelse af XML findes i Candidate.xsd

XSD-filer:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

CandidateId – heltal [required]

Sprog – to-tegns-ISO [optional]

#### CandidateImport

CandidateImport læser et tegnhelhedskodet XML-dokument, der sendes som en streng og tilføjer det til kunde-CV-puljen.

Yderligere beskrivelse af XML findes i Candidate.xsd

XSD-filer:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

Kandidat – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for oplysninger) [required]

7 / 14

#### CandidateUpdate

Samme som CandidateImport, men kandidatens id er påkrævet i XML-dokumentet.

XSD-filer:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

Kandidat – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for oplysninger) [required]

#### AddCandidateToRecruitingProject

XSD-filer:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parametre:

CandidateId – heltal [required]

RecruitingProjectId – heltal [required]

DepartmentId – heltal [required]

RecruiterId – heltal [optional]

#### DocumentUpload

DocumentUpload kan anvendes til at fastgøre et CV eller et billede til et kandidatregister. Filen må ikke være større end 2 MB og en fil af typen CV må kun være i følgende format:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Filer af typen Billede kan kun være i følgende format:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD-filer:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parametre:

CandidateId – heltal [required]

DocumentType – strengopregning (cv, billede) [required]

DocumentName – streng [required]

Document – streng (MIME Base64 kodet version af dokumentet) [required]

#### DocumentDownload

XSD-filer:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parametre:

CandidateId – heltal [required]

DocumentName – streng [required]

#### CandidateValidateUsername

CandidateValidateUsername bruges til at kontrollere, om et brugernavn er tilgængeligt oog korrekt formatteret.

XSD-filer:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parametre:

CandidateUsername – streng [required]

#### CVSetup

CVSetup viser de tilgængelige datafelter for den angivne kunde. Dette kan anvendes til at udfylde

kundespecifikke spørgsmål

XSD-filer:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parametre:

Sprog

#### Hændelser

Hændelser viser tilgængelige hændelser med udgangspunkt i de angivne parametre.

XSD-filer:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parametre:

EventModule – streng [required] f.eks. CV

EventClass – streng [required] f.eks. ansat

HandledByIdentifier – streng [optional] f.eks. my_web_service_client

HandledByTracked – boolesk [optional] holder styr på de hændelser, du tidligere har sendt.

HandledByStatus – opregning (alle,bearbejdet,ny) [optional] af, hvad der skal vises to display, standard er nye.

#### MONO .NET C# EXAMPLE

anvender System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "customer";

Service.AuthHeaderValue.Username = "username";

Service.AuthHeaderValue.Password = "password";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

For at kompilere ovenstående eksempel, skal du hente WSDL-filen fra EasyCruit og kompilere den.WSDL URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Kommandolinjeeksempel på kompilering

wsdl EasyCruit.wsdl

mcs /target:library EasyCruit.cs r:System.Web.Services

mcs /r:EasyCruit.dll ec_soap.cs

PERL SOAP::LITE EXAMPLE

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

RAW SOAP REQUEST EXAMPLE

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance](http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" >

< soap:Header>

< AuthHeader>

<  Customer>customer< /Customer>

< Username>username< /Username>

< Password>password< /Password>

< /AuthHeader>

< /soap:Header>

< soap:Body>

< CandidateExport>

< Language>no< /Language>< CandidateId>123456789< /CandidateId>

< /CandidateExport>

< /soap:Body>

< /soap:Envelope>

RAW SOAP RESPONSE EXAMPLE

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

< soap:Body>

< CandidateExportResponse >

< Candidate>DATA</Candidate>

< /CandidateExportResponse>

< /soap:Body>

< /soap:Envelope>

DATA til dette eksempel skal afkodes, og den resulterende XML er baseret på skemaet nedenfor:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Se også:

![](../Resources/Images/icon-document-link.png)  [Import og eksport af rekrutteringsprojektdata](import_and_export_of_vacancy_data.htm)

![](../Resources/Images/icon-document-link.png)  [Rekrutteringsprojekt XML-feed](vacancy_xml_feed.htm)

![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Integration/API’er](guide_for_administrators_integration_apis.htm)

![](../Resources/Images/icon-document-link.png)  [Eksempel på internetservicesvar](example_web_service_response.htm)

![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Rapporter](guide_for_administrators_reports.htm)# Kandidat-API-metoder

## Et sammenhængende sæt metoder

EasyCruits internetservicegrænseflade består af et sæt navngivne metoder. Disse metoder er sammenhængende. Det gøres på en sådan måde, at de oplysninger, der indhentes ved at anvende en af metoderne, kan anvendes som input til en anden relateret metode.

Der er metoder til at indhente projekter og kandidatlister. Dette giver et overblik over de tilgængelige data. Derefter kan der vælges et særligt projekt eller en kandidat til en fuld eksport. Denne henter alle de data, der er forbundet med punktet. Denne kombination af en omfattende liste og alle oplysninger sikrer, at en kunde kan hente alle sine data.

Dette belyses bedst i form af et eksempel: Der er en metode, der hedder CandidateIdList, med hvilken en kunde kan hente en liste over kandidatregisteridentifikatorer. Alle de data, der er gemt for en bestemt kandidat, kan efterfølgende hentes ved at tilføje den tilsvarende identifikator til en anden metode, der hedder CandidateExport.

## Tilgængelige metoder

Det præcise XML-format til input og output kan udforskes ved at undersøge XML-skemafilerne, der er henvist til fra WSDL-filen: WSDL-fil - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Under normale omstændigheder bør du ikke skulle håndtere dette aspekt selv, da dine værktøjer bør klare den del af arbejdet.

#### Almindeligt godkendelsesparameter

Hver eneste metode kræver, at se sender godkendelsesdata (defineret i SOAP, HEAD) sammen med din specifikke anmodning. Ingen anmodning håndteres uden succesfuld autentificering og godkendelse af forfatteren til den indkomne anmodning. Disse autentificeringsdata består af kundenavn, brugernavn og adgangskode. Dette er præcis den samme type data, som kræves ved login på EasyCruits internetapplikation via login-formularen. Bemærk dog, at for at få adgang til internetservicen, skal du oplyse brugeroplysninger på en bruger af internetservicen. Bemærk, at adgangskoder ikke må indeholde £ eller €.

#### CandidateSearch

CandidateSearch viser dig en liste over kandidater inden for de anførte søgeparametre. Listen indeholder en kandidats id, fornavn, mellemnavn, efternavn, dato for tilføjelse, dato for ændring, dato for ansættelse og hvilken kategori (kandidat, CV-kandidat, CV-kandidatemne, medarbejder) vedkommende er placeret i.

XSD-filer:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parametre:

DateAddedFrom – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateAddedTo – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateModifiedFrom – ISO-formateret dato date ÅÅÅÅ-MM-DD

DateModifiedTo – ISO-formateret dato date ÅÅÅÅ-MM-DD

Kategori – strengopregning (kandidat, CV-kandidat, CV-kandidatemne, Medarbejder)

#### CandidateExport

CandidateExport viser en streng, der er et karakterhelhedskodet XML-dokument. Du skal afkode dette og fortolke XML Yderligere beskrivelse af XML findes i Candidate.xsd

XSD-filer:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

CandidateId – heltal [required]

Sprog – to-tegns-ISO [optional]

#### CandidateImport

CandidateImport læser et tegnhelhedskodet XML-dokument, der sendes som en streng og tilføjer det til kunde-CV-puljen.

Yderligere beskrivelse af XML findes i Candidate.xsd

XSD-filer:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

Kandidat – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for oplysninger) [required]

7 / 14

#### CandidateUpdate

Samme som CandidateImport, men kandidatens id er påkrævet i XML-dokumentet.

XSD-filer:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametre:

Kandidat – streng (se  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for oplysninger) [required]

#### AddCandidateToRecruitingProject

XSD-filer:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parametre:

CandidateId – heltal [required]

RecruitingProjectId – heltal [required]

DepartmentId – heltal [required]

RecruiterId – heltal [optional]

#### DocumentUpload

DocumentUpload kan anvendes til at fastgøre et CV eller et billede til et kandidatregister. Filen må ikke være større end 2 MB og en fil af typen CV må kun være i følgende format:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Filer af typen Billede kan kun være i følgende format:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD-filer:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parametre:

CandidateId – heltal [required]

DocumentType – strengopregning (cv, billede) [required]

DocumentName – streng [required]

Document – streng (MIME Base64 kodet version af dokumentet) [required]

#### DocumentDownload

XSD-filer:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parametre:

CandidateId – heltal [required]

DocumentName – streng [required]

#### CandidateValidateUsername

CandidateValidateUsername bruges til at kontrollere, om et brugernavn er tilgængeligt oog korrekt formatteret.

XSD-filer:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parametre:

CandidateUsername – streng [required]

#### CVSetup

CVSetup viser de tilgængelige datafelter for den angivne kunde. Dette kan anvendes til at udfylde

kundespecifikke spørgsmål

XSD-filer:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parametre:

Sprog

#### Hændelser

Hændelser viser tilgængelige hændelser med udgangspunkt i de angivne parametre.

XSD-filer:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parametre:

EventModule – streng [required] f.eks. CV

EventClass – streng [required] f.eks. ansat

HandledByIdentifier – streng [optional] f.eks. my_web_service_client

HandledByTracked – boolesk [optional] holder styr på de hændelser, du tidligere har sendt.

HandledByStatus – opregning (alle,bearbejdet,ny) [optional] af, hvad der skal vises to display, standard er nye.

#### MONO .NET C# EXAMPLE

anvender System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "customer";

Service.AuthHeaderValue.Username = "username";

Service.AuthHeaderValue.Password = "password";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

For at kompilere ovenstående eksempel, skal du hente WSDL-filen fra EasyCruit og kompilere den.WSDL URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Kommandolinjeeksempel på kompilering

wsdl EasyCruit.wsdl

mcs /target:library EasyCruit.cs r:System.Web.Services

mcs /r:EasyCruit.dll ec_soap.cs

PERL SOAP::LITE EXAMPLE

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

RAW SOAP REQUEST EXAMPLE

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance](http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" >

<soap:Header>

<AuthHeader>

<Customer>customer</Customer>

<Username>username</Username>

<Password>password</Password>

</AuthHeader>

</soap:Header>

<soap:Body>

<CandidateExport>

<Language>no</Language><CandidateId>123456789</CandidateId>

</CandidateExport>

</soap:Body>

</soap:Envelope>

RAW SOAP RESPONSE EXAMPLE

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

<soap:Body>

<CandidateExportResponse >

<Candidate>DATA</Candidate>

</CandidateExportResponse>

</soap:Body>

</soap:Envelope>

DATA til dette eksempel skal afkodes, og den resulterende XML er baseret på skemaet nedenfor:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Se også:

![](../Resources/Images/icon-document-link.png)  [Import og eksport af rekrutteringsprojektdata](import_and_export_of_vacancy_data.htm)

![](../Resources/Images/icon-document-link.png)  [Rekrutteringsprojekt XML-feed](vacancy_xml_feed.htm)

![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Integration/API’er](guide_for_administrators_integration_apis.htm)

![](../Resources/Images/icon-document-link.png)  [Eksempel på internetservicesvar](example_web_service_response.htm)

![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Rapporter](guide_for_administrators_reports.htm)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI1NTkwNTgwMF19
-->