# Kandidātu API metodes

## Saistītu metožu kopa

EasyCruit tīmekļa pakalpojuma interfeisu veido metožu kopa. Šīs metodes ir savstarpēji saistītas. Informāciju, ko izgūst ar vienu metodi, var izmantot kā ievades datus citai, saistītai metodei.

Pastāv metodes projektu sarakstu izgūšanai un kandidātu sarakstu izgūšanai. Tas sniedz pārskatu par pieejamiem datiem. Tad pilnai datu eksportēšanai var atlasīt konkrētu projektu vai kandidātu. Tādējādi izgūst visus ar vienumu saistītos datus. Šī visaptverošā saraksta un pilnu datu kombinācija nodrošina, ka klients var izgūt visus datus.

To vislabāk var parādīt ar piemēru. Viena no metodēm ir CandidateIdList, ar kuru klients var izgūt kandidāta ierakstu identifikatoru sarakstu. Norādot attiecīgo identifikatoru citai metodei, ko sauc par CandidateExport, pēc tam var izgūt visus par kādu kandidātu saglabātos datus.

## Pieejamās metodes

Precīzu XML formātu, ko izmanto datu ievade un izvade, var izpētīt, apskatot XML shēma failus ar referenci no WSDL faila: WSDL file - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. Parasti jums nav nepieciešams nodarboties ar šo aspektu, jo to jūsu vietā paveic jūsu izmantotie rīki.

#### Kopīgais autentifikācijas parametrs

Katra metode prasa, lai kopā ar pieprasījumu jūs nosūtat autentifikācijas datus (kas definēti SOAP HEAD). Pieprasījums netiek apstrādāts, ja autentifikācija un iesūtošās pieprasījuma autora autorizācija nav sekmīga. Autentifikācijas dati ietver klienta vārdu, lietotājvārdu un paroli. Šie dati ir tādi paši kā tie, kuri vajadzīgi, lai pieteiktos EasyCruit tīmekļa lietotnē, izmantojot pieteikšanās veidlapu. Ņemiet vērā, ka, lai piekļūtu tīmekļa pakalpojumam, jums vajag sniegt tīmekļa pakalpojuma lietotāja akreditācijas datus. Ņemiet vērā, ka parolēs nevar būt simbols £ vai €.

#### CandidateSearch

CandidateSearch sniedz kandidātu sarakstu meklēšanas parametru robežās. Saraksts ietver kandidāta ID, vārdu, otro vārdu, uzvārdu, pievienošanas datumus, izmaiņu datumu, darbā pieņemšanas datumu un statusa kategoriju (candidate, cv_candidate, cv_prospect, co-worker).

XSD faili:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parametri:

DateAddedFrom – ISO formāta datums GGGG-MM-DD

DateAddedTo – ISO formāta datums GGGG-MM-DD

DateModifiedFrom – ISO formāta datums GGGG-MM-DD

DateModifiedTo – ISO formāta datums GGGG-MM-DD

Category – virknes uzskaitījums (candidate, cv_candidate, cv_prospect, co-worker)

#### CandidateExport

Ar CandidateExport izveido virkni, kas ir rakstzīmju veidā kodēts XML dokuments. Jums vajag to dekodēt un parsēt XML. Sīkāks XML apraksts ir Candidate.xsd

XSD faili:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametri:

CandidateID – cipars [obligāti]

Language – divas rakstzīmes [nav obligāti]

#### CandidateImport

CandidateImport lasa rakstzīmju vienību kodētu XML dokumentu, kas nosūtīts virknes veidā, un pievieno to klienta CV datu bāzei.

Sīkāks XML apraksts ir Candidate.xsd

XSD faili:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametri:

Candidate – virkne (skatīt sīkāk  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)) [obligāti]

7 / 14

#### CandidateUpdate

Tas pats, kas CandidateImport, bet XML dokumentā ir vajadzīgs kandidāta ID.

XSD faili:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parametri:

Candidate – virkne (skatīt sīkāk  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)) [obligāti]

#### AddCandidateToRecruitingProject

XSD faili:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parametri:

CandidateId – cipars [obligāti]

RecruitingProjectId – cipars [obligāti]

DepartmentId – cipars [obligāti]

