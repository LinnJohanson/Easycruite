# Søkemaler

Søkemaler gjør det mulig for EasyCruit-administratorer å opprette maler som rekrutterere kan bruke til å søke i jobbsøkerbasen. Denne funksjonaliteten er nyttig for virksomheter som har et stort antall registrerte søkere, eller når du søker etter et veldig spesifisert sett av ferdigheter. Avhengig av alternativet som er inkludert i søkemalen, kan verdiene legges inn i fritekstfelt og velges fra utfylte lister, resultater fra spørsmål og opplastede filer.

Seksjonen  Arbeidserfaring  i søkemalen gir for eksempel brukeren mulighet til å velge fra rullegardinlister, rullegardinlister med flere valg og fritekstfelter.

Hvis du vil vite mer om å kjøre søk, kan du se  [Søke etter kandidater](../getting-started/searching_for_candidates.htm).

#### Opprette en søkemal

1.  Fra  verktøylinjen  velger du  Innstillinger  og deretter  Søkemaler.
2.  Hvis du vil opprette en helt ny søkemal, må listen  Velg søkemal  vise  Velg  
    ,– eller –  
    hvis du baserer søkemalen på en eksisterende mal, velger du den fra listen  Velg søkemal.
3.  Skriv et navn på søkemalen i feltet  Lagre søk som.
4.  Klikk på pilen ved siden av hver overskrift for å utvide alternativene som er tilgjengelige i den seksjonen.
5.  Velg ønskede verdier for hver søkeparameter.  
    For hver seksjon der det er valgt søkeparametere, vises en rød stjerne i overskriftsraden.
6.  Klikk på  Lagre mal for å lagre den nye malen.

#### Redigere en eksisterende søkemal

1.  Fra  verktøylinjen  velger du  Innstillinger  og deretter  Søkemaler.
2.  Velg malen som skal endres, fra listen  Velg søkemal.
3.  Klikk på pilen ved siden av hver overskrift for å utvide alternativene som er tilgjengelige i den seksjonen.  
    Søkemalen vises i den samme seksjonen som den ble utvidet i sist den ble lagret.
4.  Velg ønskede verdier for hver søkeparameter.
5.  Klikk på  Oppdater mal  for å lagre endringene.

#### Slette en søkemal

1.  Fra  verktøylinjen  velger du  Innstillinger  og deretter  Søkemaler.
2.  Velg malen som skal slettes, fra listen  Velg søkemal.
3.  Klikk på  Slett mal  og deretter på  OK  når du blir bedt om å bekrefte slettingen.

#### Bruke hurtiglenker til søk

1.  På  startsiden  klikker du på pilikonet for å utvide boksen  Hurtiglenker til søk.
2.  Klikk på det ønskede søkeelementet i listen  Søkemaler  eller  Lagrede søk  for å vise siden for avansert  CV-søk.
3.  Fullfør søket etter behov.  
    Alternativet Hurtiglenker til søk er ikke tilgjengelig som standard og må aktiveres i systemet ditt.

#### Søkekriterier – hensyn og eksempler

Når du konfigurerer søkebetingelsene for søkemaler, er det flere hensyn som kan påvirke resultatene. Hvis de forventede søkeresultatene ikke vises, kan det skyldes følgende problemer:

Søkebetingelsene må bestå av minst tre tegn, og spesialtegn som «+» and «-» er ikke søkbare tegn og medregnes ikke minstetallet på tre tegn. Programmeringskompetanse i «C++» kan for eksempel ikke inkluderes i et fritekstsøk.

-   Vanlige ord som «og» eller «navn» er også utelukket fra søk.

Det er en rekke operatorer som kan inkluderes i søkekriteriene. Dette bidra til mer innsnevrede søk og består av det følgende:

.+ : Et plusstegn indikerer at det følgende ordet må være tilstede.
.- : Et minustegn indikerer at det følgende ordet ikke må være tilstede.
() : Parenteser gjør det mulig å gruppere ord sammen til underuttrykk.
.* : Stjernen er et jokertegn som kan legges til på slutten av et søkeord.
" : En frase som innesluttes mellom hermetegn, må ha en identisk match for at den skal bli inkludert i søkeresultatene.

For å illustrere det foregående viser de følgende eksemplene hvordan forskjellige søkebetingelser returnerer forskjellige resultater:

salg avd - Returnerer resultater hvor minst ett av de to ordene finnes

+salg +avd - Returnerer resultater hvor begge ordene finnes

+salg avd - Returnerer resultater hvor «salg» finnes, men rangerer resultater som inneholder «avd», høyere

+salg -avd - Returnerer resultater hvor «salg» finnes, men ikke «avd»

+salg ~avd - Returnerer resultater hvor «salg» finnes, men rangerer resultater som inneholder «avd», lavere

+salg +(>avd <sjef) - Returnerer resultater som inneholder «salg» og «avd» eller «salg» og «sjef», i alle rekkefølger, «salg avd» vil imidlertid rangeres høyere enn «salg sjef»
salg* - Returnerer resultater som inneholder ord som «salgs», «salgssjef» eller «salgsrepresentant»
"salg avd" - Returnerer resultater som inneholder nøyaktig frasen «salg avd»

##### Se også:

![](../Resources/Images/icon-document-link.png)  [Søke etter kandidater](searching_for_candidates.htm)
![](../Resources/Images/icon-document-link.png)  [Jobbkategorier](job_categories.htm)
![](../Resources/Images/icon-document-link.png)  [Interne spørsmål](additional_questions.htm)
![](../Resources/Images/icon-document-link.png)  [Brukere: Opprette, endre, slette](users_create_edit_delete.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk2OTc0OTk2Ml19
-->