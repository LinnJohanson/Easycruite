# Import och export av annonsdata

## Översikt

I den här artikeln beskrivs följande tre webbtjänstmetoder som finns i WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyList  – Exporterar en lista på tillgängliga annonser från EasyCruit.
-   VacancyExport  – Exporterar annonsdata från EasyCruit.
-   VacancyImport  – Importerar annonsdata till EasyCruit.

## Aktivera åtkomst till Web Service

Tillgång till EasyCruit Web Service kräver ett giltigt EasyCruit-konto. Autentisering görs vid varje begäran mot webbtjänsten genom att tillhandahålla en giltig kundidentifierare, användarnamn och lösenord i SOAP-rubriken för begäran. Observera att lösenord inte kan innehålla £ eller €.

Dessutom styrs åtkomsten till de enskilda webbtjänstmetoderna med en uppsättning konfigureringsalternativ inom EasyCruit för både kunden som helhet och för varje enskild användarenhet. Detta görs för att uppnå maximal kontroll över vem som får komma åt vilka uppgifter genom EasyCruit Web Services. För att få åtkomst till någon av webbtjänstmetoderna måste både kunder och användare konfigureras med nödvändiga behörigheter i EasyCruit. Detta kan göras genom att skicka en förfrågan till teamet EasyCruit Customer Success och specificera vilka webbtjänstemetoder som behövs och vilka användare som ska ha åtkomst till vilken metod.

I EasyCruit i både kund- och användarinställningarna, kallas webbtjänsterna export/import för:

-   Tillgång till export av annonsöversikt (VacancyList)
-   Tillgång till export av annonsdata (VacancyExport)
-   Tillgång till import av annonsdata (VacancyImport)

## Export av annonsöversikt

För att hämta en lista över annonser som en viss användare har tillgång till i EasyCruit måste du göra ett SOAP-anrop till EasyCruit Web Service-metoden ”VacancyList”, med den specifika användarens inloggningsuppgifter.

VacancyList kan ta emot två valfria parametrar: språk och avdelning. Dessa parametrar kan användas för att filtrera den exporterade listan på ett givet språk och/eller avdelning. Om inga parametrar anges kommer en fullständig lista på annonser att returneras. Den exporterade listan kan användas för ytterligare anrop till samma metod för att begränsa urvalet eller som indata för vidare anrop mot metoden VacancyExport.

Den resulterande listan innehåller ett annonselement för varje tillgänglig annons. ”ID”-parametern för varje annons är det interna projekt-id:t i EasyCruit. Varje annons kommer att innehålla:

-   ett titel-element som är projekttiteln i EasyCruit.
-   ett RefId-element som är kundens externa referens (detta kan vara tomt).
-   en lista på de avdelningar som annonsen tillhör med avdelnings-id:n och namn.
-   en lista över de språk som annonsen getts ut på.

### XML-schemadefinitioner

XML-schema för begäran om VacancyList:  [https://www.easycruit.com/wsdl/ws/VacancyListRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML-schema för svar på VacancyList:  [https://www.easycruit.com/wsdl/ws/VacancyListRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML-exempel

#### VacancyList SOAP request exempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header> 

<urn:AuthHeader>

< Customer > ? < / Customer >

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?</ passwordString>

</ Password>

< !--Optional:-->

< Version>?< /Version>

</ urn:AuthHeader>

</ soapenv:Header>

< soapenv:Body>

< urn:VacancyList>

< urn:Vacancy language="?" department="?"/>

</ urn:VacancyList>

</ soapenv:Body>

</ soapenv:Envelope>

#### VacancyList SOAP response exempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyListResponse>

< VacancyList ContentLanguage="?">

< !--Noll eller flera repetitioner:-->

< Vacancy id="?">

< !--Du kan ange följande 4 objekt i vilken som helst ordning-->

< Title>?</ Title>

< RefId>?</ RefId>

< Departments>

< !--1 eller flera repetitioner:-->

< Department id="?">?</ Department>

< /Departments>

< Languages>

< !--1 eller flera repetitioner:-->

< Language iso="?">?</ Language>

< /Languages>

< /Vacancy>

< /VacancyList>

< /urn:VacancyListResponse>

< /soapenv:Body>

< /soapenv:Envelope>

.NET C# exempel

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

/* Hämtade objektuppgifter */

// Vacancy[ i ].Title

// Departments[ j ].Value

}

