# Notifikationer

Dette afsnit indeholder systemnotifikationer om alle kendte problemer eller forbedringer.

## EasyCruit-notifikation - Mulltiposting. fr uregelmæssig service - LØST

#### Problembeskrivelse/Hvad er problemet?

Jobfordelingsservicen, der leveres af  Multiposting.fr  tilbød en uregelmæssig service. Dette problem opstod efter færdiggørelsen af ​​en migrering af deres jobfordelings til et nyt datacenter, hvilket fandt sted i løbet af påsken. Kunder, der havde kunne bruge funktionen Multiposting.fr, oplevede længere end forventede sideindlæsningstider på Publiceringssiden. Yderligere blev det oplevet, at hvis en kunde valgte at annoncere fra Publiceringssiden ved hjælp af Multiposting.fr, kunne det tage op til 3 minutter og måske endda mislykkes med visning af fejlmeddelelse 801.

#### Kundeindvirkning/Har det indvirkning på mig?

Det var kun de kunder, der havde aktiveret den nye Multiposting.fr-service, der blev påvirket.

#### Løsning/Kan jeg komme uden om dette?

Der var ingen løsning på problemet.

#### Foranstaltninger og handlinger/Hvad gør EasyCruit-teamet ved problemet?

Multiposting.fr-servicen blev repareret og den fungerer nu normalt. EasyCruit-teamet vil fortsat overvåge den i den næste uges tid.

Hvi du har spørgsmål til dette, er du velkommen til at kontakte os.

## Visma EasyCruit Support

Miljøet giver dig mulighed for at logge supportsager (spørgsmål) og overvåge dets status. Hvis du ikke har adgang til miljøet, skal du kontakte din administrator eller EasyCruits support.

