# Hallutsinatsioon — väljamõeldud kontakt või fakt

**Mida see näitab:** kui kontekst on liiga õhuke, täidab Claude lüngad usutavalt kõlavate, aga väljamõeldud detailidega — nimedega, kohtumistega, jagatud taustaga. Mustand kõlab hästi, kuni saaja avab selle ja küsib "mis koosolek?".

Saatja näites: **Rohejälg OÜ** (Triin Lepik, CSRD-nõustaja).
Saaja näites: **Tallinna Ettevõtlusinkubaator**.

---

## Halb prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.
Pakume CSRD-nõustamist. Eesmärk: kohtumine.
```

Mis siin puudu on:
- Konkreetne saaja nimi (kas ta on naine, mees, või "programmijuht" üldiselt?)
- Miks just nemad — kas on hiljutine uudis, signaal, jagatud kontekst?
- Mis Rohejälg ja inkubaator ühendab — kas Triin oli ise kunagi kasvatatav, kas mõni alumn vajab CSRD-d?

## Mis tuleb välja

```
Tere Kristel,

Olin rõõmuga eelmise kuu inkubaatori demo-päeval ja sai
kuulda teie 2025 cohort'i tutvustusi — eriti haaras
mind energia-vertikaali fookus. Meil on Rohejäljaga
sarnaseid kogemusi just sellistes sektorites ja
tahaksime jagada, kuidas CSRD-raamistik teiste
alumnite jaoks väärtust on toonud.

Kas saaksime järgmise nädala neljapäeval kell 14
korraks rääkida?

Triin
Rohejälg OÜ
```

### Kus on hallutsinatsioon

- **"Tere Kristel"** — Triin pole kunagi öelnud programmijuhi nime. Claude pani esimese eesnime, mis tundus "programmijuht-sobiv".
- **"eelmise kuu demo-päeval"** — Triin pole demo-päeval käinud. Claude eeldas, et "eelmise kuu demo-päev" on usutav ettekääne.
- **"2025 cohort'i energia-vertikaali fookus"** — väljamõeldud kohort, väljamõeldud fookus. Inkubaator avalikustab tihti cohort'i koosseise, aga "energia-vertikaal" siit ei tule.
- **"teiste alumnite jaoks väärtust toonud"** — Rohejäljal pole avalikult ühtegi inkubaatori-alumni klienti. Claude lisas "social proof" tühja kohta.

Saaja loeb seda ja teab, et midagi siin ei klapi. Halvemal juhul vastab "vabandust, kes te olete?" — paremal juhul kustutab.

### Mis on Claude'i loogika

Custom instructions ütlevad "ole konkreetne, kasuta saaja konteksti". Aga **kasutaja kontekst oli tühi**. Claude valib kahe halva variandi vahel:
1. Kirjutada üldine, nõme tekst ("Tere, oleme CSRD-firma, kas saame kohtuda?")
2. Täita lüngad usutavalt kõlavate detailidega

Vaikimisi kaldub ta (2) poole, sest see kõlab kirjutamise-näidete põhjal "rohkem nagu päris e-mail". Sellepärast see juhtub ka siis, kui `writing-samples.md` on hea — hea hääl ei takista hallutsinatsiooni, see ainult muudab hallutsinatsiooni paremini-kõlavaks.

---

## Hea prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.

Mida ma kindlasti tean:
- Saaja: programmijuht (nime ma ei tea)
- Inkubaator on Eesti suurim varajase faasi startup-akselleraator
- Cohort'id on tavaliselt 10-15 firmat, segu sektoreid

Mida ma EI tea ja ära oletust:
- Konkreetne programmijuhi nimi
- Hiljutised cohort'id või sündmused
- Kas inkubaatoril on juba CSRD-nõustaja
- Kas Triin on inkubaatoriga varem suhelnud

Miks just nemad: inkubaatori cohort-firmad on need, kes 2-3 aasta pärast
kasvavad CSRD-kohuslaste suuruseks. Varakult tutvumine = tulevaste klientide tundmine.

Eesmärk: 30-min kohtumine, kus arutame kas saame inkubaatori-cohort'ile
CSRD-ootuste lühitutvustuse teha (tasuta, väärtust näitamiseks).

Kui sa ei tea midagi täpsemat, kirjuta üldsõnalisemalt aga ära mõtle välja.
Märgi mustandis kohad, kus mul oleks kasulik täpsem info juurde anda.
```

## Mis tuleb välja

```
Tere

Olen Triin Lepik, Rohejälg OÜ asutaja. Aitame ettevõtetel
CSRD-raporteerimise jalad alla saada.

Märkasime, et inkubaatori cohort'id liiguvad sageli kasvu-tempos,
mille käigus jõuavad 2-3 aastaga CSRD-skoopi. Selleks ajaks
on ette valmistamine palju odavam kui viimasel hetkel paanitsemine.

Pakume tasuta 30-min sessiooni teie cohort-firmadele, kus
selgitame mis CSRD on, kelle jaoks ja millal. Eesmärk: anname
neile raamistiku, et nad oskaksid õigeid küsimusi õigel ajal küsida.

Kas saaksime järgmise paari nädala jooksul 30 minutit korraks
rääkida, kas see formaat teie cohort'i puhul mõtteka oleks?

[KÜSI HEIGOLT: kas mainida konkreetse cohort'i kuupäeva või jätta lahtiseks?]

Triin
Rohejälg OÜ
triin@rohejalg.ee
```

Pane tähele:
- "Tere" ilma nimeta — sest nime ei tea
- Üldine pakkumine, mis kehtib mistahes cohort'i puhul
- Ei mainita ühtegi sündmust, mida Triin pole näinud
- "[KÜSI HEIGOLT:...]" — märk inimesele, et siia tuleb info juurde anda

Saaja loeb seda ja teab, et siin pole midagi väljamõeldud.

---

## Kokkuvõte

1. **Miks see juhtub:** custom instructions surub "ole konkreetne" — kui kasutaja konkreetset infot ei anna, täidab Claude tühje lünki usutavalt kõlavaga.
2. **Kuidas seda märgata:** loe mustand läbi nagu saaja. Kui näed nime, kohtumist, jagatud kogemust või konkreetset fakti — küsi endalt "kas ma kirjutasin selle Claude'ile?". Kui ei, on see välja mõeldud.
3. **Kuidas parandada:** lisa promptisse otsesõnu "MIDA MA EI TEA" sektsioon ja juhis "ära mõtle välja". Hea agent peab eelistama tühja koha märkimist väljamõeldisele.
