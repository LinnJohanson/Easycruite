# XML annonsefeed

Ved hjelp av EasyCruits nettjeneste RESTful kan du koble til systemet vårt og hente ut data i standardisert XML-format. Dette er den vanligste tilkoblingsmåten, da den gjør det mulig med rask og enkel integrering med EasyCruit.

Vi gir deg en unik URL-adresse som kun brukes til stillingsannonser til deg, og som inneholder aktive jobber i XML-format.

## Type feed

EasyCruits RESTful-tjeneste leverer en direktefeed i sanntid. Det betyr at den er uavhengig av dine preferanser for å definere publiseringsvarigheten (definert publiseringsintervall eller egendefinerte datoer), og alle forespørsler vil være i XML-format i tidsrommet som er angitt av kunden ved publisering av jobben. Eksempel: Hvis brukeren valgte 2. januar som startdato for publisering og 20. januar som sluttdato for publisering, da vil forespørselen være oppført i XML-feeden fra 2. januar til 20. januar. Etter den 20. fjernes den fra feeden. Det vil si at listen med jobber som du har publisert via EasyCruit, skal alltid representere en kopi av annonser oppført i feeden. Hvis en kunde fjerner stillingsannonsen, fjernes den også fra XML-feeden.

### Publiseringsperiode

EasyCruit støtter mange publiseringsperioder som brukeren kan velge. Som standard tilbyr vi 30 dager. Vi har støtte for egendefinerte start- og sluttdatoer også.

#### Oppførings-XML

<Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

<Versions>

<Version language="en"> (annonsespråket, f.eks. da, sv, gb osv.)

<Title>Obligatorisk tittel</Title>

<TitleHeading>Ikke obligatorisk undertittel</TitleHeading>

<AlternativeCompanyName>Virksomhetens navn</AlternativeCompanyName>

<ApplicationDeadline>Fritekstfelt med søknadsfrist</ApplicationDeadline>

<Location>Fritekstfelt med arbeidssted</Location>

<Engagement>Fritekstfelt med tiltredelse</Engagement>

<Region>

<Country id="xx" name="Sweden"> (landet tilknyttet stillingen)

<County id="xxx">Fylke i det valgte landet</County>

</Country>

</Region>

<Categories>

<Item type="area-of-interest" id="xxx">Interesser</Item>

<Item type="position-type" id="xxx">Stillingstype</Item>

<Item type="job-level" id="xxx">Stillingsnivå</Item>

<Item type="duration" id="xxx">Varighet</Item>

<Item type="extent" id="xxx">Omfang</Item>

<Item type="operating-time" id="xxx">Driftstid</Item>

</Categories>

</Version>

</Versions>

<Departments>

<Department id="xxx">

<Name>Avdelingens navn</Name>

<LogoURL>Fullstendig URL til opplastet logo</LogoURL>

<VacancyURL>URL til annonse</VacancyURL>

<ApplicationURL>URL til søknadsskjema</ApplicationURL>

</Department>

</Departments>

</Vacancy>

#### Annonse-XML

I tillegg til variablene ovenfor er dette variablene for stillingsannonsen.

<Description>Annonsetekst med HTML-formatering inkludert</Description>

<About>Informasjon om avdelingen med HTML-formatering</About>

<PrivacyPolicy>Avdelingens personverngaranti med HTML-formatering</PrivacyPolicy>

<Address type="postal">(avdelingens postadresse)

<Street>Gatenavn/nummer</Street>

<Area>Poststed</Area>

<AreaCode>Postnummer</AreaCode>

</Address>

<Address type="office">(avdelingens besøksadresse)

<Street>Gatenavn/nummer</Street>

<Area>Poststed</Area>

<AreaCode>Postnummer</AreaCode>

</Address>

<Telephone type="office">Telefon</Telephone>

<Telephone type="telefax">Faks</Telephone>

<ContactPersons>

<ContactPerson>

<CommonName>Kontaktpersonens navn</CommonName>

<Email>Kontaktpersonens e-postadresse (hvis publisert)</Email>

<Telephone type="office">Kontaktpersonens telefon</Telephone>

<Telephone type="cellular">Kontaktpersonens mobiltelefon</Telephone>

< /ContactPerson>

< /ContactPersons>

< HomepageURL>URL til avdelingens nettsider< /HomepageURL>

< ImageURL>Fullstendig URL til opplastet bilde< /ImageURL>

### Merknader

Følgende variabler kan forekomme flere ganger < Country>, < County>, < ContactPersons>, <Item

type="area-of-interest">, < Item type="position-type">, < Item type="job-level">, < Item type="duration">,< Item type="extent">, < Item type="operating-time"> i annonsene.

Den eneste obligatoriske variabelen er < Title>. De andre feltene kan derfor være tomme.

#### Flere avdelinger i annonsen

En viktig funksjon i EasyCruit er at du kan knytte flere avdelinger til samme annonse. I så fall må kandidaten velge en avdeling før han eller hun søke på stillingen. Denne funksjonen vil bli implementer i XML. Kontakt vårt EasyCruit Customer Success Team hvis du trenger å konfigurere en teststilling med flere avdelinger.

#### Buffer

XML-feeden fra EasyCruit har en buffer på én time. Oppføringer i EasyCruit vil bare være synlige i én time med mindre brukeren anvender funksjonen for publisering på nytt.

#### Tilleggsinformasjon (XSD)

Oppføring:  [https://www.easycruit.com/dtd/vacancy-list.xsd](https://www.easycruit.com/dtd/vacancy-list.xsd)

Annonse:  [https://www.easycruit.com/dtd/vacancy.xsd](https://www.easycruit.com/dtd/vacancy.xsd)

###### Se også:

![](../Resources/Images/icon-document-link.png)  [Importere og eksportere annonsedata](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Kandidatrelaterte API-metoder](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Integrasjon/API-er](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Eksempel på Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratorveiledning – Rapporter](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzE5NzMxMTc5XX0=
-->