RecruiterId – cipars [obligāti]

#### DocumentUpload

DocumentUpload var izmantot, lai kandidāta reģistrētajiem datiem pievienotu CV vai attēlu. Fails nedrīkst būt lielāks par 2MB, CV fails var būt šādā formātā:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

Attēla faili var būt tikai šādā formātā:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD faili:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parametri:

CandidateId – cipars [obligāti]

DocumentType – virknes uzskaitījums (cv, picture) [obligāti]

DocumentName – virkne [obligāti]

Document – virkne (kodēta dokumenta MIME Base64 versija) [obligāti]

#### DocumentDownload

XSD faili:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parametri:

CandidateId – cipars [obligāti]

DocumentName – virkne [obligāti]

#### CandidateValidateUsername

CandidateValidateUsername izmanto, lai pārbaudītu, vai lietotājvārds ir pieejams un pareizi formatēts.

XSD faili:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parametri:

CandidateUsername – virkne [obligāti]

#### CVSetup

CVSetup ietver pieejamos datu laukus par konkrētu klientu, to var izmantot, lai aizpildītu

konkrētam klientam piesaistītus jautājumus.

XSD faili:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parametri:

Valoda

#### Notikumi

Izveido pārskatu par notikumiem, balstoties uz norādītājiem paramteriem.

XSD faili:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Parametri:

EventModule – virkne [obligāti], piemēram, cv

EventClass – virkne [obligāti], piemēram, pieņemts darbā

HandledByIdentifier – virkne [nav obligāti], piemēram,.my_web_service_client

HandledByTracked – loģiskais tips [nav obligāti], piemēram, izseko notikumiem, ko esat nosūtījis iepriekš.

HandledByStatus – uzskaitījums (all,processed,new) [nav obligāts] ar to, ko rādīt, pēc noklusējuma tiek rādīts jaunākais.

#### MONO .NET C# EXAMPLE

using System;

class ec_soap

{

public static void Main(string[] args)

{

EasyCruit Service = new EasyCruit();

Service.AuthHeaderValue = new AuthHeader();

Service.AuthHeaderValue.Customer = "customer";

Service.AuthHeaderValue.Username = "lietotājvārds";

Service.AuthHeaderValue.Password = "parole";

/** Candidate Export **/

MessageCandidateExport CandidateID = new MessageCandidateExport();

CandidateID.CandidateId = "123456789";

CandidateID.Language = "gb";

MessageCandidateExportResponse CandidateResponse =

Service.CandidateExport(CandidateID);

Console.WriteLine(CandidateResponse.Candidate);

}

}

Lai kompilētu iepriekšminēto piemēru, vajag lejupielādēt un kompilēt WSDL failu no EasyCruit. WSDL URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Kompilācijas piemēra komandas līnija

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

NEAPSTRĀDĀTA SOAP PIEPRASĪJUMA PIEMĒRS

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:xsd="[http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)" xmlns:xsi="[http://www.w3.org/2001/XMLSchemainstance](http://www.w3.org/2001/XMLSchemainstance)"

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" >

< soap:Header>

< AuthHeader>

< Customer>klients< /Customer>

< Username>lietotājvārds< /Username>

< Password>parole< /Password>

< /AuthHeader>

< /soap:Header>

< soap:Body>

< CandidateExport>

< Language>no< /Language>< CandidateId>123456789< /CandidateId>

< /CandidateExport>

< /soap:Body>

< /soap:Envelope>

NEAPSTRĀDĀTAS SOAP ATBILDES PIEMĒRS

<?xml version="1.0" encoding="UTF8"?>

<soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

< soap:Body>

< CandidateExportResponse >

< Candidate>DATI< /Candidate>

< /CandidateExportResponse>

< /soap:Body>

< /soap:Envelope>

Ši piemēra DATI ir jāatkodē un iegūtais XML ir balstīts uz zemāk norādīto shēmu:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

##### Skatīt arī:

![](../Resources/Images/icon-document-link.png)  [Vakanču datu imports un eksports](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Vakanču XML plūsma](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – integrācija/API](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Tīmekļa pakalpojuma atbildes piemērs](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – pārskati](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5MTAxNDM0Nl19
-->