[Norsk portal-login](https://community.visma.no/)

[Alle andre landes portal-login](https://visma.force.com/customers/login)

## Notifikationer

### EasyCruit-migrering til et Visma-hostet miljø

#### Opdatering - 23/04/2017

Migreringen til vores nye datacenter er blevet gennemført, og alle kunder kører nu på den nye platform.

Vi oplever imidlertid stadig problemer med at modtage testresultater fra SHL og Assessio. Vi arbejder på at udbedre dette hurtigst muligt og holder dig opdateret på denne side.

Opdatering 24/04/2017 09:30 CET: Vi modtager igen testresultater fra SHL og Assessio . Disse resultater stammer imidlertid kun fra nye tests og alle de tests, der er blevet kørt af kandidater i løbet af lørdag eftermiddag og søndag er ikke blevet opdateret i EasyCruit. Vi arbejder i øjeblikket på at udbedre dette.

#### Opdatering - 11/04/2017

Som en del af migreringen til Visma-miljøet sker der ændringer i den måde, hvormed EasyCruit håndterer afsenderpolitikrammerne for e-mail, som der skrives i EasyCruit.

Der dannes et SPF-register i Visma-miljøet og dette kan inkluderes som en del af dit eget SPF-register for at undgå, at du skal angive de individuelle indtastninger. Her er et eksempel:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Bemærk, at et gammel register ikke må fjernes, før efter migreringen har fundet sted.

#### Opdatering - 28/03/2017

Som tidligere annonceret er migreringen af data fra Lumesse til Vismas værtsmiljø i gang. Migreringen af pilotkunderne er nu vellykket afsluttet.

Med udgangspunkt i de erfaringer vi fik i løbet af pilotperioden, kan vi se, at tiden beregnet til migreringen er længere, end oprindeligt forventet.

Den planlagte nedetid er derfor blevet ændret til lørdag 22. april klokken 16:00 - søndag 23. april klokken 06:00 CEST.

#### Oversigt

I 2016 købte Visma EasyCruit fra Lumesse. Efter grundige forberedelser er vi endelige ved at rykke EasyCruit fra Lumesse og til et Visma-værtsmiljø. Migreringen sker i faser fra midten af marts til midten af april.

EasyCruit-servicen er tilgængelig i løbet af migreringen med undtagelse af i den planlagte nedetid lørdag 22. april klokken 16:00 - søndag 23. april klokken 06:00 CEST. På denne side kan du se vigtige opdateringer og status for migreringen.

Du som kunde burde ikke blive påvirket af denne ændring, med mindre du har hvidlistet EasyCruit-e-mailserverens IP i dit SPF-register eller dit firewall-/spam-filter. Efter migreringen ændres e-mailserveradressen sig og du skal opdatere alle hvidlister med den nye adresse. IP-adresserne bliver på annonceret forud for migreringen den 22. april.

Du skal navigere til: Visma Trust-Center/Transparency for opdateringsoplysninger vedrørende vores værtsmiljø og bearbejdning af data. Sørg for, at du deler disse oplysninger med alle relevante brugere i din it-afdeling. Hvis du har spørgsmål - kontakt din account manager eller support.

#### Nye mailserver-IP-adresser

Da EasyCruit flyttes til et Visma-værtsmiljø, ændrer mailserver-IP-adressen sig på tidspunktet for migrering.

Alle de kunder, der i øjeblikket anvender SPF-registre til at bekræfte EasyCruit som gyldig afsender, skal tilføje nye IP-adresser til deres SPF-register. Dette er en manuel ændring, der foretages af din it-administrator. Den gamle IP-adresse, 62.209.53.50, må ikke fjernes, før migreringen har fundet sted.

Yderligere IP-adresser kan til enhver tid tilføjes fra nu af. For at sikre, at der ikke er forstyrrelser i de e-mails, der sendes fra EasyCruit, skal dette gøres inden 21. april.

De nye IP-adresser er:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

Som en del af migreringen er der blevet oprettet et SPF-register, der kan inkluderes i stedet for at tilføje IP-adresser manuelt. Eksempel på dette: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Bemærk, at et gammel register ikke må fjernes, før efter migreringen har fundet sted.

#### DNS-spredning

Da EasyCruit flyttes fra en værtsudbyder til en anden, får alle serverne i systemet nye IP-adresser.

Vi forventer, at spredningen af de nye IP-adresser til DNS-servere sker i løbet af nedetiden og derfor ikke giver kunderne problemer.

Det er imidlertid muligt, at visse servere ikke har fået de nye IP-adresser, eller at en kunde anvender lokale DNS-registre. I disse scenarier kan det være nødvendigt, at en kunde renser den lokale cache eller anvender en anden DNS-server, indtil den almindelige er blevet opdateret.

#### Nye IP-adresser til udgående trafik

Da EasyCruit flyttes fra en værtsudbyder til en anden, får alle serverne i systemet nye IP-adresser.

Dette inkluderer de servere, der foretager de udgående forbindelser, dvs. publiceringskanalintegrationer og evalueringsintegrationer.

Sammenlignet med hvordan EasyCruit kører i dag sker forbindelserne fremover fra en række IP-adresser frem for bare en enkelt. Hvis integrationspartneren foretager hvidlistning, skal vedkommende derfor opdatere firewallen og anvende de nye ændringer.

### Driftsproblemnotifikationer 31.8.2016: 18:43 CEST LØST

Problemerne er nu løst og alle ansøgere bør nu kunne ansøge på alle stillinger.

Bemærk, at for at implementere løsningen skal serverne genstartes. Dette kan have foranlediget en kort afbrydelse i servicen. Vi beklager den ulejlighed, dette kan have medført.

#### Driftsproblemnotifikationer 31.8.2016: 14:46 CEST

Vi oplever i øjeblikket forstyrrelser i vores EasyCruit-service. Problemet forhindrer visse kandidater i at gennemføre deres ansøgninger. Dette sker, hvis felterne uddannelse og erfaring gøres obligatoriske i projektet. Vi kan forvisse dig om, at vi arbejder på højtryk fo at løse problemet og vi beklager den ulejlighed, det har medført for dig.

### Driftsproblemnotifikation - problem med sikkerhedscertifikat

Driftsproblemnotifikation - problem med sikkerhedscertifikat, 14.10.2016 13.13 CEST

Udstederen af vores sikkerhedscertifikat, GlobalSign, oplever en fejl, der påvirker EasyCruit og andre servicer. Brugere og kandidater kan derfor i øjeblikket opleve fejl, når de forsøger at få adgang til EasyCruit-servicen.

GlobalSign arbejder på at løse problemet, men grundet caching-problemer kan det tage op til 4 dage at udbedre problemet.

Hvis du ikke kan vente, kan du følge denne vejledning på GlobalSigns hjemmeside, der hjælper dig med at rense den relevante cache:

[https://support.globalsign.com/custo...ticles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

Vi beklager den ulejlighed, dette har medført for dig.

### Visma EasyCruit vedligeholdelsesnotifikation 05.06.2017 21.00-21.10 CEST

Vedligeholdelse af Visma EasyCruit vil blive foretaget 5. juni 2017 mellem 21:00 og 21:10 CEST. I denne periode kan EasyCruit Visma ikke bruges.

Brugerne kan ikke logge på systemet og kandidater kan ikke bruge karrierecenter eller søge på ledige stillinger.

Vi vil gerne undskylde for den ulejlighed, dette har medført for dig.

Hvis du har spørgsmål vedrørende denne vedligeholdelse, bedes du rette henvendelse til din lokale EasyCruit Visma support.

### Driftsproblemnotifikation - opdatering om problemer med ydeevne 17.01.2017

Visma EasyCruit oplever i øjeblikket forstyrrelser i servicen, hvilket resulterer i længere svartid for systemets brugere. Vi kan forvisse dig om, at vi arbejder på højtryk fo at løse problemet og vi beklager den ulejlighed, det har medført for dig.

Vores udviklingsteam har dedikeret ressourcerne og disse problemer har højeste prioritet.

Ved udgangen af uge tilføjer vi mere hukommelse som en af løsningerne for at øge svartiden.

### Visma EasyCruit vedligeholdelsesnotifikation 14.03.2017 18.30-19.00 CET

Vedligeholdelse af memcache vil blive foretaget 14. marts 2017 mellem 18:30 og 19:00 CET. I denne periode kan EasyCruit ikke bruges.

Brugerne kan ikke logge på systemet og kandidater kan ikke bruge karrierecenter eller søge på ledige stillinger.

Vi vil gerne undskylde for den ulejlighed, dette har medført for dig.

Hvis du har spørgsmål vedrørende denne vedligeholdelse, bedes du rette henvendelse til din lokale EasyCruit support.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODkzMDgxODRdfQ==
-->