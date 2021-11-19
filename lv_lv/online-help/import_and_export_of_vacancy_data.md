# Vakanču datu imports un eksports

## Pārskats

Šajā rakstā aprakstītas trīs tīmekļa pakalpojumu metodes, ko izmanto WSDL: https://www.easycruit.com/wsdl/ws/EasyCruit.wsdl

-   VacancyLis  – eksportē pieejamo vakanču sarakstu no EasyCruit.
-   VacancyExport  – eksportē vakanču datus no EasyCruit.
-   VacancyImport  – importē vakanču datus sistēmā EasyCruit.

## Tīmekļa pakalpojumu piekļuves iespējošana

Lai piekļūtu EasyCruit tīmekļa pakalpojumam, vajadzīgs derīgs EasyCruit konts. Autentifikācija nepieciešama katru reizi, kad tiek pieprasīts tīmekļa pakalpojums, ievadot derīgu klienta identifikatoru, lietotājvārdu un paroli pieprasījuma SOAP galvenē. Ņemiet vērā, ka parolēs nevar būt simbols £ vai €.

Turklāt piekļuvi atsevišķām tīmekļa pakalpojumu metodēm kontrolē ar konfigurācijas kopas opcijām EasyCruit sistēmā – gan attiecībā uz visiem klientiem kopumā, gan attiecībā uz katru lietotāju. Tas tiek darīts, lai maksimāli kontrolētu piekļuvi datiem, kad tiek izmantoti EasyCruit tīmekļa pakalpojumi. Lai iegūtu piekļuvi tīmekļa pakalpojumu metodēm, gan klients, gan lietotājs ir jākonfigurē ar atbilstošām tiesībām EasyCruit sistēmā. To var izdarīt, nosūtot pieprasījumu EasyCruit klientu atbalsta komandai un norādot, kādas tīmekļa pakalpojumu metodes ir vajadzīgas un kuriem lietotājiem vajadzīga piekļuve konkrētai metodei.

EasyCruit sistēmas ietvaros gan klientu, gan lietotāju iestatīšanā eksporta/importa tīmekļa pakalpojumus dēvē šādi:

-   Piekļuve VacancyList eksportam (VakančuSaraksts)
-   Piekļuve vakanču apraksta datu eksportam (VakančuEksports)
-   Piekļuve vakanču apraksta datu importam (VakančuImports)

## Vakanču saraksta eksports

Lai izgūtu vakanču sarakstu, kuram lietotājs var piekļūt EasyCruit sistēmā, jāveic SOAP pieprasījums attiecībā uz EasyCruit tīmekļa pakalpojuma metodi, ko sauc par “VacancyList”, izmantojot konkrētā lietotāja pieteikšanās datus.

VacancyList var būt divi izvēles parametri: valoda un nodaļa. Šos parametrus var izmantot, lai filtrētu eksportēto sarakstu pēc attiecīgās valodas un/vai nodaļas. Ja parametri netiks noteikti, tad rezultātā būs pilns vakanču saraksts. Eksportēto sarakstu var izmantot, lai veiktu papildu pieprasījumus attiecība uz to pašu metodi, lai sašaurinātu atlasi, vai veikt papildu pieprasījumus attiecībā uz VacancyExport metodi.

Iegūtajā sarakstā pieejamai vakancei būs viens vakances elements. Katras vakances “id” parametrs ir EasyCruit sistēmā esošais iekšējā projekta id. Katra vakance saturēs:

-   Nosaukuma elementu, kas ir projekta nosaukums EasyCruit sistēmā.
-   RefId elementu, kas ir klienta ārējā atsauce (tā var būt tukša).
-   To nodaļu saraksts, ar kurām vakance ir saistīta, ieskaitot nodaļu id un nosaukumu.
-   To valodu saraksts, kurās vakance ir pieejama.

### XML shēmas definīcija

XML shēmas definīcija attiecībā uz VacancyList pieprasījumu:  [https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...istRequest.xsd)

XML shēmas definīcija attiecībā uz VacancyList atbildi:  [https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...stResponse.xsd)

### XML piemēri

#### VacancyList SOAP pieprasījuma piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

 < urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?</passwordString>

< /Password>

< !--Optional:-->

< Version>?</Version>

</urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyList>

< urn:Vacancy language="?" department="?"/>

< /urn:VacancyList>

< /soapenv:Body>

< /soapenv:Envelope>

#### VacancyList SOAP atbildes piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

 < soapenv:Header/>

< soapenv:Body>

< urn:VacancyListResponse>

