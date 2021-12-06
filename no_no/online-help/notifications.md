# Meldinger

Dette avsnittet omfatter systemmeldinger om kjente problemer eller forbedringer.

## EasyCruit-melding – Multiposting. fr ustabil tjeneste – LØST

#### Beskrivelse av problemet / Hva er problemet?

Stillingsdistribusjonstjenesten levert av  Multiposting.fr  var ustabil. Problemet oppstod etter at stillingsdistribusjonstjenesten var migrert til et nytt datasenter i påsken. Kunder som har kunnet bruke Multiposting.fr-funksjonen, opplevde at det tok lengre tid enn ventet å laste inn Publisering-siden. Hvis i tillegg kunden valgte Multiposting.fr på Publisering-siden til å publisere, kunne publiseringen ta opptil tre minutter og var kanskje ikke vellykket, noe som resulterte i en 801-feilmelding.

#### Konsekvenser for kunden / Er jeg berørt?

Bare kunder som har aktivert den nye Multiposting.fr-tjenesten var berørt.

#### Omgåelse / Kan jeg omgå dette problemet?

Det var ingen måte å omgå problemet på.

#### Tiltak og handlinger / Hva gjør EasyCruit-teamet med dette?

Multiposting.fr-tjenesten ble fikset og fungerer nå som den skal. EasyCruit-teamet vil fortsette å følge med på tjenesten neste uke.

Ta gjerne kontakt med oss hvis du har spørsmål om dette.

## Visma EasyCruit kundestøtte

På kundeportalen Community kan du melde fra om problemer og følge med på behandlingsstatusen. Hvis ikke du har tilgang til Community, kan du kontakte systemansvarlig eller EasyCruit kundestøtte.

