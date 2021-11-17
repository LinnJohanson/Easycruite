# Meklēšanas kritēriji – apsvērumi un piemēri

Iestatot meklēšanas veidņu kritērijus, jāņem vērā vairāki faktori, kas ietekmē rezultātus. Ja netiek parādīti vajadzīgie rezultāti, tam var būt šādi iemesli:

-   Meklējamā vārdā jābūt vismaz trim rakstzīmēm; tādas rakstzīmes kā "+" un "-" netiek meklētas un tāpēc tās netiek iekļautas minimālajā rakstzīmju skaitā. Piemēram, programmēšanas prasmes "C++" nevar iekļaut teksta meklēšanā.
-   Tādi vienkārši vārdi kā "un" vai "vārds" arī tiek izslēgti no meklēšana.

Meklēšanas kritērijos var iekļaut vairākus operatorus. Tādējādi var veikt mērķtiecīgāku meklēšanu, kas ietver:

**.+** - Pluss zīme norāda, ka sekojošam vārdam jābūt ietvertam

**.-**- Mīnuss zīme norāda, ka sekojošais vārds nedrīkst būt ietverts

**( )** -  Ar iekavu palīdzību vārdus var sagrupēt pakārtotos izteicienos

**.*** - Zvaigznīte ir aizstājējzīme, ko var pievienot meklējamā vārda beigās.

**"** - Dubultpēdiņās iekļauta frāze ir jāatrod precīzi.

Lai ilustrētu iepriekšminēto, turpmāk ir parādīti piemēri, kā dažādi meklēšanas kritēriji ģenerē atšķirīgus rezultātus:

**pārdošanas nodaļa**
Meklēšanas rezultātā ir vismaz viens no diviem vārdiem

**+pārdošanas +nodaļa**
Meklēšanas rezultātā ir abi vārdi

**+pārdošanas nodaļa**
Meklēšanas rezultātā ietverts vārds "pārdošanas", bet tas ir vērtēts augstāk, ja ir iekļauts arī vārds "nodaļa"

**+pārdošanas -nodaļa**
Meklēšanas rezultātā ir vārds "pārdošanas", bet vārda "nodaļa" nav

**+pārdošanas ~nodaļa**
Meklēšanas rezultātā ietverts vārds "pārdošanas", bet tas ir vērtēts zemāk, ja ir iekļauts arī vārds "nodaļa"

**+pārdošanas+(>nodaļa<spec)**
Meklēšanas rezultātā ir vārdi "pārdošanas" un "nodaļa" vai "nodaļa" un "spec" jebkurā kārtībā, bet vārdi "pārdošanas nodaļa" ir vērtēti augstāk nekā "pārdošanas spec"

**pārd***
Meklēšanas rezultātā ir vārdi "pārdošanas" un "pārdevējs"

**"pārdošanas nodaļa"**
Meklēšanas rezultātā ir precīza frāze "pārdošanas nodaļa"


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc3NDkwNDUyMl19
-->