< VacancyList ContentLanguage="?">

< !--Nulle vai vairāk atkārtojumu:-->

< Vacancy id="?">

< !--Jūs varat ievadīt 4 vienumus jebkurā kārtībā-->

< Title>?< /Title>

< RefId>?< /RefId>

< Nodaļas>

< !--1 vai vairāki atkārtojumi:-->

< Department id="?">?< /Department>

< /Departments>

< Valodas>

< !--1 vai vairāki atkārtojumi:-->

< Language iso="?">?< /Language>

< /Languages>

< /Vacancy>

< /VacancyList>

< /urn:VacancyListResponse>

< /soapenv:Body>

< /soapenv:Envelope>

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

## Vakanču datu eksports

Lai eksportētu datus no EasyCruit, jāveic SOAP pieprasījums attiecībā uz EasyCruit tīmekļa pakalpojumu “VacancyExport”. Šai metodei var izmantot četrus izvēles parametrus: id (vakances projekta id EasyCruit sistēmā), valoda, nodaļas id un allowXMLTags.

Ja nenorāda vakances id, tad rezultātā būs visas vakances, kurām konkrētajam lietotājam ir piekļuve. Tāpēc ir ieteicams vispirms izmantot VacancyList tīmekļa pakalpojumu kā filtru, lai samazinātu eksportēto datu daudzumu. Vakance var būt vienā vai vairākās valodās (valodu pieejamība dažādām vakancēm var būt dažāda). Lai izgūtu vakanci norvēģu valodā, valodas parametrā norādiet “nb”. Lai izgūtu visas noteiktai klienta nodaļai piesaistītās vakances, nodaļās parametrā ir jānorāda nodaļas id (nodaļas un vakances id var izgūt no VacancyList tīmekļa pakalpojuma). AllowXMLTags norāda, vai mums jāparāda vakances teksts kā jēldati vai arī pirms eksportēšanas mums ir jānoņem HTML tagi u.c. no teksta.

Katrai eksportētajai vakancei būs viens vakances elements. Katras vakances “id” parametrs ir projekta iekšējais id EasyCruit sistēmā, un valodas parametrs norāda valodu, kurā vakance bija publicēta. Katra vakance saturēs šādus elementus:

-   ProjectTitle, kas ir projekta nosaukums EasyCruit sistēmā.
-   RefId, kas ir klienta ārējās atsauces id.

Vakances id, vakances valoda, ProjectTitle un RefId ir paredzēti iekšējai atsaucei un nav domāti publicēšanai:

Publicēšanai paredzēti šādi elementi:

-   TitleHeading: virsraksts virs vakances nosaukuma.
-   Title: vakances nosaukums.
-   CompanyName: uzņēmuma nosaukums tādā veidā, kādā tas tiek parādīts vakancē.
-   Body: vakances teksts (vai nu jēldati vai atbrīvots no HTML elementiem atkarībā no MLTags parametra).
-   Deadline: datums (nav obligāti jābūt datuma vai laika vērtībai), kas ir pieteikšanās termiņš vakancei.
-   Engagement: datums (nav obligāti jābūt datuma vai laika vērtībai), kad uzņēmums vēlas pieņemt darbā.
-   Location: darba ģeogrāfiskā atrašanās vieta.
-   CompanyInformation: uzņēmuma elements, kam ir trīs apakšelementi: Nodaļa, Par un Sākumlapa. Tas ir klienta nodaļas nosaukums, apraksts un sākumlapa. Ja vakance ir saistīta ar vairākām nodaļām, šī informācija tiks atkārtota katrai atsevišķai nodaļai.
-   Contacts: vakancē iekļauto kontaktpersonu saraksts un to saistība ar attiecīgajām nodaļām.

### XML shēmas definīcija

XML shēmas definīcija attiecībā uz VacancyExport pieprasījumu:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML shēma attiecībā uz VacancyExport atbildi:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML piemēri

#### VacancyExport SOAP pieprasījuma piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

 < passwordString>?< /passwordString>

< /Password>

< !--Optional:-->

< Version>?< /Version>

< /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyExport>

< urn:Vacancy id="?" department="?" language="?" allowMLTags="?"/>

</ urn:VacancyExport>

< /soapenv:Body>

< /soapenv:Envelope>

## VacancyExport SOAP atbildes piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyExportResponse>

< VacancyList>

< !--Nulle vai vairāk atkārtojumu:-->

< Vacancy id="?" language="?">

< !--Var ievadīt 13 vienumus jebkurā kārtībā-->

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

