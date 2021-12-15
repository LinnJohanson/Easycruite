# Import and Export of Vacancy Data

## Overview

This article describes the following three web service methods found in the WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyList  - Exports a list of available vacancies from EasyCruit.
-   VacancyExport  - Exports the vacancy data from EasyCruit.
-   VacancyImport  - Imports vacancy data into EasyCruit.

## Enabling Web service access

Access to EasyCruit Web Service requires a valid EasyCruit account. Authentication is done on each request against the web service by providing a valid customer identifier, username and password in the SOAP header of the request. Note that passwords cannot contain £ or €.

In addition, access to the individual web service methods is controlled by a set of configuration options inside EasyCruit for both the customer as a whole and for each individual user entity. This is done to achieve maximum control on who is allowed to access which data through EasyCruit Web Services. To get access to any of the web service methods both Customer and User needs to be configured with the necessary privileges in EasyCruit. This can be done by sending a request to EasyCruit Customer Success Team, specifying which web services methods are needed and which users who should have access to which method.

Inside EasyCruit in both the Customers and Users setup, the export/import web services are referred to as:

-   Access to export ofVacancyList (VacancyList)
-   Access to export of Vacancy description data (VacancyExport)
-   Access to import of Vacancy description data (VacancyImport)

## Export of vacancy list

To retrieve a list of vacancies that a given user has access to in EasyCruit you need to make a SOAP call to the EasyCruit Web Service method called “VacancyList”, using that particular users login credentials.

VacancyList can take two optional parameters: language and department. These parameters can be used to filter the exported list on a the given language and/or department. If no parameters are specified then a complete list of vacancies will be returned. The exported list can be used for additional calls to the same method to narrow down the selection, or as input to further calls against the VacancyExport method.

The resulting list will contain one Vacancy element for each available vacancy. The “id” parameter on each vacancy is the internal project id in EasyCruit. Each Vacancy will contain:

-   a Title element which is the project title in EasyCruit.
-   a RefId element which is the customers external reference (this may be empty).
-   a list of Departments the vacancy belongs with department id's and names.
-   a list of Languages the vacancy is available in.

### XML Schema definitions

XML Schema for VacancyList request:  [https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML Schema for VacancyList response:  [https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML Examples

#### VacancyList SOAP request example

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

#### VacancyList SOAP response example

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

## Export of vacancy data

To export vacancy data from EasyCruit you need to make a SOAP call to the EasyCruit Web Service “VacancyExport”. This method takes four optional parameters: id (project id for the vacancy in EasyCruit), language, department id and allowXMLTags.

If you don't specify a vacancy id then all vacancies that a given user has access to will be returned. It's therefore advisable that you first use the VacancyList web service as a filter to reduce the amount of data exported. Any given vacancy can exist in one or more languages (which languages are available can vary between vacancies). To retrieve a vacancy in the Norwegian language specify “nb” in the language parameter. To retrieve all vacancies for a given customer department you will need to specify the department id in the department parameter (department id's and vacancy id's can be retrieved from the VacancyList web service). AllowXMLTags specifies if we should return the vacancy text as raw data or if we should remove HTML tags etc. from the text before exporting.

The resulting list will contain one Vacancy element for each exported vacancy. The “id” parameter on each vacancy is the internal project id in EasyCruit and the language parameter specifies the language the vacancy was published in. Each Vacancy will contain the following elements:

-   ProjectTitle which is the title of the project inside EasyCruit.
-   RefId which is the customers external reference id.

Vacancy id, vacancy language, ProjectTitle and RefId is for internal reference and not meant for publishing:

Elements for used publishing are:

-   TitleHeading: The header above the vacancy Title.
-   Title: The vacancy title.
-   CompanyName: The name of company as it is displayed in the vacancy.
-   Body: The vacancy text (either raw data or stripped for HTML entities, dependent on the allow MLTags parameter).
-   Deadline: The date (not necessarily a date/time value) which is the deadline for applying to the vacancy.
-   Engagement: Date (not necessarily a date/time value) the company wants to hire.
-   Location: Geographical location of the job/position.
-   CompanyInformation: The company element has three sub-elements; Department,About and Homepage. This is the name, description and homepage of the hiring Customer Department. If the position is for more than one department this information will be repeated for each individual department.
-   Contacts: List of contacts that are included in the vacancy and which departments they belong to.

### XML Schema definitions

XML Schema for VacancyExport request:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML Schema for VacancyExport response:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML Examples

#### VacancyExport SOAP request example

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

## VacancyExport SOAP response example

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

<TelephoneOffice>?</TelephoneOffice>

<TelephoneMobile>?</TelephoneMobile>

<Department id="?">?</Department>

</Contact>

</Contacts>

<Questions>?</Questions>

<CompanyInformation>

<!--Zero or more repetitions:-->

<Company>

<!--You may enter the following 3 items in any order-->

<Department>?</Department>

<About>?</About>

<Homepage>?</Homepage>

</Company>

</CompanyInformation>

</Vacancy>

</VacancyList>

</urn:VacancyExportResponse>

</soapenv:Body>

</soapenv:Envelope>

.NET C# example:

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

## Import of vacancy data

To import vacancy data from EasyCruit you need to make a SOAP call to the EasyCruit Web Service “VacancyImport”.

The following data can be imported:

-   Title: Vacancy title.
-   TitleHeading: Heading above vacancy title.
-   Body: Vacancy text.
-   Deadline: Date the applicant must apply by.
-   Engagement: Time of hiring.
-   Location: Geographical location of job/position.

There are two obligatory parameters that has to be specified:

-   The Language parameter on the Version element specifies what language the vacancy is in.
-   The RefId parameter on the Vacancy element parameter is the customers internalreference to the vacancy.

The imported data will become available and selectable from a drop-down menu inside EasyCruit when a user initiates a new vacancy project.

### XML Schema definitions

XML Schema for VacancyExport request:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML Schema for VacancyExport response:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML Examples

#### VacancyImport SOAP request example

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header>

<urn:AuthHeader>

<Customer>?</Customer>

<Username>?</Username>

<Password passwordEncoding="?">

<passwordString>?</passwordString>

< /Password>

<!--Optional:-->

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

#### VacancyImport SOAP response example

< soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/] (http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

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

##### See also:

![](../Resources/Images/icon-document-link.png) [Candidate API Methods](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png) [Vacancy XML Feed](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Integration/APIs](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png) [Example Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Reports](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzIyMTIxMDA5XX0=
-->