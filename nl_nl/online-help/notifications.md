# Meldingen

Dit hoofdstuk bevat de systeemmeldingen over bekende problemen en verbeteringen.

## EasyCruit-melding - Onregelmatige service Multiposting.fr - OPGELOST fr intermittent service - RESOLVED

#### Probleembeschrijving / Wat is het probleem?

De vacatureverspreidingsservice van  Multiposting.fr  was onregelmatig. Dit probleem deed zich voor na het voltooien van een migratie van hun vacatureverspreidingservice naar een nieuw datacenter gedurende het paasweekend. De klanten die het gebruik van de Multiposting.fr-functie ingeschakeld hebben, ondervonden langer dan verwachte laadtijden voor de publicatiepagina. Als de klant op de publicatiepagina koos om te publiceren via Multiposting.fr, kon het publiceren bovendien tot 3 minuten duren en soms niet lukken (foutmelding 801).

#### Gevolgen voor de klant / Heeft dit gevolgen voor mij?

Dit had enkel gevolgen voor de klanten die de nieuwe Multiposting.fr-service ingeschakeld hebben.

#### Omzeilen / Kan ik dit probleem omzeilen?

Dit probleem kon niet omzeild worden.

#### Maatregelen en acties / Wat doet het EasyCruit-team eraan?

De Multiposting.fr-service is hersteld en functioneert weer normaal. Het EasyCruit-team blijft de beschikbaarheid de komende week controleren.

Mocht u vragen hebben hierover, neem dan gerust contact met ons op.

## Visma EasyCruit-support

Via de Community kunt u supportcases (problemen) loggen en de status bekijken. Als u geen toegang heeft tot de Community, neem dan contact op met uw administrator of met het EasyCruit-supportteam.