< !--Nulle vai vairāk atkārtojumu:-->

< Contact>

< !--You may enter the following 5 items in any order-->

< Name>?<  /Name>

< EmailAddress>?< /EmailAddress>

< TelephoneOffice>?< /TelephoneOffice>

< TelephoneMobile>?< /TelephoneMobile>

< Department id="?">?</ Department>

< /Contact>

< /Contacts>

< Questions>?</ Questions>

< CompanyInformation>

< !--Nulle vai vairāk atkārtojumu:-->

<Izņēmums>

< !--Jūs varat ievadīt 3 vienumus jebkurā kārtība-->

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

## Vakanču datu imports

Lai importētu datus no EasyCruit, jāveic SOAP pieprasījums attiecībā uz EasyCruit tīmekļa pakalpojumu “VacancyImport”.

Var importēt šādus datus:

-   Title: vakances nosaukums.
-   TitleHeading: virsraksts virs vakances nosaukuma.
-   Body: vakances teksts.
-   Deadline: datums, līdz kuram kandidātam jāpiesakās.
-   Engagement: darbā pieņemšanas laiks.
-   Location: darba ģeogrāfiskā atrašanās vieta.

Ir jānorāda divi obligātie parametri:

-   Valodas parametrs versijas elementā norāda, kāda valodā ir vakance.
-   RefId parametrs vakances elementa parametrā ir klienta vakances iekšējā atsauce.

Importētie dati kļūst pieejami un atlasāmi EasyCruit nolaižamajā izvēlnē, kad lietotājs sāk jaunu vakances projektu.

### XML shēmas definīcija

XML shēmas definīcija attiecībā uz VacancyExport pieprasījumu:  [https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd](https://www.easycruit.com/wsdl/ws/Va...ortRequest.xsd)

XML shēma attiecībā uz VacancyExport atbildi:  [https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd](https://www.easycruit.com/wsdl/ws/Va...rtResponse.xsd)

### XML piemēri

#### VacancyImport SOAP pieprasījuma piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header>

< urn:AuthHeader>

< Customer>?< /Customer>

< Username>?< /Username>

< Password passwordEncoding="?">

< passwordString>?< /passwordString>

< /Password>

< !--Optional:-->

< Version>?< /Version>

 < /urn:AuthHeader>

< /soapenv:Header>

< soapenv:Body>

< urn:VacancyImport>

< !--1 vai vairāki atkārtojumi:-->

< urn:Vacancy RefId="?">

< !--1 vai vairāki atkārtojumi:-->

< urn:Version Language="?">

< !--Jūs varat ievadīt 8 vienumus jebkurā kārtībā-->

< urn:Title>?</urn:Title>

< !--Optional:-->

< urn:TitleHeading>?</urn:TitleHeading>

< !--Optional:-->

< urn:Body>?</urn:Body>

< !--Optional:-->

< urn:Deadline>?</urn:Deadline>

< !--Optional:-->

< urn:Engagement>?</urn:Engagement>

< !--Optional:-->

< urn:Location>?</urn:Location>

< !--Optional:-->

< urn:DailyHours>?</urn:DailyHours>

< !--Optional:-->

< urn:Questions>?</urn:Questions>

</urn:Version>

</urn:Vacancy>

</urn:VacancyImport>

</soapenv:Body>

</soapenv:Envelope>

#### VacancyImport SOAP atbildes piemērs

<soapenv:Envelope xmlns:soapenv="[http://schemas.xmlsoap.org/soap/envelope/](http://schemas.xmlsoap.org/soap/envelope/)" xmlns:urn="urn:EasyCruit">

< soapenv:Header/>

< soapenv:Body>

< urn:VacancyImportResponse>

< !--Optional:-->

< Status>?< /Status>

</urn:VacancyImportResponse>

</soapenv:Body>

</soapenv:Envelope>

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

Version.TitleHeading = "Sistēmas attīstītāji";

Version.Body = "Šis ir vakances teksts";

Version.Deadline

Version.Engagement = "1. august 2008";

Version.Location = "Oslo";

MessageVacancyImportResponse result = Service.VacancyImport(Vacancy);

Console.WriteLine(result.Status);

}

}

##### Skatīt arī:

![](../Resources/Images/icon-document-link.png)  [Kandidātu API metodes](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Vakanču XML plūsma](vacancy_xml_feed.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – integrācija/API](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Tīmekļa pakalpojuma atbildes piemērs](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – pārskati](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDAxMjU5NTcyLDExNTM4MTYwMTZdfQ==
-->