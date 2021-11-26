# Rekrutteringsprojekt XML-feed

Via RESTful (webservice) gør EasyCruit det muligt for dig at koble dig på vores system og trække data i det almindelige XML-format. Dette er den mest populære metode til opkobling, da det tillader hurtig og nem integrering med EasyCruit.

Vi giver dig en unik URL udelukkende til stillingsannoncer til dig, der indeholder aktive stillinger i XML-format.

## Feedtype

Denne EasyCruit RESTful-service leverer en live feed i realtid. Det betyder, at uafhængigt af din foretrukne indstilling til at definere publiceringsvarigheden (defineret ved publiceringsinterval eller brugerdefinerede datoer); vil alle anmodninger forblive i XML i den periode, der er blevet indstillet af kunden, da stillingen blev publiceret. Eksempel: Hvis brugeren valgte 2. januar som publiceringsstartdato og den 20. januar som slutdato, registreres anmodningen i XML fra 2. januar til 20. januar. Efter den 20. fjernes den fra feeden. Den liste af stillinger, der er publiceret på din side fra EasyCruit, bør altid repræsentere en kopi af publiceringer, der er anført i feeden. Hvis en kunde fjerner et jobopslag, fjernes jobbet fra XML’en.

### Annonceringsperiode

EasyCruit understøtter flere annonceringsperioder, som brugeren kan vælge imellem. Som udgangspunkt tilbyder vi 30 dage. Vi understøtter også brugerdefinerede publiceringsstart- og slutdatoer.

#### Kategoriserings-XML

< Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

< Versions>

< Version language="en"> (Vacancy language, ex. da, sv, eng, osv.)

< Title>Mandatory title< /Title>

< TitleHeading>Not mandatory sub title< /TitleHeading>

< AlternativeCompanyName>Company name< /AlternativeCompanyName>

< ApplicationDeadline>Free text field with application deadline< /ApplicationDeadline>

< Location>Free text field with job location</ Location>

< Engagement>Free text field with engagement< /Engagement>

< Region>

< Country id="xx" name="Sweden"> (Vacancy country)

< County id="xxx">Region in selected country< /County>

< /Country>

< /Region>

< Categories>

< Item type="area-of-interest" id="xxx">Area of interest< /Item>

< Item type="position-type" id="xxx">Position type< /Item>

< Item type="job-level" id="xxx">Job level< /Item>

< Item type="duration" id="xxx">Duration< /Item>

< Item type="extent" id="xxx">Extent< /Item>

< Item type="operating-time" id="xxx">Operation time< /Item>

< /Categories>

< /Version>

< /Versions>

< Departments>

< Department id="xxx">

< Name>Department name< /Name>

< LogoURL>Full URL to uploaded logo< /LogoURL>

< VacancyURL>URL to vacancy< /VacancyURL>

< ApplicationURL>URL to application form< /ApplicationURL>

< /Department>

< /Departments>

< /Vacancy>

#### Rekrutteringsprojekt-XML

Udover de ovennævnte variabler, er dette variablerne til stillingsaanoncen.

< Description>Vacancy text with html formatting included< /Description>

< About>Department ingress with html formatting< /About>

< PrivacyPolicy>Department Privacy Policy with html formatting< /PrivacyPolicy>

< Address type="postal">(Department postal)

< Street>Street name / number< /Street>

< Area>City< /Area>

< AreaCode>Zip< /AreaCode>

< /Address>

< Address type="office">(Department visiting address)

< Street>Street name / number< /Street>

< Area>City< /Area>

< AreaCode>Zip< /AreaCode>

< /Address>

< Telephone type="office">Phone< /Telephone>

< Telephone type="telefax">Fax< /Telephone>

< ContactPersons>

< ContactPerson>

< CommonName>Contact person name< /CommonName>

< Email>Contact person e-mail if published< /Email>

< Telephone type="office">Contact person phone number< /Telephone>

< Telephone type="cellular">Contact person cellular< /Telephone>

< /ContactPerson>

< /ContactPersons>

< HomepageURL>Department web site address< /HomepageURL>

< ImageURL>Full URL to uploaded image< /ImageURL>

### bemærkninger

Der kan være flere tilfælde af de følgende variabler <Country>, <County>, <ContactPersons>, <Item

type="area-of-interest">, < Item type="position-type">, < Item type="job-level">, < Item type="duration">,< Item type="extent">, < Item type="operating-time"> in every vacancy.

Den eneste obligatoriske variable er < Title>. Derfor er de andre felter muligvis tomme.

#### Flere afdelinger i rekrutteringsprojektet

En vigtig funktion i EasyCruit er, at du kan samle flere afdelinger i en annonce. Det betyder, at kandidaten tvinges til at vælge en afdeling, inden der kan ansøges. Denne funktion implementeres i XML. Kontakt EasyCruits Customer Success, hvis du har brug for at indstille en teststilling med flere afdelinger.

#### Cache

Der er en times cache i XML-feed fra EasyCruit. indtastninger, der foretages i EasyCruit er kun synlige en time senere, hvis brugeren bruger genudsendelsesfunktionen.

#### Yderligere oplysninger (XSD)

Kategorisering:  [https://www.easycruit.com/dtd/vacancy-list.xsd](https://www.easycruit.com/dtd/vacancy-list.xsd)

Rekrutteringsprojekt:  [https://www.easycruit.com/dtd/vacancy.xsd](https://www.easycruit.com/dtd/vacancy.xsd)

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Import og eksport af rekrutteringsprojektdata](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Kandidat-API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Integration/API’er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Eksempel på internetservicesvar](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Vejledning til administratorer - Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg4MzUzNTEwMl19
-->