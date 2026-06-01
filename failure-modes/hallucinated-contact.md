# Hallutsinatsioon — väljamõeldud kontakt või fakt

**Mida see näitab:** Kui kontekst on liiga lünkik, kipub Claude puuduva info täitma usutavalt kõlavate, aga väljamõeldud detailidega — näiteks nimede, varasemate kohtumiste või jagatud taustaga. Mustand võib kõlada suurepäraselt, kuni saaja seda loeb ja imestab: "Mis koosolekust ta räägib?".

Saatja näites: **Rohejälg OÜ** (Triin Lepik, CSRD-nõustaja).
Saaja näites: **Tallinna Ettevõtlusinkubaator**.

---

## Puudulik prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.
Pakume CSRD-nõustamist. Eesmärk: kohtumine.
```

### Mis siin puudu on?
- **Konkreetne saaja:** Kas tegemist on naise, mehe või lihtsalt "programmijuhiga" üldiselt?
- **Põhjus:** Miks just nemad? Kas tugined mõnele hiljutisele uudisele, signaalile või ühisele kontekstile?
- **Ühisosa:** Mis Rohejälge ja inkubaatorit ühendab? Kas Triin oli ise kunagi programmis osaleja või vajab mõni vilistlane CSRD teenust?

## Tulemus

```
Tere Kristel,

Olin rõõmuga eelmise kuu inkubaatori demo-päeval ja sain
kuulda teie 2025 cohort'i tutvustusi — mind haaras eriti
energia-vertikaali fookus. Meil on Rohejäljaga
sarnaseid kogemusi just sellistes sektorites ja
tahaksime jagada, kuidas CSRD-raamistik teiste
vilistlaste jaoks väärtust on toonud.

Kas saaksime järgmise nädala neljapäeval kell 14
korraks rääkida?

Triin
Rohejälg OÜ
```

### Kus on hallutsinatsioon?

- **"Tere Kristel"** — Triin pole kordagi programmijuhi nime maininud. Claude valis lihtsalt esimese eesnime, mis tundus antud rolli sobivat.
- **"eelmise kuu demo-päeval"** — Triin pole sellisel üritusel osalenud. Claude eeldas, et demo-päeval osalemine on asjakohane ja usutav ettekääne kirjutamiseks.
- **"2025 cohort'i energia-vertikaali fookus"** — Väljamõeldud kohort ja fookus. Inkubaatorid küll avalikustavad kohortide infot, kuid "energia-vertikaali" info on siinkohal täiesti laest võetud.
- **"teiste vilistlaste jaoks väärtust toonud"** — Rohejäljal pole avalikult teadaolevalt ühtegi inkubaatori vilistlasest klienti. Claude lisas siia nö sotsiaalse tõestuse puuduva info täiteks.

Saaja loeb seda ja saab kohe aru, et midagi ei klapi. Halvemal juhul küsib ta: "Vabandust, kes te olete ja millisest demo-päevast te räägite?". Paremal juhul kiri lihtsalt kustutatakse.

### Kuidas Claude siin mõtleb?

Suunised (Custom instructions) käsivad: "Ole konkreetne ja kasuta saaja konteksti." Kuna **kasutaja ise konkreetset konteksti ei andnud**, valib Claude kahe halva variandi vahel:
1. Kirjutab üldsõnalise ja igava teksti ("Tere, oleme CSRD-firma, kas saame kohtuda?").
2. Täidab lüngad usutavalt kõlavate detailidega.

Vaikimisi kaldub mudel teise variandi poole, sest kirjutamisnäidete põhjal tundub see "rohkem nagu päris e-kiri". Seetõttu juhtub hallutsineerimist isegi siis, kui `writing-samples.md` on väga hästi koostatud. Hea eeskuju ei hoia hallutsinatsioone ära, vaid paneb need lihtsalt paremini ja usutavamalt kõlama.

---

## Tugev prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.

Mida ma kindlasti tean:
- Saaja: programmijuht (nime ma ei tea).
- Inkubaator on Eesti suurim varajase faasi startup-kiirendi.
- Cohort'id on tavaliselt 10-15 firmat erinevatest sektoritest.

Mida ma EI tea ja palun ära oleta:
- Konkreetne programmijuhi nimi.
- Hiljutised cohort'id või sündmused.
- Kas inkubaatoril on juba CSRD-nõustaja.
- Kas Triin on inkubaatoriga varem suhelnud.

Miks just nemad: Inkubaatori cohort-firmad on need, kes 2-3 aasta pärast
kasvavad CSRD-kohuslaste suuruseks. Varakult tutvumine aitab tulevasi kliente tundma õppida.

Eesmärk: 30-minutiline kohtumine, kus arutame, kas saame inkubaatori cohort'ile
teha CSRD-ootuste lühitutvustuse (tasuta, väärtuse näitamiseks).

Kui sa ei tea midagi täpsemat, kirjuta üldsõnalisemalt, aga ära mõtle fakte välja.
Märgi mustandis ära kohad, kuhu ma peaksin ise täpsema info lisama.
```

## Tulemus

```
Tere

Olen Triin Lepik, Rohejälg OÜ asutaja. Aitame ettevõtetel
CSRD-raporteerimisega algust teha.

Oleme märganud, et inkubaatori cohort'id kasvavad sageli tempos,
mille tulemusena jõuavad nad 2-3 aastaga CSRD-nõuete skoopi. Varakult 
selleks valmistumine on oluliselt soodsam kui viimase hetke kiirustamine.

Pakume tasuta 30-minutilist sessiooni teie cohort-firmadele, kus
selgitame, mis CSRD on, kellele see laieneb ja millal. Eesmärk on anda
neile raamistik, et nad oskaksid õigel ajal õigeid küsimusi esitada.

Kas saaksime järgmise paari nädala jooksul 30 minutit rääkida, et arutada, 
kas selline formaat tooks teie cohort'ile väärtust?

[KÜSI HEIGOLT: kas mainida mõne konkreetse programmi või cohort'i nime?]

Triin
Rohejälg OÜ
triin@rohejalg.ee
```

### Pane tähele:
- **Pöördumine:** "Tere" ilma nimeta, kuna nimi ei olnud teada.
- **Üldisus vs konkreetsus:** Pakkumine on üldine ja kehtib mistahes cohort'i puhul.
- **Faktipõhisus:** Ei mainita ühtegi sündmust ega detaili, mida Triin tegelikult ei tea.
- **Juhised kasutajale:** `[KÜSI HEIGOLT: ...]` on selge märk, et siin on vaja inimese sisendit.

Saaja loeb seda ja teab, et kiri on aus ning ükski fakt pole laest võetud.

---

## Kokkuvõte

1. **Miks see juhtub:** Kui reeglid nõuavad konkreetsust, aga kasutaja seda ei paku, täidab mudel lüngad ise, et tekst kõlaks usutavamalt.
2. **Kuidas seda märgata:** Loe mustand läbi saaja pilguga. Kui näed seal nime, sündmust, jagatud kogemust või konkreetset fakti, küsi endalt: "Kas ma andsin selle info Claude'ile?". Kui vastus on ei, on see mudeli poolt välja mõeldud.
3. **Kuidas parandada:** Lisa oma prompti alati selge sektsioon "MIDA MA EI TEA" koos juhisega "ära mõtle fakte välja". Hea agent peab eelistama faktide puudumise tunnistamist nende väljamõtlemisele.
