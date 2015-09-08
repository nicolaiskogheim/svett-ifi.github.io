---
Categories: [Arrangementer]
Description: "Introduksjonsarrangement"
Tags: []
date: 2015-08-09T17:31:16+02:00
title: "Få et forsprang på livet som programmerer: Del 2"
---

Dato: 10.09.2015  
Sted: Fortress @ Ole Johan Dahls  
[Arrangement på facebook](https://www.facebook.com/events/550620871758803/)

# Terminalen og Unix

De fleste av dere har vært på forkurs og har allerede litt kjennskap til hva som foregår i en terminal.
Vi skal bygge litt videre, men det gjør ikke noe om du ikke var på den undervisningen, eller om du rett og slett har glemt alt.

Det viktigste for å gå gjort noe er at du vet hvor du går for å få hjelp.
Å være flink til å finne svar på spørsmål er helt essensielt som programmerer,
fordi man møter på ting hele tiden som man enten ikke vet, eller bare har glemt.
Derfor er et av to fokuspunkter i denne artikkelen å gjøre deg flinkere til å finne fram.
Det andre er å gi en smakebit på hva som er mulig.
Jeg oppfordrer deg til å søke opp ting når du lurer på noe. Enkelte ting er utelatt i denne artikkelen, både for å holde den lettlest, og for å gi deg trening i å bruke Google.

# TODO: Flytt denne til der hvor man introduseres
Du får svar på det meste på Google, men av og til er det mye raskere å bruke hjelpesystemet som finnes i terminalen,
selv om det kanskje ikke virker helt sånn i starten.


### Terminologi

*Prompt* : Teksten som står til venstre for markøren/cursoren i terminalen. Eksempel:
```sh
jonas@ifi $ 
```
Vanligvis i eksempler nøyer man seg med å bruke f.eks. `$` som prompt.

```sh
$ echo hei
hei #en kommentar
```
*kommando* : programmet som kalles. Her `echo`.  
*argument(er)* : teksten etter kommandoen. Her `hei`  
*output* : det kommandoen printer når du kaller den. Alt som ikke har en *prompt* foran seg
er som regel output fra forrige kommando.  
*kommentar* : tekst som ikke blir lest av terminalen. Her `#en kommentar`  

```sh
$ ls -l
```
*flagg* : disse får kommandoen til å oppføre seg annerledes.

## Start terminalen
Kjører du Ubuntu og er ukjent med det,
kan du trykke på symbolet øverst til venstre i verktøylinjen og søke på "terminal".
Ellers har du [google](https://google.com).  

Programmet du får opp kalles en terminalemulator, fordi den emulerer/etterligner gamle terminaler.
Her kan man kjøre kommandoer som lar deg gjøre veldig mye.
Siden dette kurset handler om å bli trygg i terminalen,
og å bli kvitt klaustrofobi-følelsen man kan få,
så skal vi fokusere på hvordan ting fungere og hvordan man finner hjelp i stedet for å pugge kommandoer og hvilke argumenter de tar.
Å pugge kommandoer er ikke noe du burde gjøre uansett; kommandoer og flagg du bruker ofte vil du huske av deg selv,
og andre ting er kanskje ikke nødvendig å gå rundt å huske på,
spesielt når du vet hvordan du finner fram når du en gang trenger det.

Nå skal vi se noen eksempler, og prøve å kjøre litt kommandoer.
Ingenting av dette kan gjøre noe skummelt med filene dine,
men når det kommer slike kommandoer,
som sletter filer for eksempel, så blir det merket tydelig.

`ls` er en veldig vanlig kommando som lar deg liste opp mapper og filer der du befinner deg i filsystemet.
```sh
$ ls
enfil.txt enannenfil.txt enmappe
```

Som med mange andre kommandoer, kan denne ta mange flagg og argumenter. Et eksempel på et flagg er `-l`, som lar deg vise mapper og filer i en liste
```sh
$ ls -l

total 0
-rw-r--r-- 1 nicolai staff  0 Aug 16 15:57 enannenfil.txt
-rw-r--r-- 1 nicolai staff  0 Aug 16 15:57 enfil.txt
drwxr-xr-x 2 nicolai staff 68 Aug 16 15:57 enmappe
```

Vi bruker et minus-tegn, også kalt *dash*, for å si at det kommer et flagg og ikke noe annet.
Vi kan bruke flere `flagg` samtidig, begge eksemplene gjør akkurat det samme.
```sh
$ ls -la
```
```sh
$ ls -l -a
```

Et `argument`, altså noe som ikke er et `flagg`, kan være navnet på en mappe.
```sh
$ ls enmappe
fil.txt bil.txt
```

Mange kommandoer fungerer stort sett slikt som dette. Du skriver navnet på dem og gir dem alternativt noen `flagg` eller `argumenter` som endrer hvordan de oppfører seg.

### Les manualen

Den enkleste måten å finne ut hvordan du skal bruke en kommando er ofte å lese man-siden for den kommandoen. 

```sh
man ls
```


Dette vil fyre opp manualsidene til kommandoen `ls`. 
Programmet som viser manualsiden kalles en `pager`, og her kan det hende at du ikke får bruke mus/trackpad til å navigere, men det gjør ingenting, for det er kjempelett å bruke tastaturet uansett.

Dette er en rask oversikt, men du kan alltids trykke `h` når du leser manualsieder for å finne ut hvilke taster du kan bruke.

```sh
j   ned
k   opp
u   opp en halv side
d   ned ---- || ----

/text<Enter>  Søk etter "text"
n             Gå til neste treff av søket
N             Gå til forrige treff av søket

q   lukk
```
------

Andre kommandoer du kommer til å støte på er disse:
```sh
cat    concatenate files and print on the standard output
cd     change the current directory
cp     copy files and directories
echo   display a line of text
find   walk a file hierarchy
htop   interactive process viewer
less
ls
mkdir
mv
rm
touch
```
Gjerne les manualsidene til noen av dem, og prøv de ut.