// Languages[ k ].iso

// Languages[ k ].Value

}

## Export av annonsdata

För att exportera annonsdata från EasyCruit måste du göra ett SOAP-anrop till EasyCruit Web Service ”VacancyExport”. Den här metoden tar emot fyra valfria parametrar: id (projekt-id för annonsen i EasyCruit), språk, avdelnings-id och allowXMLTags.

Om du inte anger ett annons-id kommer alla annonser som en given användare har åtkomst till att hämtas. Det är därför tillrådligt att du först använder webbtjänsten VacancyList som ett filter för att reducera mängden exporterade data. Vilken annons som helst kan finnas på ett eller flera språk (vilka språk som finns tillgängliga kan variera mellan projekt). För att hämta en annons på norska anger du "nb" i språkparametern. För att hämta alla annonser för en given kundavdelning måste du ange avdelnings-id i avdelningsparametern (avdelningens-id:n och annons-id:n kan hämtas från webbtjänsten VacancyList). AllowXMLTags anger om vi ska returnera annonstexten som rådata eller om vi ska ta bort HTML-taggar etc. från texten före exporten.

Den resulterande listan innehåller ett annonselement för varje exporterad annons. ”ID”-parametern för varje annons är det interna projekt-id:t i EasyCruit och språk-parametern anger vilket språk annonsen publicerades på. Varje annons kommer att innehålla följande element:

-   ProjectTitle vilket är projekttiteln i EasyCruit.
-   RefId som är kundens externa referens-id (detta kan vara tomt).

Vacancy id, vacancy language, ProjectTitle och RefId är för intern referens och inte avsedd för publicering:

Element som används för publicering är:

-   TitleHeading: Rubriken ovanför annonstiteln.
-   Title: Annonsen titel.
-   CompanyName: Företagets namn som det visas i annonsen.
-   Body: Annonstexten (antingen rådata eller strippad för HTML-enheter, beroende på parametern allow MLTags).
-   Deadline: Datumet (inte nödvändigtvis ett datum-/tidvärde) som är senaste ansökningsdatum för den lediga tjänsten.
-   Engagement: Datum (inte nödvändigtvis ett datum-/tidvärde) när företaget vill anställa.
-   Location: Geografisk plats för jobbet/befattningen.
-   CompanyInformation: Företagselementet har tre underelement: Department, About och Homepage. Detta är namnet, beskrivningen och hemsidan för den anställande kundavdelningen. Om befattningen gäller mer än en avdelning kommer denna information att upprepas för varje individuell avdelning.
-   Contacts: Lista på kontakter som är inkluderade i annonsen och vilka avdelningar de tillhör.

### XML-schemadefinitioner

