# Introduksjon til versjonskontroll

## Om workshoppen

Denne workshopen er en kort og enkel introduksjon til versjonskontroll med GitHub. Gjennom workshopen vil du bli kjent med de mest vanlige kommandoene i Git og scenarioene man treffer på når man benytter seg av Git.

## 🔤 Kom i gang!

-   Før du kan begynne med workshopen må du ha `git` installert på maskinen din. Hvordan du installerer `git` for ditt operativsystem kan du se [her](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
-   Du vil trenge en GitHub-konto for å kunne gjennomføre alle oppgavene i workshopen (Du kan gjennomføre noen av oppgavene uten en GitHub-konto). For å opprette en konto kan du besøke denne [lenken](https://github.com/signup).
-   Før du starter med oppgavene må du "forke" repoet til din GitHub. Helt til høyre for navnet på repoet vil du finne en knapp som heter "fork". Ved å klikke på denne vil du opprette en kopi av repoet på din GitHub som du kan jobbe ut i fra.

## Oppgavene

### Emojis 😺

Du kommer til å se noen emojis i oppgavene. De betyr ca det her:

-   🏆 Oppgave: Her er hva du skal gjøre
-   💡 Tips: Litt ekstra info som kan være greit å være for å løse en oppgave
-   ✅ Testing av løsningen: Hvordan du kan sjekke at det du har gjør blir riktig
-   🚨 Løsningsforslag: Her finner du en komplett gjennomgang av hvordan du kan løse oppgaven

### 📦 1. Last ned repoet

Før vi kan starte med å teste hvordan `git` fungerer lokalt på din maskin, må vi hente det fra GitHub til din maskin.

🏆 Last ned repoet til din maskin ved hjelp av en kommando i `git`.

> 💡 Om du ikke vil bruke terminalen for å laste ned repoet kan du gjøre det på nettsiden til repoet.

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git clone https://github.com/bekk/versionskontroll-intro.git

Cloning into 'versjonskontroll-intro'...
remote: Enumerating objects: 54, done.
remote: Counting objects: 100% (54/54), done.
remote: Compressing objects: 100% (50/50), done.
remote: Total 54 (delta 1), reused 54 (delta 1), pack-reused 0
Receiving objects: 100% (54/54), 249.08 KiB | 3.95 MiB/s, done.
Resolving deltas: 100% (1/1), done.
```

</details>

### ℹ️ 2. Sjekk status

Nå har vi klonet repoet og fått laget vår egen version. Vi kan nå starte med kanskje en av de mest brukte funksjonene i git, nemlig å se hvordan _stå_ ser ut! Har vi endret noe og hvilken branch står vi på?

🏆 I terminalen, skriv `git status`! Hva sier terminalen?

<details>
<summary> 🚨 Løsningsforslag</summary>

```
> git status

On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

</details>

### 🧱 3. Lag din første commit

#### 3.1 Gjør en endring

🏆 Åpne filen `endre-meg.txt` og erstatt placeholderne <dato> og <universitet> med de riktige verdiene.

🏆 Kjør kommandoen vi lærte i sta for å se `status`. Hvordan ser det ut?

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

🏆 Bruk `git add` for å legge til filen vi har endret i versjonshistorikken.

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

### 🆙 4. Push endringene

Vi har nå fått gjort en endring og lagt det til i historikken lokalt på maskinen din. Det er nå på tid å få dyttet disse endringene til remote også 🤩

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
