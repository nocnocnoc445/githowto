# GitHowTo harjutusprojekt

See repository on minu harjutusprojekt, mille tegin [GitHowTo](https://githowto.com/) õpetuse punktide 2–29 läbimise käigus. Projekti sisu on lihtne HTML-leht (`index.html`) koos stiilifailiga, kuid tegelik eesmärk oli õppida **Git'i** kasutama nii lokaalselt kui ka koos GitHubiga.

## Mida ma õppisin

- Repository loomine ja failide jälgimine
- Muudatuste lisamine staging area'sse ja commitimine
- Ajaloo vaatamine ja vanade versioonide juurde naasmine
- *Tagide* kasutamine olulistele versioonidele (`v1`, `v1-beta`)
- Vigade parandamine: `revert`, `reset` ja `commit --amend`
- Harude (*branch*) loomine ja nende vahel liikumine
- Harude ühendamine `merge` ja `rebase` abil
- **Merge-konfliktide lahendamine** käsitsi
- Töö kaugrepositooriumiga (GitHub)

## Git'i põhitöövoog

Git'i igapäevane töö käib minu jaoks kolmes etapis:

1. **Muuda** faili töökataloogis
2. **Lisa** muudatus staging area'sse käsuga `git add`
3. **Salvesta** muudatus ajalukku käsuga `git commit`

Enne commitimist tasub alati kontrollida olukorda käsuga `git status`. Õppisin raskel teel, et fail tuleb enne `git add` käsku ka **salvestada**, muidu ei lähe muudatus commiti.

### Tüüpiline töövoog

```bash
git status
git add README.md
git commit -m "Kirjeldav commiti sõnum"
git push
```

## Kasutatud käsud

| Käsk | Mida see teeb |
|------|---------------|
| `git status` | Näitab, mis failid on muutunud ja mis on staging area's |
| `git add` | Lisab muudatused järgmisesse commiti |
| `git commit` | Salvestab muudatused ajalukku |
| `git log` | Näitab commitide ajalugu |
| `git tag` | Märgib commiti nimega, näiteks versiooniks |
| `git reset` | Liigutab haru tagasi varasema commiti peale |
| `git branch` | Loob, näitab või kustutab harusid |
| `git switch` | Vahetab aktiivset haru |
| `git merge` | Ühendab teise haru muudatused praegusesse harru |
| `git rebase` | Tõstab haru commitid teise haru otsa |
| `git push` | Saadab commitid GitHubi |

### Harudega töötamine

```bash
git switch -C style          # loo uus haru ja liigu sinna
git commit -m "..."          # tee muudatusi eraldi harus
git switch main
git merge style              # too muudatused main harru
```

### Konflikti lahendamine rebase'i ajal

Kui mõlemas harus on muudetud sama rida, peatub `git rebase` ja fail sisaldab konfliktimärke (`<<<<<<<`, `=======`, `>>>>>>>`). Lahendasin selle nii:

```bash
# 1. Paranda fail käsitsi ja kustuta konfliktimärgid
# 2. Märgi konflikt lahendatuks
git add .
# 3. Jätka rebase'i
git rebase --continue
```

## Ajaloo vaatamine

Mugavaks ülevaateks kasutan käsku:

```bash
git log --all --graph
```

See näitab kõiki harusid, tage ja seda, kus `HEAD` parasjagu asub.

## Projekti edenemine

- [x] GitHowTo punktid 2–29 läbitud
- [x] Tagid `v1` ja `v1-beta` loodud
- [x] Harud `main` ja `style` loodud ning ühendatud
- [x] Rebase-konfliktid lahendatud
- [x] Repository GitHubi üles laetud
- [x] README.md Markdowniga vormindatud
- [x] GitHub Skills „Communicate using Markdown“ kursus lõpetatud

## Kasulikud lingid

- [GitHowTo](https://githowto.com/)
- [GitHub Markdowni juhend](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

---

Autor: **Aaron Lomp**
