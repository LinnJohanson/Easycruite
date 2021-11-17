# Vakanču XML plūsma

Ar RESTful (tīmekļa pakalpojums) palīdzību EasyCruit sniedz iespēju savienot jūsu sistēmu ar mūsu sistēmu un iegūt datus standartizētā XML formātā. Tā ir populārākā savienošanas metode, jo tā nodrošina ātru un ērtu integrāciju ar EasyCruit.

Mēs jums sniegsim unikālu vietrādi URL, kas paredzēts tikai jūsu sludinājumiem un saturēs aktīvās vakances XML formātā.

## Plūsmas veids

EasyCruit RESTful pakalpojums nodrošina reāllaika plūsmu. Tas nozīmē, ka neatkarīgi no jūsu vēlamās sludinājuma ilguma definēšanas opcijas (definēts sludinājuma intervāls vai pielāgoti datumi), visi pieprasījumi paliks XML noteiktajā laika periodā, ko iestatījis klients, izsludinot vakanci. Piemērs: ja lietotājs atlasīja 2. janvāri kā sludinājuma sākuma datumu un 20. janvāri kā sludinājuma beigu datumu, tad pieprasījums tiks iekļauts XML no 2. janvāra līdz 20. janvārim. Pēc 20 datuma tas tiks noņemts no plūsmas. Tādējādi vakanču saraksts, kas izsludināts no jūsu puses un ko sniedz EasyCruit, vienmēr atbilst plūsmā iekļautajiem sludinājumiem. Ja klients noņem sludinājumu, tad vakance tiek noņemta no XML.

### Sludinājuma periods

EasyCruit atbalsta vairākus sludinājuma periodus, ko izvēlas lietotājs. Standarta variantā mēs piedāvājam 30 dienas. Mēs atbalstām arī klienta izvēlētu sākuma un beigu datumu.

#### Saraksta XML

< Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

< Versions>

< Version language="en"> (Vacancy language, ex. da, sv, gb, etc.)

< Title>Obligāts virsraksts</ Title>

< TitleHeading>Neobligāts apakšvirsraksts</ TitleHeading>

< AlternativeCompanyName>Uzņēmuma nosaukums</ AlternativeCompanyName>

< ApplicationDeadline>Brīva stila teksts ar pieteikšanās datumu</ ApplicationDeadline>

< Location>Brīva stila teksts ar darba atrašanās vietu</ Location>

< Engagement>Brīva stila teksts ar iesaisti </ Engagement>

< Region>

< Country id="xx" name="Sweden"> (Vakances valsts)

< County id="xxx">Reģions izvēlētajā valstī</ County>

</ Country>

</ Region>

< Categories>

< Item type="area-of-interest" id="xxx">Interešu joma</ Item>

< Item type="position-type" id="xxx">Darba veids</ Item>

< Item type="job-level" id="xxx">Darba līmenis</ Item>

< Item type="duration" id="xxx">Ilgums</ Item>

< Item type="extent" id="xxx">Apjoms</ Item>

< Item type="operating-time" id="xxx">Darbības laiks</ Item>

</ Categories>

</ Version>

</ Versions>

<Nodaļas>

< Department id="xxx">

< Name>Nodaļas nosaukums</ Name>

< LogoURL>Augšupielādētā logotipa pilns URL</ LogoURL>

< VacancyURL>vakances URL </ VacancyURL>

< ApplicationURL>Pieteikuma veidlapas URL</ ApplicationURL>

</ Department>

</ Departments>

</ Vacancy>

#### Vakances XML

Papildus iepriekš norādītajiem mainīgajiem, tie ir vakances sludinājuma mainīgie.

< Description>Vakances teksts ar iekļautu html formātu</ Description>

< About>Nodaļas iekļuve ar html formātu</ About>

< PrivacyPolicy>Nodaļas privātuma politika ar html formātu</ PrivacyPolicy>

< Address type="postal">(Nodaļas pasts)

< Street>Ielas nosaukums/ numurs</ Street>

< Area>Pilsēta</ Area>

< AreaCode>Indekss</ AreaCode>

< /Address>

< Address type="office">(Nodaļas adrese)

< Street>Ielas nosaukums/ numurs< /Street>

< Area>Pilsēta</ Area>

< AreaCode>Indekss</ AreaCode>

</ Address>

< Telephone type="office">Tālrunis</ Telephone>

< Telephone type="telefax">Fakss</ Telephone>

< ContactPersons>

< ContactPerson>

< CommonName>Kontaktpersonas vārds</ CommonName>

< Email>Kontaktpersonas e-pasts, ja publicēts</ Email>

< Telephone type="office">Kontaktpersonas tālruņa numurs</ Telephone>

< Telephone type="cellular">Kontaktpersonas mobilais</ Telephone>

</ ContactPerson>

</ ContactPersons>

< HomepageURL>Nodaļas tīmekļa vietnes adrese</ HomepageURL>

< ImageURL>Augšupielādētā logotipa pilns URL</ ImageURL>

### Piezīmes

Katrā vakancē var būt vairāki šādi mainīgie: < Country>, < County>, < ContactPersons>, <Item

type="area-of-interest">, < Item type="position-type">, < Item type="job-level">, < Item type="duration">,< Item type="extent">, < Item type="operating-time">.

Vienīgais obligātais mainīgais ir <Title>. Tāpēc citi lauki var būt tukši.

#### Vairākas nodaļas vakancē

EasyCruit nodrošina svarīgu funkciju – piesaistīt sludinājumam vairākas nodaļas. Tas nozīmē, ka kandidāts tiek vedinātas izvēlēties nodaļu pirms pieteikšanās darbam. Šī funkcija ir ieviesta xml. Lūdzu, sazinieties ar EasyCruit klientu atbalsta nodaļu, ja vēlaties izveidot izmēģinājuma vakanci ar vairākām nodaļām.

#### Kešatmiņa

XML plūsmai no EasyCruit ir vienas stundas kešatmiņa. EasyCruit ieraksti būs redzami tikai vienu stundu vēlāk, ja vien lietotājs neizmanto pārpublicēšanas funkciju.

#### Papildu informācija (XSD)

Saraksts:  [https://www.easycruit.com/dtd/vacancy-list.xsd](https://www.easycruit.com/dtd/vacancy-list.xsd)

Vakance:  [https://www.easycruit.com/dtd/vacancy.xsd](https://www.easycruit.com/dtd/vacancy.xsd)

##### Skatīt arī:

![](../Resources/Images/icon-document-link.png)  [Vakanču datu imports un eksports](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png)  [Kandidātu API metodes](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – integrācija/API](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png)  [Tīmekļa pakalpojuma atbildes piemērs](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png)  [Administratoru rokasgrāmata – pārskati](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjc5MTg0ODUxXX0=
-->