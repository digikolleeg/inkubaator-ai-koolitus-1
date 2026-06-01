# Üldine väljund — kontekst on olemas, aga hääl ei klapi

**Mida see näitab:** Project'i "Knowledge" sektsioonis on portfoolio failid ja custom instructions on paigas, aga mustand kõlab ikka nagu suvalise AI-tööriista vaikimisi väljund. 

Põhjus: `communication-style.md` annab küll reeglid, aga ei too näiteid. Mudel kasutab oma sisseehitatud "professionaalset" tooni, sest tal pole eeskuju, kuidas sa päriselt kirjutad.

Saatja näites: **Rohejälg OÜ** (Triin Lepik).
Saaja näites: **Tallinna Ettevõtlusinkubaator**.

---

## Nõrk `communication-style.md`

```markdown
---
name: communication-style
type: portfolio
updated: 2026-06-01
---

# Minu suhtlusstiil

Kirjutan lühidalt ja otse. Väldin tühje fraase.
Kasutan *Teie* formaalsetes kontekstides ja *sina* sõpradega.
Eelistan asjalikku tooni.
```

(Fail `writing-samples.md` Project'i "Knowledge" sektsioonist puudub.)

## Prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.
Pakume tasuta CSRD-tutvustust inkubaatori cohort-firmadele.
Eesmärk: 30-min kohtumine.
```

## Tulemus

```
Lugupeetud programmijuht,

Loodan, et see e-kiri leiab teid hea tervise juures. Olen Triin Lepik,
Rohejälg OÜ asutaja. Meie ettevõte on spetsialiseerunud CSRD
(Corporate Sustainability Reporting Directive) nõustamisteenustele.

Soovime teile pakkuda võimalust korraldada teie cohort-ettevõtetele
tasuta 30-minutilist tutvustusseanssi CSRD raamistiku põhitõdedest.
Usume, et see oleks kasulik nii teie programmile kui ka osalevate
ettevõtete pikaajalisele konkurentsivõimele.

Kas oleks võimalik leida sobiv aeg lähemate nädalate jooksul,
et arutada võimalust selle koostöö osas?

Parimate soovidega,
Triin Lepik
Rohejälg OÜ
```

### Mis siin valesti on?

- **"Lugupeetud programmijuht"** — Triin ei alusta kunagi nii formaalselt.
- **"Loodan, et see e-kiri leiab teid hea tervise juures"** — Suunised keelavad selle fraasi selgelt. Ilma näideteta langeb mudel aga tagasi oma harjumuspärasele mustrile.
- **"on spetsialiseerunud... nõustamisteenustele"** — Puhas kantseliit. Triin ütleks pigem "Aitame ettevõtetel...".
- **"Usume, et see oleks kasulik"** — Ebamäärane ja nõrk väide, mis ei anna selget väärtust.
- **"Parimate soovidega"** — AI standardne signatuur, mis ei kõla nagu Triin.

Mustand on tehniliselt korrektne — siin pole hallutsinatsioone ega kirjavigu —, aga see kõlab nagu **igaüks**, mitte nagu Triin. Saaja tunneb kohe ära, et tegemist on AI loodud tekstiga.

### Kuidas Claude siin mõtleb?

Fail `communication-style.md` annab Claude'ile juhised ("kirjutan lühidalt"). Kuid need reeglid on **abstraktsed**. Mudel ei tea, mida "lühidalt" sinu kontekstis tähendab — on see kolm rida, viis lõiku või hoopis üks lause?

Kui eeskuju puudub, rakendab mudel oma sisseehitatud "lühikese professionaalse Eesti e-kirja" stiili. Tulemuseks on tekst, mis kõlab nagu Microsoft Office'i meilimall. Reeglid töötasid teoorias, aga praktikas domineeris mudeli algseadistus.

---

## Tugev `communication-style.md` + `writing-samples.md`

Täiendame faili `communication-style.md`:

```markdown
## Konkreetsed reeglid

- 3 lõiku, e-kirja lõpus on üks selge palve.
- Pöördumine: "Tere [nimi]" või "Tere" — mitte kunagi "Lugupeetud".
- Esimene lause = põhjus, miks ma kirjutan. Väldi tühje viisakusavaldusi.
- Signatuur: "Triin / Rohejälg OÜ".
- Keelatud fraasid: "Loodan...", "Parimate soovidega", "Lugupeetud", "Usume, et...".
```

Lisame Project'i "Knowledge" sektsiooni faili `writing-samples.md` koos ühe näitega:

```markdown
## Näide — külm e-kiri tootmisettevõttele (saadetud 2026-04, vastus tuli)

Tere Margus,

Saksa partnerfirma küsib Scope 3 andmeid — kuulsin seda
päringut sel kuul juba kahelt teie sektori tegijalt.
Kui te pole veel vaadanud, siis see küsimus jõuab teieni
varem või hiljem.

Meil on raamistik, mis paneb Scope 3 andmed kokku 2-3 nädalaga,
ilma et peaksite uut süsteemi juurutama. Kas tahaksite näha, kuidas
me seda näiteks Tartu masinatööstuses tegime?

Triin
Rohejälg OÜ
triin@rohejalg.ee
```

## Sama prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.
Pakume tasuta CSRD-tutvustust inkubaatori cohort-firmadele.
Eesmärk: 30-min kohtumine.
```

## Tulemus

```
Tere

CSRD nõuded laienevad 2026-2027 ja paljud inkubaatori cohort-firmad
puutuvad sellega kasvades peagi kokku. Varakult ettevalmistamine
on kordades soodsam kui viimase hetke paanika.

Pakume tasuta 30-minutilist sessiooni teie cohort'ile, kus näitame, mis
CSRD on, kellele see laieneb ja millal. Nii oskavad tiimid õigel ajal
õigeid küsimusi küsida.

Kas leiame paari nädala jooksul 30 minutit, et arutada, kas selline formaat
teie programmile sobiks?

Triin
Rohejälg OÜ
```

### Pane tähele:
- **Pöördumine:** "Tere" ilma nimeta (sest nime ei antud — sama loogika nagu varasemas näites).
- **Otse asja juurde:** Esimene lause annab kohe põhjuse (CSRD nõuete laienemine), pikk tutvustus jääb ära.
- **Struktuur:** Kolm lühikest lõiku ja üks selge palve.
- **Signatuur:** Järgib täpselt Triinu mustrit, "Parimate soovidega" on kadunud.
- **Toon:** Konkreetne, otsekohene ja ilma ebamääraste fraasideta.

See tekst kõlab nagu Triin. Saaja tajub isiklikku stiili.

---

## Kokkuvõte

1. **Miks see juhtub:** Reeglitest üksi ei piisa. Mudel tugineb oma sisseehitatud "professionaalse e-kirja" mallile, kui ta ei näe, kuidas sa päriselt kirjutad. Hea näide (Few-Shot Prompting) prompti sees töötab alati paremini kui pelgalt reeglite loetlemine.
2. **Kuidas seda märgata:** Loe mustand kõva häälega ette. Kui see kõlab nagu mistahes Eesti ettevõtte tegevjuhi standardkiri, mitte nagu sina ise, siis on kuskil viga. Testi: kas su kolleeg saaks aru, et see tekst on sinu kirjutatud?
3. **Kuidas parandada:** Lisa `writing-samples.md` Project'i "Knowledge" sektsiooni. Pane sinna vähemalt 2 täismahus näidet just sellest kanalist, mida parasjagu kasutad (e-kiri, LinkedIn). Lisa ka kontekst ("saadetud 2026-04, vastus tuli"). Mudel kopeerib mustreid palju edukamalt, kui ta pelgalt reegleid järgib.
