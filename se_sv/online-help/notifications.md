
# Meddelanden

Det här avsnittet innehåller systemmeddelanden om kända problem eller förbättringar.

## EasyCruit-meddelande – Mulltiposting. fr intermittent service – ÅTGÄRDAT

#### Problembeskrivning/Vad är problemet?

Jobbdistributionstjänsten som tillhandahålls av  Multiposting.fr  tillhandahöll en intermittent service. Problemet uppstod efter att en flytt av deras jobbdistributionstjänst till ett nytt datacenter, som genomfördes under påskhelgen, slutförts. De kunder som har blivit aktiverade att använda funktionen Multiposting.fr, upplevde att det tog längre tid än väntat att ladda publiceringssidan. Dessutom, om kunden valde att publicera med användning av Multiposting.fr från publiceringssidan, kunde publiceringen ta upp till tre minuter och ibland lyckades den inte alls och ett 801-felmeddelande visades.

#### Kundpåverkan/Är jag påverkad?

Endast kunder som hade aktiverat den nya Multiposting.fr-tjänsten påverkades.

#### Tillfällig lösning/Kan jag kringgå detta på något sätt?

Det finns ingen tillfällig lösning på problemet.

#### Åtgärder och insatser/Vad gör EasyCruit-teamet för att lösa detta?

Multiposting.fr-tjänsten åtgärdades och fungerar nu som vanligt. EasyCruit-teamet kommer att fortsätta att övervaka prestandan nästa vecka.

Om du har några frågor om detta, tveka inte att kontakta oss.

## Visma EasyCruit Support

Du kan logga dina supportärenden (problem) i Community och övervaka deras status. Om du inte har tillgång till Community kontaktar du din administratör eller EasyCruit support

