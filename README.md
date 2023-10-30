# Introduksjon til versjonskontroll

## Om workshoppen

Denne workshopen er en kort og enkel introduksjon til versjonskontroll med GitHub. Gjennom workshopen vil du bli kjent med de mest vanlige kommandoene i Git og scenarioene man treffer på når man bruker Git som verktøy.

## 🔤 Kom i gang!

-   Før du kan begynne med workshopen må du ha `git` installert på din maskin. Hvordan du installerer `git` for ditt operativsystem kan du se [her](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
-   Du vil trenge en GitHub-konto for å kunne gjennomføre alle oppgavene i workshopen (Du kan gjennomføre noen av oppgavene uten en GitHub-konto). For å opprette en konto kan du besøke denne [lenken](https://github.com/signup).
-   Før du starter med oppgavene må du "forke" repoet til din GitHub. Helt til høyre for navnet på repoet vil du finne en knapp som heter "fork". Ved å klikke på denne vil du opprette en kopi av repoet på din GitHub som du kan jobbe ut i fra. **Det er veldig viktig at "Copy the main branch only" er av når du forker repoet**.

## Oppgavene

### Emojis 😺

Du kommer til å se noen emojis i oppgavene. De betyr ca det her:

-   🏆 Oppgave: Her er hva du skal gjøre
-   💡 Tips: Litt ekstra info som kan være greit å være for å løse en oppgave eller bare et tips
-   ✅ Testing av løsningen: Hvordan du kan sjekke at det du har gjør blir riktig
-   🚨 Løsningsforslag: Her finner du en komplett gjennomgang av hvordan du kan løse oppgaven

---

### 👥 0. Konfigurer Git

For å gjøre det lesbart hvem som har endret en commit etc. må vi konfiguere litt informasjon om deg.

Vi started med å sette navnet og bruker kommandoen:

`git config --global user.name "Kari Nordmann"`

Og epostadressen din:

`git config --global user.email "kari.nordmann@example.com"`

### 📦 1. Last ned repoet

Før vi kan starte med å teste hvordan `git` fungerer lokalt på din maskin, må vi hente repoet fra din GitHub til din maskin.

🏆 Last ned repoet til din maskin ved hjelp av `git clone`.

> 💡 Om du ikke vil bruke terminalen for å laste ned repoet kan du gjøre det på nettsiden til repoet.

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git clone https://github.com/<ditt brukernavn på github>/versionskontroll-intro.git

Cloning into 'versjonskontroll-intro'...
remote: Enumerating objects: 54, done.
remote: Counting objects: 100% (54/54), done.
remote: Compressing objects: 100% (50/50), done.
remote: Total 54 (delta 1), reused 54 (delta 1), pack-reused 0
Receiving objects: 100% (54/54), 249.08 KiB | 3.95 MiB/s, done.
Resolving deltas: 100% (1/1), done.
```

</details>

---

### ℹ️ 2. Sjekk status

Nå har vi klonet repoet og fått vår egen versjon lokalt. Vi kan nå starte med kanskje en av de mest brukte funksjonene i git, nemlig å se hvordan *ståa* ser ut! Har vi endret noe og hvilken branch står vi på?

🏆 I terminalen, skriv `git status`. Hva sier terminalen?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git status

On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

</details>

---

### 🧱 3. Lag din første commit

#### 3.1 Gjør en endring

🏆 Åpne filen `endre-meg.txt` og erstatt placeholderne <dato> og <universitet> med de riktige verdiene.

> 💡 En nyttig kommando for å se hvilke endringer som er gjort er `git diff`. Prøv den ut for å se hvordan endringene i filen vises!

🏆 Kjør kommandoen vi lærte i oppgave 2 for å se `status`. Hvordan ser det ut?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git status

On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   endre-meg.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

</details>

#### 3.2 Lag commiten

Nå skal vi legge til endringene våre i historien.

🏆 Bruk `git add` for å legge til filen vi har endret i versjonshistorikken.

🏆 Kjør `git status` hvordan ser det ut?

🏆 Bruk `git commit -m <en melding som beskriver endringene>` for å legge til en melding om endringene vi har gjort.

🏆 Hvordan ser status ut nå?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git add endre-meg.txt
> git commit -m "legger til universitet og dato i diktet"
[main b9758b4] legger til universitet og dato i diktet
 1 file changed, 2 insertions(+), 2 deletions(-)
> git status

On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

</details>

---

### 🆙 4. Push endringene

Vi har nå fått gjort en endring og lagt det til i historikken lokalt på maskinen din. Det er nå på tid å få dyttet disse endringene til remote/GitHub også 🤩

> 💡 Du kan bruke `git log` for å se at remoten/GitHub ligger bak den lokale historikken din.

🏆 Bruk `git push` for å dytte endringene dine til remote

🏆 Kjør `git status`. Hvordan ser det ut nå?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git status

On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

</details>

---

### 🎊 5. Lag en branch!

En av de største fordelene med å bruke versjonskontroll er at det gjør det mulig å jobbe med nye features eller bug fixes uten at man må jobbe med den versjonen som er stabil. I denne oppgaven skal du lage din første gren aka branch!

🏆 Bruk `git switch` til å lage din første branch, gi den et navn som indikerer at vi skal endre tittelen på diktet

> 💡 Om du får en feilmelding om at branchen ikke eksisterer, så kan du prøve igjen med `git switch --create <branch-navn>`

🏆 Kjør `git status`, står du fortsatt på `main`?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git switch --create "må-få-endret-den-tittelen-på-diktet"
Switched to a new branch 'må-få-endret-den-tittelen-på-diktet'
> git status
On branch må-få-endret-den-tittelen-på-diktet
nothing to commit, working tree clean
```

</details>

---

### 🤔 6. Endre tittel på diktet

Diktet i `endre-meg.txt` har ikke verdens beste tittel (diktet er ikke fantastisk heller 🤖). I denne oppgaven skal vi endre nettopp tittelen.

🏆 Gi diktet i `endre-meg.txt` en bedre tittel og legg endringene dine i historien med en beskrivende commit-melding.

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git add endre-meg.txt
> git commit -m "gir diktet en ny tittel"
[må-få-endret-den-tittelen-på-diktet 65daea4] gir diktet en ny tittel
 1 file changed, 1 insertion(+), 1 deletion(-)
```

</details>

---

### ⤵️ 7. Hente inn andre sine endringer

Noen på teamet har også endret detaljer i diktet og vi må hente inn disse endringene før vi kan pushe vår branch med ny tittel på diktet.

🏆 Bruk `git pull` for å hente inn endringene til kollegaen din.

> 💡 For å se andre brancher som finnes på repoet kan du bruke `git branch -a` for å se brancher som eksisterer lokalt eller på remote/GitHub

🏆 Hva skjedde når du prøvde å hente endringene fra kollegaen din?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git pull origin dikt-med-annet-universitet
Auto-merging endre-meg.txt
CONFLICT (content): Merge conflict in endre-meg.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Når vi prøve å hente inn endringene til kollegaen vår oppstod det som heter en merge conflict! I neste oppgave skal vi se på hvordan vi kan løse slike.

</details>

---

### 🔀 8. Løs merge conflict

Kollegaen hadde også fylt inn universitet og dato i diktet og det har nå oppstått en [merge-conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line) siden begge har endret på samme del av diktet.

🏆 Kjør `git status` og åpne filen hvor det har oppstått en *merge conflict* i en tekst-editor.

<details>
<summary> 🚨 Løsningsforslag</summary>

```
On branch må-få-endret-den-tittelen-på-diktet
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   endre-meg.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

</details>

🏆 Løs *merge conflicten* ved å fjerne datoen og universitetsnavnet som kollegaen din har endret til på hen sin branch.

<details>
<summary> 🚨 Løsningsforslag</summary>

```
vim endre-meg.txt

-- GitHub reisen --

På universitets sti jeg trår,
Versionskontroll jeg nå skal lære.
Commits, branches, og mergekommandoer,
I kodeskogen, jeg finner mine spor.

Git og GitHub, verden åpner seg,
Historien i filene jeg forstår nå lett.
Dagens dato, en ny start, en tid for vekst,
Med versionskontroll, jeg tar den beste fest.

<<<<<<< HEAD
Dato: 31.10.23
Universitet: UiT
=======
Dato: UiO
Universitet: 31.10.2023
>>>>>>> origin/dikt-med-annet-universitet

```

For å beholde de endringene vi har endret til må vi fjerne alt som ikke hører til vår "head".

```
-- GitHub reisen --

På universitets sti jeg trår,
Versionskontroll jeg nå skal lære.
Commits, branches, og mergekommandoer,
I kodeskogen, jeg finner mine spor.

Git og GitHub, verden åpner seg,
Historien i filene jeg forstår nå lett.
Dagens dato, en ny start, en tid for vekst,
Med versionskontroll, jeg tar den beste fest.

Dato: 31.10.23
Universitet: UiT

```

Så må vi legge til den "korrekte" filen tilbake i historien.

```
> git add endre-meg.txt
```

Til slutt må vi "commite" for å markere `merge conflicten` som løst. Kjører en `git status` for å sjekke at alt er løst.

```
> git commit
[må-få-endret-den-tittelen-på-diktet e89fc29] Merge remote-tracking branch 'origin/dikt-med-annet-universitet' into må-få-endret-den-tittelen-på-diktet

> git status
On branch må-få-endret-den-tittelen-på-diktet
nothing to commit, working tree clean
```

</details>

---

### ⬅️ 9. Lag en pull request

Vi har nå endret tittel på diktet og det er på tide å få dette inn i `main`. Dette kan vi gjøre ved å lage en [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

> 💡 Prøv å kjør `git log` nå som vi har fikset merge conflicten. Har kollegaen din gjort noen andre endringer også?

🏆 Bruk kommandoen du lærte tidligere i kurset til å få din branch opp til remote/GitHub

🏆 Besøk repoet ditt på GitHub og opprett en pull request mot `main`

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git push origin må-få-endret-den-tittelen-på-diktet
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 16 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 857 bytes | 857.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote:
remote: Create a pull request for 'må-få-endret-den-tittelen-på-diktet' on GitHub by visiting:
remote:      https://github.com/dittbrukernavn/versjonskontroll-intro/pull/new/slug
remote:
To github.com:joakimsjo/versjonskontroll-intro.git
 * [new branch]      må-få-endret-den-tittelen-på-diktet -> må-få-endret-den-tittelen-på-diktet
```

**På GitHub**

1. Velg "Compare & pull request" på oversikten av repoet ditt for å opprette en Pull Request.
2. Gi Pull Requesten din et beskrivende navn.
3. Velg "Create pull request".

</details>

## ⏩ Veien videre

Du har nå fått en kort introduksjon til de vanligste kommandoene og scenarioene man kan oppleve når man benytter seg av git som versjonskontroll. Om du har lyst til å lære enda mer om git kan du besøke disse lenkene for mer informasjon og eksempler:

-   [Enda mer forståelse om branches/grener](https://learngitbranching.js.org/)
-   [GitHub sin dokumentasjon](https://docs.github.com/en)
-   [Git forklart gjennom gitarspill](https://www.youtube.com/watch?v=S9Do2p4PwtE)
-   [Pretty git log](https://coderwall.com/p/euwpig/a-better-git-log)
-   [Oversikt over applikasjoner for å administrere git](https://git-scm.com/downloads/guis)

## 👩🏻‍🎓 GitHub Student Developer Pack

Dette er et hot tip 🔥 Som student kan man få tilgang til flere funksjoner og verktøy graits gjennom GitHub sin Student Developer Pack. Her kan du også få tilgang til flere ressurser som lærer deg blant annet mer om hvordan GitHub kan brukes til å bygge, teste og deploye applikasjonene dine automatisk. For å se alle fordeler og hvordan søke — [gå hit! ](https://education.github.com/pack)
