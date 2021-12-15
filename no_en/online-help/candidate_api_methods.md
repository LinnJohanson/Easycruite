# Candidate API Methods

## An Interrelated Set of Methods

The EasyCruit web service interface consists of a set of named methods. These methods are interrelated. This is done in such a way that the information retrieved by invoking one method may be used as input to another, related method.

There are methods to retrieve lists of projects and lists of candidates. This provides an overview over the data available. A particular project or candidate can then be selected for a full export. This retrieves all of the data associated with the item. This combination of comprehensive list and full detail ensures a customer can retrieve all of their data.

This is best made clear giving an example. There is one method called CandidateIdList, invoking which a customer may retrieve a list of candidate record identifiers. All of the data stored for a given candidate may then be retrieved by supplying the corresponding identifier to another method, called CandidateExport.

## Methods Available

The exact XML format for input and output can be explored by studying the XML Schema files referenced from the WSDL file: WSDL file - https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl. You should not normally need to deal with this aspect yourself, though, as your tools should do that part of the job.

#### Common Authentication Parameter

Each and every method requires you to send authentication data ( defined in the SOAP HEAD) along with your specific request. No request is handled without successful authentication and authorization of the incoming request's author. This authentication data consists of customer name, user name and password. This is exactly the same kind of data that is required when logging in to the EasyCruit web application via the login form. Note, however, that in order to access the web service you need to supply the credentials of a web service user. Note that passwords cannot contain £ or €.

#### CandidateSearch

CandidateSearch provides you with a list of candidates within the search parameters supplied. The list contains a candidate's ID, given name, middle name, family name, date addded, date modified, date hired and which category (candidate, cv_candidate, cv_prospect, co-worker) he/she are placed in.

XSD files:

CandidateSearchRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...rchRequest.xsd)

CandidateSearchResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...chResponse.xsd)

Parameters:

DateAddedFrom – ISO formated date YYYY-MM-DD

DateAddedTo – ISO formated date YYYY-MM-DD

DateModifiedFrom – ISO formated date YYYY-MM-DD

DateModifiedTo – ISO formated date YYYY-MM-DD

Category – String enumeration (candidate, cv_candidate, cv_prospect, co-worker)

#### CandidateExport

CandidateExport returns a string that is a character entity encoded XML document. You would need to decode this and parse the XML. Further description of the XML are in Candidate.xsd

XSD files:

CandidateExportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateExportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

CandidateID – integer [required]

Language – two character iso [optional]

#### CandidateImport

CandidateImport reads a character entity encoded XML document sent as a string, and adds it to the customer CV-Pool.

Further description of the XML are in Candidate.xsd

XSD files:

CandidateImportRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ortRequest.xsd)

CandidateImportResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...rtResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

Candidate – string (see  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for details) [required]

7 / 14

#### CandidateUpdate

Same as CandidateImport, but the candidate's ID are required in the XML document.

XSD files:

CandidateUpdateRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ateRequest.xsd)

CandidateUpdateResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...teResponse.xsd)

Candidate.xsd –  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

Parameters:

Candidate – string (see  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)  for details) [required]

#### AddCandidateToRecruitingProject

XSD files:

AddCandidateToRecruitingProjectRequest –

[https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd](https://www.easycruit.com/wsdl/ws/Ad...ectRequest.xsd)

AddCandidateToRecruitingProjectResponse –

[https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd](https://www.easycruit.com/wsdl/ws/Ad...ctResponse.xsd)

Parameters:

CandidateId – integer [required]

RecruitingProjectId – integer [required]

DepartmentId – integer [required]

RecruiterId – integer [optional]

#### DocumentUpload

DocumentUpload could be used to attach a CV or picture to a candidate record. The file can not be larger then 2MB, and a file of type CV could only in following format:

doc, pdf, ppt, rtf, sxw, sdw, txt, text, wpd, xls, lwp, WKS, WK1, WK3, WK4, docx, xlsx, pptx, jpg, jpeg, png, tif, tiff, gif, bmp

File of type Picture could only be in following format:

jpg, jpeg, png, tif, tiff, gif, bmp

XSD files:

DocumentUploadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentUplaodResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

Parameters:

CandidateId – integer [required]

DocumentType – string enumeration (cv, picture) [required]

DocumentName – string [required]

Document – string (MIME Base64 encoded version of the document) [required]

#### DocumentDownload

XSD files:

DocumentDownloadRequest.xsd –  [https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd](https://www.easycruit.com/wsdl/ws/Do...oadRequest.xsd)

DocumentDownloadResponse.xsd –  [https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd](https://www.easycruit.com/wsdl/ws/Do...adResponse.xsd)

Parameters:

CandidateId – integer [required]

DocumentName – string [required]

#### CandidateValidateUsername

CandidateValidateUsername are used to check if a username are available and properly formatted.

XSD files:

CandidateValidateUsernameRequest.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd](https://www.easycruit.com/wsdl/ws/Ca...ameRequest.xsd)

CandidateValidateUsernameResponse.xsd –

[https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd](https://www.easycruit.com/wsdl/ws/Ca...meResponse.xsd)

Parameters:

CandidateUsername – string [required]

#### CVSetup

CVSetup returns the available data fields for the specified customer, this could be used to populate

customer specific questions.

XSD files:

CVSetupRequest.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd](https://www.easycruit.com/wsdl/ws/CVSetupRequest.xsd)

CVSetupResponse.xsd –  [https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd](https://www.easycruit.com/wsdl/ws/CVSetupResponse.xsd)

Parameters:

Language

#### Events

Events returns available events based on the specified paramaters.

XSD files:

EventsRequest.xsd –  [https://www.easycruit.com/wsdl/ws/EventsRequest.xsd](https://www.easycruit.com/wsdl/ws/EventsRequest.xsd)

EventsResponse.xsd –  [https://www.easycruit.com/wsdl/ws/EventsResponse.xsd](https://www.easycruit.com/wsdl/ws/EventsResponse.xsd)

Paramaters:

EventModule – string [required] e.g. cv

EventClass – string [required] e.g. hired

HandledByIdentifier – string [optional] e.g. my_web_service_client

HandledByTracked – boolean [optional] keeps track of events you have sent earlier.

HandledByStatus – enumeration(all,processed,new) [optional] what to display, default are new.

#### MONO .NET C# EXAMPLE

using System;

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

To compile the above example you need to download the WSDL file from EasyCruit and compile it.WSDL URL:  [https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl](https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl)

Command line example of compilation

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

xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns="urn:EasyCruit">

< soap:Header>

< AuthHeader>

< Customer>customer< /Customer>

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

< ?xml version="1.0" encoding="UTF8"?>

< soap:Envelope xmlns:soap="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)">

< soap:Body>

< CandidateExportResponse xmlns="urn:EasyCruit">

< Candidate>DATA< /Candidate>

< /CandidateExportResponse>

< /soap:Body>

< /soap:Envelope>

The DATA for this example needs to be decoded, and the resulting XML is based on schema below:  [https://www.easycruit.com/wsdl/ws/Candidate.xsd](https://www.easycruit.com/wsdl/ws/Candidate.xsd)

##### See also:

![](../Resources/Images/icon-document-link.png) [Import and Export of Vacancy Data](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png) [Vacancy XML Feed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Integration/APIs](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png) [Example Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Reports](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMzgzNDM2OTRdfQ==
-->