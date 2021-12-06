# Søkekriterier – hensyn og eksempler

Når du konfigurerer søkebetingelsene for søkemaler, er det flere hensyn som kan påvirke resultatene. Hvis de forventede søkeresultatene ikke vises, kan det skyldes følgende problemer:

-   Søkebetingelsene må bestå av minst tre tegn, og spesialtegn som «+» and «-» er ikke søkbare tegn og medregnes ikke minstetallet på tre tegn. Programmeringskompetanse i «C++» kan for eksempel ikke inkluderes i et fritekstsøk.
-   Vanlige ord som «og» eller «navn» er også utelukket fra søk.

Det er en rekke operatorer som kan inkluderes i søkekriteriene. Dette bidra til mer innsnevrede søk og består av det følgende:

+

Et plusstegn indikerer at det følgende ordet må være tilstede.

-

Et minustegn indikerer at det følgende ordet ikke må være tilstede.

( )

Parenteser gjør det mulig å gruppere ord sammen til underuttrykk.

*

Stjernen er et jokertegn som kan legges til på slutten av et søkeord.

"

En frase som innesluttes mellom hermetegn, må ha en identisk match for at den skal bli inkludert i søkeresultatene.

For å illustrere det foregående viser de følgende eksemplene hvordan forskjellige søkebetingelser returnerer forskjellige resultater:

salg avd

Returnerer resultater hvor minst ett av de to ordene finnes

+salg +avd

Returnerer resultater hvor begge ordene finnes

+salg avd

Returnerer resultater hvor «salg» finnes, men rangerer resultater som inneholder «avd», høyere

+salg -avd

Returnerer resultater hvor «salg» finnes, men ikke «avd»

+salg ~avd

Returnerer resultater hvor «salg» finnes, men rangerer resultater som inneholder «avd», lavere

+salg +(>avd <sjef)

Returnerer resultater som inneholder «salg» og «avd» eller «salg» og «sjef», i alle rekkefølger, «salg avd» vil imidlertid rangeres høyere enn «salg sjef»

salg*

Returnerer resultater som inneholder ord som «salgs», «salgssjef» eller «salgsrepresentant»

"salg avd"

Returnerer resultater som inneholder nøyaktig frasen «salg avd»


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjY5NjA4MTMxXX0=
-->