XML-schema för begäran om VacancyExport:  [https://www.easycruit.com/wsdl/ws/VacancyExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-schema för svar på om VacancyExport:  [https://www.easycruit.com/wsdl/ws/VacancyExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-exempel

#### VacancyExport SOAP request exempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

 < soapenv:Header>

< urn:AuthHeader>

< Customer>?</ Customer>

< Username>?</ Username>

< Password passwordEncoding="?">

< passwordString>?</ passwordString>

</ Password>

< !--Optional:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyExport>

< urn:Vacancy id="?" department="?" language="?" allowMLTags="?"/>

< /urn:VacancyExport>

< /soapenv:Body>

< /soapenv:Envelope>

## VacancyExport SOAP response exempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyExportResponse>

< VacancyList>

<!--Noll eller flera repetitioner:-->

< Vacancy id="?" language="?">

< !--Du kan ange följande 13 objekt i vilken som helst ordning-->

< ProjectTitle>?</ ProjectTitle>

< refId>?</ refId>

< TitleHeading>?</ TitleHeading>

< Title>?</ Title>

< CompanyName>?</ CompanyName>

< Body>?</ Body>

< Deadline>?</ Deadline>

< Engagement>?</ Engagement>

< Location>?</ Location>

< DailyHours>?</ DailyHours>

< Contacts>

<!--Noll eller flera repetitioner:-->

<Contact>

<!--Du kan ange följande 5 objekt i vilken som helst ordning-->

<Name>?</Name>

<EmailAddress>?</EmailAddress>

<TelephoneOffice>?</TelephoneOffice>

<TelephoneMobile>?</TelephoneMobile>

<Department id="?">?</Department>

</Contact>

</Contacts>

<Questions>?</Questions>

<CompanyInformation>

<!--Noll eller flera repetitioner:-->

<Company>

<!--Du kan ange följande 3 objekt i vilken som helst ordning-->

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

.NET C# exempel:

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

/* Hämtade objektuppgifter */

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

## Import av annonsdata

För att importera annonsdata från EasyCruit måste du göra ett SOAP-anrop till EasyCruit Web Service ”VacancyImport”.

Följande data kan importeras:

-   Title: Annonsens titel.
-   TitleHeading: Rubriken ovanför annonstiteln.
-   Body: Annonstexten.
-   Deadline: Senaste ansökningsdatum.
-   Engagement: Anställningsdatum.
-   Location: Geografisk plats för jobbet/befattningen.

Det finns två obligatoriska parametrar som måste anges:

-   Språkparametern på versionselementet anger vilket språk annonsen publiceras på.
-   RefId-parametern i annonselementparametern är kundens interna referens för annonsen.

De importerade uppgifterna kommer att bli tillgängliga och valbara i en rullgardinsmeny i EasyCruit när en användare påbörjar ett nytt rekryteringsprojekt.

### XML-schemadefinitioner

XML-schema för begäran om VacancyExport:  [https://www.easycruit.com/wsdl/ws/VacancyExportRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML-schema för svar på om VacancyExport:  [https://www.easycruit.com/wsdl/ws/VacancyExportResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML-exempel

#### VacancyImport SOAP request exempel

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

<urn:VacancyImport>

<!--1 eller flera repetitioner:-->

<urn:Vacancy RefId="?">

<!--1 eller flera repetitioner:-->

<urn:Version Language="?">

<!--Du kan ange följande 8 objekt i vilken som helst ordning-->

<urn:Title>?</urn:Title>

<!--Optional:-->

<urn:TitleHeading>?</urn:TitleHeading>

<!--Optional:-->

<urn:Body>?</urn:Body>

<!--Optional:-->

<urn:Deadline>?</urn:Deadline>

<!--Optional:-->

<urn:Engagement>?</urn:Engagement>

<!--Optional:-->

<urn:Location>?</urn:Location>

<!--Optional:-->

<urn:DailyHours>?</urn:DailyHours>

<!--Optional:-->

<urn:Questions>?</urn:Questions>

</urn:Version>

</urn:Vacancy>

</urn:VacancyImport>

</soapenv:Body>

</soapenv:Envelope>

#### VacancyImport SOAP response exempel

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

<soapenv:Header/>

<soapenv:Body>

<urn:VacancyImportResponse>

<!--Optional:-->

<Status>?</Status>

</urn:VacancyImportResponse>

</soapenv:Body>

</soapenv:Envelope>

#### .NET C# exempel

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

Version.TitleHeading = "Systemutvecklare";

Version.Body = "Detta är annonstexten";

Version.Deadline

Version.Engagement = "1. augusti 2008";

Version.Location = "Oslo";

MessageVacancyImportResponse result = Service.VacancyImport(Vacancy);

Console.WriteLine(result.Status);

}

}

Se även:

![](../Resources/Images/icon-document-link.png)  [Kandidat-API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Annons XML-flöde](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer – Integration/API:er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Exempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer - Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1NDgxNzEyN119
-->