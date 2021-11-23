# Meklēšanas veidnes

Ar meklēšanas veidņu palīdzību EasyCruit administratori var izveidot veidnes, kuras personāla atlases speciālisti var izmantot kandidātu meklēšanai datu bāzē. Šī funkcija ir noderīga uzņēmumiem ar lielu reģistrēto kandidātu skaitu vai arī kad jāmeklē specifisku prasmju kopa. Atkarībā no meklēšanas veidnē iekļautās opcijas, vērtības var ievadīti brīvā teksta laukos, ko atlasa no aizpildītiem sarakstiem, jautājumu rezultātiem un augšupielādētiem failiem.

Piemēram, meklēšanas veidnes sadaļa  Darba pieredze  sniedz lietotājam iespēju izvēlēties no nolaižamiem sarakstiem, vairāku izvēļu nolaižamiem sarakstiem un brīvā teksta laukiem.

Informāciju par meklēšanu skatīt sadaļā  [Kandidātu meklēšana](../getting-started/searching_for_candidates.htm).

#### Meklēšanas veidnes izveidošana

1.  Rīkjoslā  noklikšķiniet uz  Iestatījumi  un tad uz  Meklēšanas veidne.
2.  Lai izveidotu pilnīgi jaunu meklēšanas veidni, sarakstam  Izvēlēties meklēšanas veidni  jābūt iestatītam uz  Atlasīt  
    - vai -  
    lai izveidotu meklēšanas veidni uz esošas veidnes bāzes, atlasiet to no saraksta  Izvēlēties meklēšanas veidni.
3.  Ievadiet meklēšanas veidnes nosaukumu laukā  Saglabāt meklējumu kā.
4.  Noklikšķiniet uz bultiņas blakus katram virsrakstam, lai izvērstu sadaļā pieejamās opcijas.
5.  Izvēlēties vajadzīgās meklēšanas parametru vērtības.  
    Katrai sadaļai, kurai ir atlasīti meklēšanas parametri, virsraksta rindā ir sarkana zvaigznīte.
6.  Noklikšķiniet uz  Saglabāt veidni, lai saglabātu jauno veidni.

#### Esošas meklēšanas veidnes rediģēšana

1.  Rīkjoslā  noklikšķiniet uz  Iestatījumi  un tad uz  Meklēšanas veidnes.
2.  Sarakstā  Izvēlēties meklēšanas veidni  atlasiet rediģējamo veidni.
3.  Noklikšķiniet uz bultiņas blakus katram virsrakstam, lai izvērstu sadaļā pieejamās opcijas.  
    Tiek parādīta meklēšanas veidne ar to pašu sadaļu, kas bija izvērsta tad, kad tā tika saglabāta pēdējo reizi.
4.  Izvēlēties vajadzīgās meklēšanas parametru vērtības.
5.  Noklikšķiniet uz  Atjaunināt veidni, lai saglabātu izmaiņas.

#### Meklēšanas veidnes dzēšana

1.  Rīkjoslā  noklikšķiniet uz  Iestatījumi  un tad uz  Meklēšanas veidnes.
2.  Sarakstā  Izvēlēties meklēšanas veidni  atlasiet dzēšamo veidni.
3.  Noklikšķiniet uz  Dzēst veidni  un pēc tam uz  Labi, kad parādās uzvedne apstiprināt dzēšanu.

#### Tiešo saišu izmantošana meklēšanai

1.  Sākumlapā  noklikšķiniet uz pluss ikonas, lai izvērstu rūtiņu  Tiešās saites uz meklēšanu.
2.  Sarakstā  Meklēšanas veidnes  vai  Saglabātie meklējumi  noklikšķiniet uz meklēšanas vienuma, lai parādītu lapu  Kandidātu meklēšana.
3.  Pabeidziet meklēšanu, kā nepieciešams.  
    Tiešo saišu meklēšanas opcija nav pieejama pēc noklusējuma, un tā ir jāiespējo mūsu sistēmā.

#### Meklēšanas kritēriji – apsvērumi un piemēri

Iestatot meklēšanas veidņu kritērijus, jāņem vērā vairāki faktori, kas ietekmē rezultātus. Ja netiek parādīti vajadzīgie rezultāti, tam var būt šādi iemesli:

Meklējamā vārdā jābūt vismaz trim rakstzīmēm; tādas rakstzīmes kā "+" un "-" netiek meklētas un tāpēc tās netiek iekļautas minimālajā rakstzīmju skaitā. Piemēram, programmēšanas prasmes "C++" nevar iekļaut teksta meklēšanā.

-   Tādi vienkārši vārdi kā "un" vai "vārds" arī tiek izslēgti no meklēšana.

Meklēšanas kritērijos var iekļaut vairākus operatorus. Tādējādi var veikt mērķtiecīgāku meklēšanu, kas ietver:

+

Pluss zīme norāda, ka sekojošam vārdam jābūt ietvertam

-

Mīnuss zīme norāda, ka sekojošais vārds nedrīkst būt ietverts

()

Ar iekavu palīdzību vārdus var sagrupēt pakārtotos izteicienos

*

Zvaigznīte ir aizstājējzīme, ko var pievienot meklējamā vārda beigās.

"

Dubultpēdiņās iekļauta frāze ir jāatrod precīzi.

Lai ilustrētu iepriekšminēto, turpmāk ir parādīti piemēri, kā dažādi meklēšanas kritēriji ģenerē atšķirīgus rezultātus:

pārdošanas nodaļa

Meklēšanas rezultātā ir vismaz viens no diviem vārdiem

+pārdošanas +nodaļa

Meklēšanas rezultātā ir abi vārdi

+pārdošanas nodaļa

Meklēšanas rezultātā ietverts vārds "pārdošanas", bet tas ir vērtēts augstāk, ja ir iekļauts arī vārds "nodaļa"

+pārdošanas -nodaļa

Meklēšanas rezultātā ir vārds "pārdošanas", bet vārda "nodaļa" nav

+pārdošanas ~nodaļa

Meklēšanas rezultātā ietverts vārds "pārdošanas", bet tas ir vērtēts zemāk, ja ir iekļauts arī vārds "nodaļa"

+pārdošanas+(>nodaļa<spec)

Meklēšanas rezultātā ir vārdi "pārdošanas" un "nodaļa" vai "nodaļa" un "spec" jebkurā kārtībā, bet vārdi "pārdošanas nodaļa" ir vērtēti augstāk nekā "pārdošanas spec"

pārd*

Meklēšanas rezultātā ir vārdi "pārdošanas" un "pārdevējs"

"pārdošanas nodaļa"

Meklēšanas rezultātā ir precīza frāze "pārdošanas nodaļa"

##### Skatīt arī:

![](../Resources/Images/icon-document-link.png)  [Kandidātu meklēšana](searching_for_candidates.htm)
![](../Resources/Images/icon-document-link.png)  [Darbu kategorijas](job_categories.htm)
![](../Resources/Images/icon-document-link.png)  [Papildu jautājumi](additional_questions.htm)
![](../Resources/Images/icon-document-link.png)  [Lietotāji: izveidot, rediģēt, dzēst](users_create_edit_delete.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQyNzg5MTkzM119
-->