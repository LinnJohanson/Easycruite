# Annons XML-flöde

Via RESTful (webservice) tillåter EasyCruit att du ansluter till vårt system och hämtar data i det standardiserade XML-formatet. Detta är den populäraste anslutningsmetoden, eftersom den möjliggör snabb och enkel integration med EasyCruit.

Vi ger dig en unik URL, enbart för jobbannonser till dig, som innehåller aktiva jobb i XML-format.

## Typ av flöde

EasyCruit RESTful-tjänsten ger ett aktuellt, realtidsflöde. Det innebär att oberoende av ditt föredragna alternativ att definiera publiceringsperioden (definierat publiceringsintervall eller anpassade datum) kommer alla annonser att ligga kvar i XML enligt den tidsram som har angetts av kunden när jobbet publicerades. Exempel: om användare valde den 2 januari som publiceringsdatum och den 20 januari som sista ansökningsdag, så kommer annonsen att listas i XML från den 2 januari till den 20 januari. Efter den 20:e kommer den att tas bort från flödet Därför kommer listan på lediga jobb som publicerats på din sida, som tillhandahålls av EasyCruit, alltid att visa en kopia av publiceringarna som är listade i flödet. Om en kund tar bort ett publicerat jobb, kommer det jobbet att tas bort från XML.

### Publiceringsperiod

EasyCruit stöder flera publiceringsperioder som kan väljas av användaren. Som standard erbjuder vi 30 dagar Vi stöder dock även anpassade start- och slutdatum.

#### Att lista i XML

<Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

<Versions>

<Version language="en"> (Annonsens språk t.ex. da, sv, gb, osv.)

<Title>Obligatorisk rubrik</Title>

<TitleHeading>Ej obligatorisk underrubrik</TitleHeading>

<AlternativeCompanyName>Företagsnamn</AlternativeCompanyName>

<ApplicationDeadline>Fritextfält med sista ansökningsdag</ApplicationDeadline>

<Location>Fritextfält med placeringsort</Location>

< Engagement>Fritextfält med anställningstid</ Engagement>

< Region>

< Country id="xx" name="Sweden"> (Land där jobbet finns)

<County id="xxx">Region i det valda landet</County>

</Country>

</Region>

< Categories>

< Item type="area-of-interest" id="xxx">Intresseområde</Item>

< Item type="position-type" id="xxx">Jobbkategori</Item>

<Item type="job-level" id="xxx">Nivå</Item>

<Item type="duration" id="xxx">Varaktighet</Item>

<Item type="extent" id="xxx">Omfattning</Item>

<Item type="operating-time" id="xxx">Driftstid</Item>

</Categories>

</Version>

</Versions>

<Departments>

<Department id="xxx">

<Name>Avdelningsnamn</Name>

<LogoURL>Fullständig URL till uppladdad logotyp</LogoURL>

<VacancyURL>URL till annons</VacancyURL>

<ApplicationURL>URL till ansökningsformulär</ApplicationURL>

</Department>

</Departments>

</Vacancy>

#### Annons XML

Förutom ovanstående variabler är finns dessa variabler för platsannonsen.

<Description>Annonstext i html-format ingår</Description>

<About>Avdelning, inledning i html-format</About>

<PrivacyPolicy>Avdelning, integritetspolicy i html-format</PrivacyPolicy>

<Address type="postal">(Avdelningens postadress)

<Street>Gatuadress/nummer</Street>

<Area>Ort</Area>

<AreaCode>Postnummer</AreaCode>

</ Address>

< Address type="office">(Avdelningens besöksadress)

< Street>Gatuadress/nummer</Street>

< Area>Ort</Area>

< AreaCode>Postnummer</AreaCode>

< /Address>

< Telephone type="office">Telefon</ Telephone>

<Telephone type="telefax">Fax</Telephone>

<ContactPersons>

<ContactPerson>

<CommonName>Kontaktpersonens namn</CommonName>

<Email>Kontaktpersonens e-postadress om den är publicerad</Email>

<Telephone type="office">Kontaktpersonens telefonnummer</Telephone>

<Telephone type="cellular">Kontaktpersonens mobilnummer</Telephone>

</ContactPerson>

</ContactPersons>

<HomepageURL>Avdelnings webbadress</HomepageURL>

<ImageURL>Fullständig URL till uppladdad bild</ImageURL>

### Anteckningar

Det kan finnas flera förekomster av följande variabler <Country>, <County>, <ContactPersons>, <Item

type="area-of-interest">, <Item type="position-type">, <Item type="job-level">, <Item type="duration">,<Item type="extent">, <Item type="operating-time"> i varje annons.

Den enda obligatoriska variabeln är <Title>. Därför kan andra fält vara tomma.

#### Flera avdelningar i annonsen

En viktig funktion i EasyCruit är att du kan knyta flera avdelningar till en annons. Det innebär att kandidaten måste välja en avdelning innan det går att ansöka om jobbet. Den här funktionen kommer att implementeras i xml. Kontakta EasyCruit Customer Success om du behöver lägga upp en testannons med flera avdelningar.

#### Cache

XML-flödet från EasyCruit cachas i en timme. Poster som upprättas i EasyCruit kommer bara att visas i en timme, om inte användaren använder funktionen publicera på nytt.

#### Ytterligare information (XSD)

Listning:  [https://www.easycruit.com/dtd/vacancy-list.xsd](https://www.easycruit.com/dtd/vacancy-list.xsd)

Annons:  [https://www.easycruit.com/dtd/vacancy.xsd](https://www.easycruit.com/dtd/vacancy.xsd)

##### Se även:

![](../Resources/Images/icon-document-link.png)  [Import och export av annonsdata](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Kandidat-API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer – Integration/API:er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Exempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Vägledning för administratörer - Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3NTM2OTE5NSwxOTQ0OTgzNjY5XX0=
-->