[Inloggen op Noorse Community Portal](https://community.visma.no/)

[Inloggen op Community Portal voor alle overige landen](https://visma.force.com/customers/login)

## Meldingen

### EasyCruit-migratie naar Visma-hostingomgeving

#### Update - 23/04/2017

De migratie van ons nieuwe datacenter is voltooid en alle klanten zijn nu live op het nieuwe platform.

We ondervinden op dit moment echter problemen bij het ontvangen van testresultaten van SHL en Assessio. We werken eraan dit zo snel mogelijk op te lossen en houden u op de hoogte op deze pagina.

Update 24/04/2017 09:30 CET: We ontvangen nu opnieuw testresultaten van SHL en Assessio. Deze resultaten zijn echter enkel van nieuwe tests en alle tests die zaterdagnamiddag en zondag gemaakt zijn door kandidaten zijn nog niet geüpdatet in EasyCruit. We werken op dit moment aan een oplossing.

#### Update - 11/04/2017

Als onderdeel van de migratie naar de Visma-hostingomgeving, zal de manier veranderen waarop EasyCruit het Sender Policy Framework voor e-mails die u schrijft in EasyCruit verwerkt.

Er wordt een SPF-record aangemaakt in de Visma-hostingomgeving en deze kan toegevoegd worden als een deel van uw eigen SPF-record zodat de individuele invoeren niet weergegeven hoeven te worden. Voorbeeld:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Wij wijzen u erop dat oude records pas verwijderd mogen worden nadat de migratie plaatsgevonden heeft.

#### Update - 28/03/2017

Zoals eerder aangekondigd is de migratie van gegevens van Lumesse naar de Visma-hostingomgeving in volle gang. De migratie van de testklanten is nu succesvol afgerond.

Op basis van de ervaring die opgedaan is in deze testperiode, zien we dat de tijd voor het migreren langer is dan oorspronkelijk verwacht.

De geplande downtime is daarom van zaterdag 22.4 16:00 tot zondag 23.4 06:00 CEST geworden.

#### Overzicht

In 2016 nam Visma EasyCruit over van Lumesse. Na grondige voorbereidingen kunnen we EasyCruit eindelijk migreren naar een Visma-hostingomgeving. De migratie gebeurt in stappen van half maart tot half april.

De EasyCruit-service blijft beschikbaar tijdens de migratieperiode, met uitzondering van een geplande downtime van zaterdag 22.4 16.00 tot zondag 23.4 06.00 CEST. Belangrijke updates en de status van de migratie vindt u op deze pagina.

U hoeft als klant geen gevolgen te ondervinden van deze wijziging, behalve als het IP van de EasyCruit-mailserver op uw veilige lijst staat in uw SPF-record of firewall/spamfilter. Na de migratie zal het IP-adres van de e-mailserver wijzigen en moet u het nieuwe adres toevoegen aan uw veilige lijsten. Het IP-adres wordt voorafgaand aan de migratie op 22 april bekendgemaakt.

Gelieve naar Visma Trust-Center/Transparency te gaan voor geüpdatete informatie over onze hostingomgeving en de verwerking van gegevens. Wij verzoeken u deze informatie te delen met alle relevante gebruikers en uw IT-afdeling. Mocht u vragen hebben, neem dan contact op met uw accountmanager of supportteam.

#### Nieuwe mailserver-IP's

Als EasyCruit verplaatst wordt naar de Visma-hostingomgeving, wijzigt het mailserver-IP op het moment van de migratie.

Alle klanten die momenteel gebruik maken van SPF-records om EasyCruit te bevestigen als een geldige afzender moeten de nieuwe IP's toevoegen aan hun SPF-record. Dit wordt handmatig gedaan door uw IT-administrator. Het oude IP, 62.209.53.50, mag niet verwijderd worden tot de migratie heeft plaatsgevonden.

De aanvullende IP's kunnen vanaf nu op elk moment toegevoegd worden. Om onderbrekingen van de e-mails verstuurd vanuit EasyCruit te voorkomen, dient dit te gebeuren tegen 21 april.

De nieuwe IP’s zijn:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

Als onderdeel van deze migratie is een SPF-record aangemaakt dat toegevoegd kan worden in plaats van handmatig invoeren van de verschillende IP’s. Voorbeeld van hoe dit toegevoegd wordt: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Wij wijzen u erop dat oude records pas verwijderd mogen worden nadat de migratie plaatsgevonden heeft.

#### DNS-doorgifte

Als EasyCruit verplaatst wordt van de ene hostingprovider naar de andere, krijgen alle servers in het systeem nieuwe IP's.

De verwachting is dat de doorgifte van de nieuwe IP's aan de DNS-servers zal plaatsvinden tijdens de downtime en dus geen problemen voor de klanten zal veroorzaken.

Het is echter mogelijk dat bepaalde servers de nieuwe IP's niet ontvangen hebben of dat een klant DNS-records in de lokale cache gebruiken. In deze gevallen kan het nodig zijn dat de klant de lokale cache wist of een alternatieve DNS-server gebruikt tot hun normale geüpdatet is.

#### Nieuwe IP’s voor uitgaand verkeer

Als EasyCruit verplaatst wordt van de ene hostingprovider naar de andere, krijgen alle servers in het systeem nieuwe IP's.

Dit is inclusief de servers die uitgaande verbindingen maken, bv. jobboardintegraties en assessmentintegraties.

In vergelijking met hoe EasyCruit nu werkt, zullen de verbindingen van verschillende IP's komen in plaats van één. Als de veilige lijst beheerd wordt door de integratiepartner, dan moet deze zijn firewall updaten voor deze wijzigingen.

### Melding operationele problemen 31.8.2016: 18:43 CEST OPGELOST

De problemen zijn opgelost en alle sollicitanten moeten nu weer kunnen solliciteren op alle posities.

Opmerking: Om de oplossing te implementeren moesten alle servers opnieuw opgestart worden. Dit kan een korte onderbreking van de service veroorzaakt hebben. Onze excuses voor het ongemak.

#### Melding operationele problemen 31.8.2016: 14:46 OPGELOST

Wij ondervinden momenteel enige verstoring van de EasyCruit-service. Het probleem verhindert dat bepaalde kandidaten hun sollicitatie kunnen voltooien. Dit komt voor als de velden Opleiding en Ervaring verplicht zijn in het project. Wij verzekeren u dat we eraan werken om dit probleem zo snel mogelijk op te lossen en bieden onze excuses aan voor het ongemak.

### Melding operationele problemen - probleem met beveiligingscertificaat

Melding operationele problemen - probleem met beveiligingscertificaat 14.10.2016 13.13 CEST

De uitgever van ons beveiligingscertificaat, GlobalSign, heeft een storing waar EasyCruit en andere services hinder van ondervinden. Gebruikers en kandidaten kunnen hierdoor tijdelijk foutmeldingen krijgen als ze toegang proberen te krijgen tot de EasyCruit-service.

GlobalSign werkt aan een oplossing voor het probleem, maar door cachingproblemen kan het tot 4 dagen duren om het volledig op te lossen.

Als u niet kunt wachten, dan kunt u deze handleiding van GlobalSign volgen om de relevante cache te wissen:

[https://support.globalsign.com/custo...ticles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

Wij bieden onze excuses aan voor het ongemak.

### Visma EasyCruit-onderhoudsmelding 05.06.2017 21.00-21.10 CEST

Er zal onderhoud van EasyCruit plaatsvinden op 5 juni 2017 tussen 21.00 en 21.10 CEST. Visma EasyCruit is dan niet beschikbaar.

Gebruikers kunnen niet inloggen in het systeem en kandidaten kunnen het Career Center niet gebruiken en kunnen niet solliciteren op vacatures.

Wij bieden onze excuses aan voor het ongemak.

Mocht u vragen hebben over dit onderhoud, neem dan gerust contact op met uw lokale Visma EasyCruit-support.

### Melding operationele problemen - functioneringsproblemen update 17.01.2017

Visma EasyCruit ondervindt momenteel enige verstoring van de service die tot een langere responstijd voor systeemgebruikers leidt. Wij verzekeren u dat we eraan werken om dit probleem zo snel mogelijk op te lossen en bieden onze excuses aan voor het ongemak.

Ons ontwikkelingsteam beschikt over gespecialiseerde middelen en geeft de hoogste prioriteit aan dit probleem.

Aan het einde van deze week zullen we extra geheugen toevoegen als een van de acties voor het verbeteren van de responstijd.

### EasyCruit-onderhoudsmelding 14.03.2017 18.30-19.00 CET

Er zal memcache-onderhoud plaatsvinden op 14 maart 2017 tussen 18.30 en 19.00 CET. EasyCruit is dan niet beschikbaar.

Gebruikers kunnen niet inloggen in het systeem en kandidaten kunnen het Career Center niet gebruiken en kunnen niet solliciteren op vacatures.

Wij bieden onze excuses aan voor het ongemak.

Mocht u vragen hebben over dit onderhoud, neem dan gerust contact op met uw lokale EasyCruit-support.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzk0NDk2MDFdfQ==
-->