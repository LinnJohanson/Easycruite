# Paziņojumi

Šajā sadaļā atrodas sistēmas paziņojumi par zināmām problēmām un uzlabojumiem.

## EasyCruit paziņojums – apziņošana. fr nestabils pakalpojums – ATRISINĀTS

#### Problēmas apraksta / Kas noticis?

Sludinājumu izplatīšanas pakalpjums, ko sniedz  Multiposting.fr  bija nestabils. Problēma radās pēc sludinājumu izplatīšanas pakalpojuma migrācijas uz jaunu datu centru Lieldienu nedēļas nogalē. Klientiem, kam ir iespējota funkcija Multiposting.fr sludinājuma lapas ielādes laiks bija ilgāks nekā parasti. Turklāt, kad klienti izvēlējās nosūtīt Sludinājuma lapu ar Multiposting.fr, sludinājuma izvietošana aizņēma līdz pat 3 minūtēm un varēja arī neizdoties – parādījās kļūdas ziņojums 801.

#### Ietekme uz klientu / Vai tas skar mani?

Tas ietekmēja tikai tos klientus, kam bija iespējots jaunia spakalpojums Multiposting.fr.

#### Aprisinājums / Vai es varu šo problēmu novērsts?

Šo problēmu nevarēja aprisināt.

#### Pasākumi un darbības / Kādus pasākumus veic EasyCruit komanda?

Multiposting.fr pakalpojums tika salabots, darbība normalizējās. EasyCruit turpinās izraudzīt darbību nākamnedēļ.

Ja jums rodas kādi jautājumi, lūdzu, sazinieties ar mums.

## Visma EasyCruit atbalsta nodaļa

Sadaļā Community jūs varat pieteikt atbalstu (problēmas) un sekot līdzi darbību statusam. Ja jums nav piekļuves sadaļai Community, lūdzu, sazinieties ar EasyCruit atbalsta dienesta administratoru.

