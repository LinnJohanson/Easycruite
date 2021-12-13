# Vacature-XML-feed

Via RESTful (webservice) biedt EasyCruit u de mogelijkheid om te verbinden met ons systeem en gegevens op te halen in het gestandaardiseerde XML-formaat. Dit is de meest populaire verbindingsmethode omdat deze een snelle en eenvoudige integratie met EasyCruit mogelijk maakt.

We voorzien u van een unieke URL, uitsluitend voor vacatureplaatsingen voor u, met actieve vacatures in XML-formaat.

## Feedtype

De EasyCruit RESTful-service zorgt voor een live, realtimefeed. Dit betekent dat ongeacht uw voorkeursoptie voor de plaatsingsduur (opgegeven plaatsingsinterval of aangepaste datums) alle verzoeken in de XML blijven gedurende die tijdsperiode die ingesteld is door de klant bij het plaatsen van de vacature. Voorbeeld: als de gebruiker 2 januari geselecteerd heeft als startdatum en 20 januari als einddatum voor de plaatsing, dan wordt het verzoek vermeld in de XML van 2 januari tot 20 januari. Na de 20ste wordt het verwijderd uit de feed. Dit betekent dus dat de lijst met de door u geplaatste vacatures aangeleverd door EasyCruit altijd een kopie moet zijn van de plaatsingen die vermeld staan in de feed. Als een klant een geplaatste vacature verwijdert, dan wordt deze vacature verwijderd uit de XML.

### Plaatsingsperiode

EasyCruit ondersteunt meerdere plaatsingsperiodes die gekozen kunnen worden door de gebruiker. Standaard bieden we 30 dagen aan. We ondersteunen echter ook aangepaste start- en einddatums voor plaatsingen.

#### Lijst-XML

<Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

<Versions>

<Version language="en"> (vacaturetaal bv. da, sv, gb enz.)

<Title>Verplichte titel</Title>

<TitleHeading>Niet-verplichte subtitel</TitleHeading>

<AlternativeCompanyName>Bedrijfsnaam</AlternativeCompanyName>

<ApplicationDeadline>Vrije tekst met sluitingsdatum voor sollicitaties</ApplicationDeadline>

<Location>Vrije tekst met locatie van de functie</Location>

<Engagement>Vrije tekst m.b.t. dienstverband</Engagement>

<Region>

<Country id="xx" name="Sweden"> (land van de vacature)

<County id="xxx">Region in selected country</County>

</Country>

</Region>

<Categories>

<Item type="area-of-interest" id="xxx">Area of interest</Item>

<Item type="position-type" id="xxx">Position type</Item>

<Item type="job-level" id="xxx">Job level</Item>

<Item type="duration" id="xxx">Duration</Item>

<Item type="extent" id="xxx">Extent</Item>

<Item type="operating-time" id="xxx">Operation time</Item>

</Categories>

</Version>

</Versions>

<Departments>

<Department id="xxx">

<Name>Afdelingsnaam</Name>

<LogoURL>Volledige URL naar geüpload logo</LogoURL>

<VacancyURL>URL naar vacature</VacancyURL>

<ApplicationURL>URL naar sollicitatieformulier</ApplicationURL>

</Department>

</Departments>

</Vacancy>

#### Vacature-XML

Naast de bovenstaande variabelen zijn er deze variabelen voor de vacatureadvertentie.

<Description>Vacaturetekst inclusief html-opmaak</Description>

<About>Introductietekst over afdeling met html-opmaak</About>

<PrivacyPolicy>Privacybeleid van afdeling met html-opmaak</PrivacyPolicy>

<Address type="postal">(postcode afdeling)

<Street>Straatnaam / nummer</Street>

<Area>Plaats</Area>

<AreaCode>Postcode</AreaCode>

</Address>

<Address type="office">(bezoekadres afdeling)

< Street>Straatnaam / nummer</Street>

< Area>Plaats</Area>

< AreaCode>Postcode</AreaCode>

< /Address>

< Telephone type="office">Phone</Telephone>

< Telephone type="telefax">Fax</Telephone>

< ContactPersons>

< ContactPerson>

< CommonName>Naam contactpersoon</CommonName>

< Email>E-mail contactpersoon indien weergegeven</Email>

< Telephone type="office">Contact person phone number< /Telephone>

< Telephone type="cellular">Contact person cellular< /Telephone>

< /ContactPerson>

< /ContactPersons>

< HomepageURL>Websiteadres afdeling< /HomepageURL>

< ImageURL>Volledige URL naar geüploade afbeelding< /ImageURL>

### Opmerkingen

De volgende variabelen <Country>, <County>, <ContactPersons>, <Item

type="area-of-interest">, < Item type="position-type">, < Item type="job-level">, < Item type="duration">,< Item type="extent">, < Item type="operating-time"> kunnen meerdere keren voorkomen in elke vacature.

De enige verplichte variabele is <Title>. Andere velden kunnen dus leeg zijn.

#### Meerdere afdelingen in de vacature

Een belangrijke functie van EasyCruit is dat u meerdere afdelingen kunt koppelen aan een advertentie. Dit zou betekenen dat de kandidaat verplicht is een afdeling te kiezen voor hij/zij kan solliciteren op de vacature. Deze functie wordt geïmplementeerd in de xml. Neem contact op met het EasyCruit Customer Success-team voor een testconfiguratie met meerdere afdelingen.

#### Cache

Er is één uur cache voor de XML-feed vanaf EasyCruit. Invoeren in EasyCruit zijn pas een uur later zichtbaar behalve als de gebruiker de opnieuw publiceren-functie gebruikt.

#### Aanvullende informatie (XSD)

Lijst:  [https://www.easycruit.com/dtd/vacancy-list.xsd] (https://www.easycruit.com/dtd/vacancy-list.xsd)

Vacature:  [https://www.easycruit.com/dtd/vacancy.xsd] (https://www.easycruit.com/dtd/vacancy.xsd)

##### Zie ook:

![](../Resources/Images/icon-document-link.png)  [Importeren en exporteren van vacaturegegevens](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Kandidaten-API-methodes](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Integratie / API's](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Voorbeeld Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Handleiding voor administrators - Rapportages](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MjU0MTE0NDJdfQ==
-->