[Innlogging for den norske Community-portalen](https://community.visma.no/)

[Innlogging for Community-portalen for alle andre land](https://visma.force.com/customers/login)

## Meldinger

### Migrering av EasyCruit til Vismas vertsmiljø

#### Oppdatering – 23.04.2017

Migreringen til det nye datasenteret vårt er fullført, og alle kundene er nå oppe og går på den nye plattformen.

Vi opplever imidlertid problemer med å motta testresultater fra SHL og Assessio. Vi jobber for å løse dette så snart som mulig og vil holde deg oppdatert på denne siden.

Oppdatering 24.04.2017 09.30 CET: Vi mottar nå testresultater fra SHL og Assessio igjen. Disse resultatene stammer imidlertid bare fra nye tester, og tester som er kjørt av kandidater på lørdag ettermiddag og søndag, har ennå ikke blitt oppdatert i EasyCruit. Vi jobber for å løse dette.

#### Oppdatering – 11.04.2017

Som del av migrering til Vismas vertsmiljø vil det bli endringer i hvordan EasyCruit håndterer strukturen for avsenderpolicy (SPF) for e-post du skriver i EasyCruit.

En SPF-post vil bli opprettet i Vismas vertsmiljø, og den kan inkluderes i kundenes egne SPF-poster for å unngå å lage en liste over de enkelte oppføringene. Dette er et eksempel:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Vær klar over at ingen gamle poster må fjernes før etter at migreringen er gjennomført.

#### Oppdatering – 28.03.2017

Som vi har kunngjort tidligere, er migreringen av data fra Lumesse til Vismas vertsmiljø nå i gang. Migreringen av pilotkundene er nå fullført.

Basert på erfaringer fra pilotperioden ser vi at det tar lengre tid å migrere enn opprinnelig beregnet.

Den planlagte driftsstansen er derfor endret til lørdag 22.4 16.00 – søndag 23.4 06.00 CEST.

#### Oversikt

I 2016 kjøpte Visma EasyCruit fra Lumesse. Etter grundige forberedelser skal vi endelig flytte EasyCruit fra Lumesse til Vismas vertsmiljø. Migreringen skal skje trinnvis fra midten av mars til midten av april.

EasyCruit-tjenesten vil være tilgjengelig i migreringsperioden, unntatt under en planlagt driftsstans fra lørdag 22.4 16.00 til søndag 23.4 06.00 CEST. Viktige oppdateringer og status for migreringen kunngjøres på denne siden.

Som kunde skal du ikke bli berørt av disse endringene, med mindre du har hvitelistet IP-adressen til EasyCruits e-postserver i SPF-posten eller brannmuren/søppelpostfilteret. Etter migreringen endres e-postserverens IP-adresse, og du må oppdatere eventuelle hvitelister med den nye adressen. IP-adressen blir kunngjort i forkant av migreringen 22. april.

Vi ber deg gå til Visma Trust-Center/Transparency for å få oppdatert informasjon om vertsmiljøet vårt og behandling av data. Husk å dele denne informasjonen med alle relevante brukere og IT-avdelingen hos dere. Hvis du har spørsmål, kan du kontakte kundeansvarlig eller kundestøtte.

#### Nye IP-adresser for e-postserver

Nå når EasyCruit skal flytte til Vismas vertsmiljø, endres e-postserverens IP-adresse. Dette skjer under migreringen.

Alle kunder som bruker SPF-poster til å bekrefte EasyCruit som gyldig avsender, må legge til nye IP-adresser i SPF-posten. Dette er en manuell endring som må gjøres av IT-administratoren hos dere. Den gamle IP-adressen, 62.209.53.50, må ikke fjernes før etter at migreringen er gjennomført.

De nye IP-adressene kan legges til når som helst fra nå av. For at det ikke skal bli avbrudd i e-post som sendes fra EasyCruit, må dette gjøres innen 21. april.

De nye IP-adressene er:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

Som del av denne migreringen har det blitt opprettet en SPF-post som inkluderes i stedet for å måtte legge til hver enkelt IP-adresse manuelt. Et eksempel på hvordan denne posten inkluderes: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Vær klar over at ingen gamle poster må fjernes før etter at migreringen er gjennomført.

#### DNS-overføring

Når EasyCruit flyttes fra en vertsleverandør til en annen, får alle serverne i systemet nye IP-adresser.

Vi venter at overføringen av de nye IP-adressene til DNS-servere vil skje under driftsavbruddet og derfor ikke forårsake problemer for kundene våre.

Det er imidlertid mulig at enkelte servere ikke har mottatt de nye IP-adressene, eller at en kunde bruker lokalt bufrede DNS-poster. I slike tilfeller må kunden tømme den lokale bufferen eller bruke en alternativ DNS-server til den som brukes vanligvis, er oppdatert.

#### Nye IP-adresser for utgående trafikk

Når EasyCruit flyttes fra en vertsleverandør til en annen, får alle serverne i systemet nye IP-adresser.

Dette inkluderer serverne som oppretter utgående tilkoblinger, f.eks. integrering med publiseringskanaler og integrering av vurderinger.

Sammenlignet med hvordan EasyCruit fungerer i dag, vil tilkoblingene komme fra en rekke IP-adresser i stedet for en enkelt adresse. Hvis integreringspartnere benytter hvitelisting, må de oppdatere brannmuren for å tilrettelegge for disse endringene.

### Melding om driftsproblemer 31.8.2016 18.43 CEST LØST

Problemene er nå løst, og alle søkerne skal nå kunne søke på alle ledige stillinger.

Vær klar over at serverne måtte startes på nytt for at løsningen skulle implementeres. Dette kan ha forårsaket et kort avbrudd i tjenesten. Vi beklager eventuelle problemer dette kan ha medført.

#### Melding om driftsproblemer 31.8.2016 14:46 CEST

Vi opplever for øyeblikket noe forstyrrelser på EasyCruit-tjenesten. Problemet gjør at enkelte kandidater ikke kan fullføre søknaden sin. Dette skjer hvis feltene for utdanning og erfaring er obligatoriske i prosjektet. Vi jobber for å løse dette problemet så raskt vi kan og beklager problemene dette kan medføre.

### Melding om driftsproblemer – problem med sikkerhetssertifikat

Melding om driftsproblemer – problem med sikkerhetssertifikat 14.10.2016 13.13 CEST

GlobalSign, som utsteder sikkerhetssertifikatet vårt, opplever en feil, som berører EasyCruit og andre tjenester. Det kan hende brukere og kandidater får feilmeldinger når de prøver å bruke EasyCruit-tjenesten.

GlobalSign jobber for å løse problemet, men på grunn av bufringsfeil, kan dette ta opptil fire dager å fikse.

Hvis ikke du kan vente, kan du følge denne veiledningen fra GlobalSigns nettside for å tømme den aktuelle bufferen:

[https://support.globalsign.com/custo...ticles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

Vi beklager problemene dette kan medføre.

### Melding om vedlikehold av Visma EasyCruit – 05.06.2017 21.00–21.10 CEST

Vedlikehold av Visma EasyCruit utføres 5. juni 2017 mellom 21.00 og 21.10 CEST. Visma EasyCruit vil ikke være tilgjengelig i dette tidsrommet.

Brukere vil ikke kunne logge seg inn på systemet, og kandidater vil ikke kunne bruke karrieresenteret eller søke på stillinger.

Vi beklager problemene dette kan medføre.

Hvis du har spørsmål om dette vedlikeholdet, må du gjerne ta kontakt med din lokale Visma EasyCruit kundestøtte.

### Melding om driftsproblemer – ytelsesproblemer 17.01.2017

Visma EasyCruit opplever for øyeblikket noe forstyrrelser på tjenesten, noe som fører til lengre responstid for systembrukerne. Vi jobber for å løse dette problemet så raskt vi kan og beklager problemene dette kan medføre.

Utviklingsteamet vårt har egne folk som jobber med dette, og saken har høyeste prioritet.

Mot slutten av denne uken skal vi installere mer minne som et tiltak for å få raskere responstid.

### Melding om vedlikehold av EasyCruit – 14.03.2017 18.30–19.00 CET

Vedlikehold av minnebufferen utføres 14. mars 2017 mellom 18.30 og 19.00 CET. EasyCruit vil ikke være tilgjengelig i dette tidsrommet.

Brukere vil ikke kunne logge seg inn på systemet, og kandidater vil ikke kunne bruke karrieresenteret eller søke på stillinger.

Vi beklager problemene dette kan medføre.

Hvis du har spørsmål om dette vedlikeholdet, må du gjerne ta kontakt med din lokale EasyCruit kundestøtte.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjc1NTMyODQ3XX0=
-->