[Norvēģijas Community portāla pieteikšanās informācija](https://community.visma.no/)

[Pārējo valstu Community portāla pieteikšanās informācija](https://visma.force.com/customers/login)

## Paziņojumi

### EasyCruit migrācija uz Visma izmitināto vidi

#### Atjauninājums – 23/04/2017

Ir pabeigta migrācija uz mūsu jauno datu centru, un visi klienti pašreiz darbojas jaunajā platformā.

Tomēr ir radušās problēmas ar testu rezultātu saņemšanu no SHL un Assessio. Mēs centīsimies tās novērst pēc iespējas drīzāk un sniegsim jaunāko informāciju šajā lapā.

Atjauninājums 24/04/2017 09:30 CET: mēs atkal saņemam testu rezultātus no SHL un Assessio. Taču tie ir tikai jauno testu rezultāti; testi, ko kandidāti veica sestdien pēcpusdienā un svētdien, vēl nav atjaunināti EasyCruit sistēmā. Mēs cenšamies šo problēmu novērst.

#### Atjauninājums - 11/04/2017

Pārejot uz Visma mitināto vidi, mainīsies veids, kādā EasyCruit apstrādās Sūtītāja politikas struktūru (SPF) attiecībā uz e-pastiem, ko jūs rakstāt EasyCruit sistēmā.

Visma mitinātajā vidē tiks izveidots SPF ieraksts, un to varēs iekļaut jūsu SPF ieraksta sastāvā, lai nevajadzētu iekļaut atsevišķus ierakstus. Piemērs:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Lūdzu, ņemiet vērā, ka vecos ierakstus nedrīkst noņemt, kamēr nav pabeigta migrācija.

#### Atjauninājums – 28/03/2017

Ka ziņots iepriekš, pašreiz notiek datu migrācija no Lumese uz Vismas mitināto vidi. Ir sekmīgi pabeigta pirmo klientu migrācija.

Balstoties uz izmēģinājuma perioda pieredzi, mēs konstatējām, ka migrācijai vajadzīgais laiks pārsniegs sākotnēji aprēķināto.

Plānotais dīkstāves laiks ir mainīts: sestdiena 22.4 plkst.16:00 - svētdiena 23.4 plkst. 06:00 CEST.

#### Pārskats

2016. gadā Visma iegādājās EasyCruit no Lumesse. Pēc rūpīgas sagatavošanās mēs pārvietojam EasyCruit no Lumesse uz Visma mitināto vidi. Migrācija notiks no marta vidus līdz aprīļa vidum.

EasyCruit pakalpojumi migrācijas laikā būs pieejami, izņemot plānoto dīkstāves laiku no sestdienas 22.4 plkst. 6.00 līdz svētdienai 23.4 plkst. 06.00 CEST. Informācija par svarīgiem atjauninājumiem un migrācijas statusu atrodama šajā lapā.

Klientus šīs izmaiņas neietekmēs, ja vien neesat iekļāvuši EasyCruit e-pasta servera IP savā SPF ierakstā vai ugunsmūra/surogātpasta filtrā. Pēc migrācijas e-pasta servera IP adrese mainīsies, un jums vajadzēs atjaunināt baltos sarakstus ar jauno adresi. IP adrese tiks paziņota pirms migrācijas 22. aprīlī.

Lūdzu, dodieties uz sadaļu: Visma Trust-Center/Transparency for updated information regarding our hosting environment and processing of data. Lūdzu, nododiet šo informāciju visiem attiecīgajiem lietotājiem jūsu IT nodaļā. Jautājumu gadījumā sazinieties ar klientu konsultantu vai atbalsta nodaļu.

#### Jaunās pasta servera IP

Pārvietojot EasyCruit tuz Visma mitināšanas vidi, pasta servera IP mainīsies līdz ar migrāciju.

Visiem klientiem, kas pašreiz izmanto SPF ierakstus, lai apstiprinātu EasyCruit kā derīgu nosūtītāju, būs jāpievieno jaunās IP saviem SPF ierakstiem. Izmaiņas manuāli jāveic IT administratoram. Veco IP 62.209.53.50 nedrīkst noņemt, kamēr nav pabeigta migrācija.

Papildu IP varēs pievienot pēc tam. Lai e-pastu sūtīšana no EasyCruit netiktu traucēta, tas ir jāizdara līdz 21. aprīlim.

Jaunās IP ir šādas:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

Migrācijas ietvaros ir izveidots SPF ieraksts, ko var izmantot, lai nevajadzētu manuāli pievienot atsevišķas IP adreses. Piemērs, kā to var izdarīt: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Lūdzu, ņemiet vērā, ka vecos ierakstus nedrīkst noņemt, kamēr nav pabeigta migrācija.

#### DNS izplatīšana

EasyCruit sistēma tiek pārvietota pie cita izmitināšanas pakalpojumu sniedzēja, visiem serveriem sistēmā tiks piešķirtas jaunas IP adreses.

Paredzēts, ka jauno IP adrešu izplatīšana DNS serveros notiks dīkstāves laikā un tāpēc neradīs klientiem nekādas problēmas.

Taču pastāv iespēja, ka daži serveri nesaņems jaunās IP adreses vai ka klients izmanto lokālā kešatmiņā saglabātus DNS ierakstus. Tādā gadījumā klientam vajadzēs notīrīt vietējo kešatmiņu vai izamntota citu DNS serveri, kamēr parastais serveris nav atjaunināts.

#### Jaunas IP adreses izejošai datplūsmai

EasyCruit sistēma tiek pārvietota pie cita izmitināšanas pakalpojumu sniedzēja, visiem serveriem sistēmā tiks piešķirtas jaunas IP adreses.

Tas ietver serveru, kuri izveido izejošus savienojumus, piemēram, darba sludinājumu dēļu integrāciju un novērtējumu integrāciju.

Salīdzinājumā ar līdzšinējo EasyCruit darbību, savienojumi tiks veidoti ar vairākām IP adresēm , nevis tikai ar vienu. Ja integrācijas partneris sastāda balso sarakstu, tam vajadzēs atjaunināt savu ugunsmūri, lai piemērotos šīm izmaiņām.

### Paziņojumi par darbības problēmām 31.8.2016: 18:43 CEST ATRISINĀTAS

Šīs problēmas ir atrisinātas, un visi kandidāti var pieteikties visām vakancēm.

Lūdzu, ņemiet vērā, ka risinājumu ieviešanai bija nepieciešams restartēt serverus. Tas varēja izraisīt īslaicīgu pakalpojuma pārtraukumu. Atvainojamies par sagādātajām neērtībām.

#### Paziņojums par darbības problēmām 31.8.2016: 14:46 CEST

Pašreiz ir traucēta EasyCruit pakalpojuma darbība. Traucējumi liedz kandidātiem iesniegt pieteikumus. Tas notiek, ja izglītības un pieredzes lauki projektā ir norādīti kā obligāti. Mēs centīsimies novērst šo problēmu pēc iespējas drīzāk. Atvainojamies par sagādātajām neērtībām.

### Paziņojums par darbības traucējumiem – drošības sertifikāta problēma

Paziņojums par darbības traucējumiem – drošības sertifikāta problēma 14.10.2016 13.13 CEST

Drošības sertifikāta izdevējam GlobalSign radās kļūda, kas ietekmēja EasyCruit un citus pakalpojumus. Tāpēc lietotāji un kandidāti saņem kļūdas ziņojumus, kad viņi mēģina piekļūt EasyCruit pakalpojumam.

GlobalSign cenšas novērst problēmu, bet sakarā ar kešatmiņas problēmām problēmas pilnīgai novēršanai vajadzēs līdz pat 4 dienām.

Ja nevarat gaidīt, jūs varat izmantot GlobalSign vietnē sniegtos norādījumus, kas palīdzēs jums attīrīt attiecīgo kešatmiņu:

[https://support.globalsign.com/custo...ticles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

Atvainojamies par sagādātajām neērtībām.

### Visma EasyCruit apkopes paziņojums 05.06.2017 21.00-21.10 CEST

2017. gada 5. jūnijā no plkst. 21.00 līdz 21.10 CEST tiks veikta Visma EasyCruit apkope. Šai laikā Visma EasyCruit pakalpojumi nebūs pieejami.

Lietotāji nevarēs pieteikties sistēmā, bet kandidāti nevarēs izmantot karjeras centru un pieteikties vakancēm.

Atvainojamies par sagādātajām neērtībām.

Ja jums rodas jautājumi par šo apkopi, lūdzu, sazinieties ar vietējo Visma Easycruit atbalsta nodaļu.

### Paziņojums par darbības problēmām - papildinājums 17.01.2017

Visma EasyCruit pakalpojumu darbība pašreiz ir traucēta – sistēmas atbildes laiks ir garāks. Mēs centīsimies novērst šo problēmu pēc iespējas drīzāk. Atvainojamies par sagādātajām neērtībām.

Mūsu izstrādes komanda ir atvēlējusi papildu resursus noteikusi šis problēmas atrisināšanu kā prioritāru.

Šis nedēļas beigās mēs pievienosim papildu atmiņu, lai uzlabotu atbildes laiku.

### Visma EasyCruit apkopes paziņojums 14.03.2017 18.30-19.00 CET

2017. gada 14. martā no plkst. 18.30 līdz 19.00 CET tiks veikta Visma EasyCruit apkope. Šai laikā EasyCruit pakalpojumi nebūs pieejami.

Lietotāji nevarēs pieteikties sistēmā, bet kandidāti nevarēs izmantot karjeras centru un pieteikties vakancēm.

Atvainojamies par sagādātajām neērtībām.

Ja jums rodas jautājumi par šo apkopi, lūdzu, sazinieties ar vietējo Easycruit atbalsta nodaļu.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkzODY3MTcwXX0=
-->