[Inloggning till den norska Community-portalen](https://community.visma.no/)

[Inloggning till Community-portalen för alla andra länder](https://visma.force.com/customers/login)

## Meddelanden

### EasyCruit flyttas till Vismas värdtjänstmiljö

#### Uppdaterat – 2017-04-23

Flytten till vårt nya datacenter har slutförts och alla kunder arbetar nu på den nya plattformen.

Vi upplever dock för närvarande problem med att ta emot testresultat från SHL och Assessio. Vi arbetar med att lösa detta så snart som möjligt och kommer att hålla dig uppdaterad på den här sidan.

Uppdatering 2017-04-24 09:30 CET: Vi får nu testresultat från SHL och Assessio igen. Dessa resultat kommer emellertid bara från nya tester och alla tester som genomfördes av kandidater under lördag eftermiddag och söndag har ännu inte uppdaterats i EasyCruit. Vi arbetar för närvarande på att lösa det här problemet.

#### Uppdaterat – 2017-11-04

Som ett led i flytten till Vismas värdtjänstmiljö kommer det att bli förändringar i hur EasyCruit hanterar ramverket Avsändarpolicy för e-postmeddelanden som du skriver i EasyCruit.

En SPF-post (Sender Policy Framework, SPF) kommer att skapas i den nya Visma-miljön och den kan infogas som en del av din egen SPF-post för att undvika att behöva lista enskilda poster. Här är ett exempel:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Observera att en gammal post inte ska tas bort förrän flytten är klar.

#### Uppdaterat – 2017-03-28

Som tidigare meddelats pågår överföring av data från Lumesse till Vismas värdtjänstmiljö. Flytten av pilotkunder har nu slutförts med lyckat resultat.

Baserat på erfarenheten från pilotperioden inser vi att tidsåtgången som beräknades för överföringen är längre än vad som ursprungligen förväntades.

Den planerade driftstoppstiden har därför ändrats till lördagen den 22 april kl. 16:00 - söndagen den 23 april kl. 06:00 CEST.

#### Översikt

Under 2016 förvärvade Visma EasyCruit från Lumesse. Efter noggrann förberedelse flyttar vi nu slutligen EasyCruit från Lumesse till Vismas värdtjänstmiljö. Flytten kommer att äga rum stegvis från mitten av mars till mitten av april.

EasyCruit-tjänsten kommer att vara tillgänglig under den här perioden, med undantag för ett planerat driftstopp lördagen den 22 april kl. 16.00 - söndag den 23 april kl. 06.00 CEST. Viktiga uppdateringar och status för flytten kommer att visas på den här sidan.

Du som kund ska inte påverkas av denna ändring, såvida du inte har vitlistat IP-adressen för EasyCruits e-postserver i din SPF-post eller brandvägg/spamfilter. Efter flytten ändras e-postserverns IP-adress och du måste uppdatera eventuella vitlistor med den nya adressen. IP-adressen kommer att meddelas före flytten den 22 april.

Vi ber dig att gå till: Visma Trust-Center/Transparency för uppdaterad information om vår värdtjänstmiljö och behandling av data. Dela denna information med alla relevanta användare och din IT-avdelning. Om du har några frågor – kontakta din kontoansvarige eller supporten.

#### Nya IP-adresser för e-postservern

Eftersom EasyCruit håller på att flyttas till Vismas värdtjänstmiljö, kommer e-postserverns IP-adress att ändras i och med flytten.

Alla kunder som nu använder SPF-poster för att bekräfta EasyCruit som en godkänd avsändare måste lägga till nya IP-adresser i sin SPF-post. Detta är en manuell ändring som utförs av din IT-administratör. Den gamla IP-adressen, 62.209.53.50, får inte tas bort innan flytten är klar.

De nya IP-adresserna kan läggas till när som helst från och med nu. För att säkerställa att det inte blir något avbrott i e-postflödet från EasyCruit, måste detta vara klart senast den 21 april.

De nya IP-adresserna är:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

Som ett led i den här flytten har en SPF-post skapats som kan inkluderas istället för att lägga till de individuella IP-adresserna manuellt. Exempel på hur denna kan inkluderas: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Observera att en gammal post inte ska tas bort förrän flytten är klar.

#### DNS-propagering

Eftersom EasyCruit håller på att flyttas från en leverantör av värdtjänster till en annan, kommer alla servrar i systemet att få nya IP-adresser.

Det förväntas att propageringen av de nya IP-adresserna till DNS-servrar kommer att ske under driftstopptiden och därför inte orsaka några problem för våra kunder.

Det kan dock hända att vissa servrar inte har fått de nya IP-adresserna eller att en kund använder lokalt cachade DNS-poster. I dessa fall kan en kund behöva tömma den lokala cachen eller använda en alternativ DNS-server tills deras ordinarie har blivit uppdaterad.

#### Nya IP-adresser för utgående trafik

Eftersom EasyCruit håller på att flyttas från en leverantör av värdtjänster till en annan, kommer alla servrar i systemet att få nya IP-adresser.

Detta inkluderar servrar som gör utgående anslutningar, t.ex. integreringar med publiceringskanaler och personlighetstester.

Jämfört med hur EasyCruit fungerar idag, kommer anslutningarna att komma från en rad IP-adresser i stället för en enda. Om vitlistor hanteras av integrationspartnern, skulle de därför behöva uppdatera sin brandvägg så att den innehåller dessa förändringar.

### Meddelanden om driftsstörningar 2016-08-31: 18:43 CEST LÖST

Problemen är nu lösta och alla kandidater bör nu kunna ansöka till alla tjänster.

Observera att för att implementera lösningen var det nödvändigt att starta om servrarna. Detta kan ha orsakat ett kort avbrott i tjänsten. Vi ber om ursäkt för eventuella olägenheter som detta orsakat.

#### Meddelanden om driftsstörningar 2016-08-31: 14:46 CEST

Vi upplever för närvarande vissa störningar i EasyCruit-tjänsten. Problemet förhindrar vissa kandidater från att slutföra sina ansökningar. Detta händer om utbildnings- och erfarenhetsfälten har gjorts obligatoriska i projektet. Vi försäkrar dig om att vi arbetar för att lösa problemet så fort vi kan och ber om ursäkt för den olägenhet som detta kan orsaka dig.

### Meddelanden om driftsstörningar – problem med säkerhetscertifikat

Meddelanden om driftsstörningar – problem med säkerhetscertifikat 2016-10-14 kl. 13.13 CEST

Utgivaren av vårt säkerhetscertifikat, GlobalSign, upplever ett fel som påverkar EasyCruit och andra tjänster. Användare och kandidater kan därför för närvarande få felmeddelanden när de försöker komma åt EasyCruit-tjänsten.

GlobalSign arbetar på att lösa problemet, men det kan ta upp till fyra dagar att åtgärda det fullständigt.

Om du inte kan vänta kan du följa den här guiden från GlobalSigns webbsida, som kommer att hjälpa dig att tömma relevant cache:

[https://support.globalsign.com/customer/portal/articles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

Vi ber om ursäkt för den olägenhet som detta kan orsaka dig.

### Visma EasyCruit underhållsmeddelande 2017-06-05 kl. 21.00-21.10 CEST

Underhåll av Visma EasyCruit kommer att utföras den 5 juni 2017 mellan kl. 21.00-21.10 CEST. Under den här tiden kommer Visma EasyCruit inte att vara tillgängligt.

Användare kommer inte att kunna logga in i systemet och kandidater kommer inte att kunna använda karriärcenter eller ansöka om lediga tjänster.

Vi vill be om ursäkt för den olägenhet som detta kan orsaka.

Tveka inte att kontakta din lokala Visma EasyCruit-support om du har några frågor om det här underhållet.

### Meddelanden om driftsstörningar – prestandaproblem uppdatering 2017-01-17

Visma EasyCruit upplever för närvarande en viss störning i tjänsten vilket resulterar i en längre svarstid för systemanvändare. Vi försäkrar dig om att vi arbetar för att lösa problemet så fort vi kan och ber om ursäkt för den olägenhet som detta kan orsaka dig.

Vårt utvecklingsteam har dedikerat resurser och ger detta problem högsta prioritet.

I slutet av denna vecka lägger vi till mer minne som en av åtgärderna för att förbättra svarstiden.

### Visma EasyCruit underhållsmeddelande 2017-03-14 kl. 18.30-19.00 CEST

Underhåll av Visma EasyCruit kommer att utföras den 14 mars 2017 mellan kl. 18.30-19.00 CET. Under den här tiden kommer EasyCruit inte att vara tillgängligt.

Användare kommer inte att kunna logga in i systemet och kandidater kommer inte att kunna använda karriärcenter eller ansöka om lediga tjänster.

Vi vill be om ursäkt för den olägenhet som detta kan orsaka.

Tveka inte att kontakta din lokala EasyCruit-support om du har några frågor om det här underhållet.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI3NTI2NTUwOF19
-->