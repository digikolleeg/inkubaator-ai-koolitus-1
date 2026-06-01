# Üldine väljund — kontekst on olemas, aga hääl ei klapi

**Mida see näitab:** Project Knowledge'is on portfoolio failid, custom instructions on paigas, aga mustand kõlab ikka nagu suvalise AI-tööriista vaikimisi-väljund. Põhjus: `communication-style.md` ütleb reegleid, aga ei näita näiteid. Mudel kasutab oma vaikimisi "professionaalset" tooni, sest tal pole näha, kuidas sina päriselt kirjutad.

Saatja näites: **Rohejälg OÜ** (Triin Lepik).
Saaja näites: **Tallinna Ettevõtlusinkubaator**.

---

## Õhuke `communication-style.md`

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

`writing-samples.md` puudub Project Knowledge'ist.

## Prompt

```
Koosta email Tallinna Ettevõtlusinkubaatori programmijuhile.
Pakume tasuta CSRD-tutvustust inkubaatori cohort-firmadele.
Eesmärk: 30-min kohtumine.
```

## Mis tuleb välja

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

### Mis siin valesti on

- **"Lugupeetud programmijuht"** — Triin ei alusta kunagi nii. Liiga formaalne.
- **"Loodan, et see e-kiri leiab teid hea tervise juures"** — custom instructions ütlevad selgelt, et see fraas on keelatud. Aga ilma näideteta kaldub mudel vaikimisi-mustrisse.
- **"on spetsialiseerunud... nõustamisteenustele"** — kantseliit. Triin ütleks "Aitame ettevõtetel...".
- **"Usume, et see oleks kasulik"** — hedge fraas, mis ei luba midagi.
- **"Parimate soovidega"** — vaikimisi-AI signatuur, mis ei kõla Triinu moodi.

Mustand on tehniliselt OK — pole hallutsinatsioone, pole vigu — aga see kõlab nagu **igaüks**, mitte nagu Triin. Saaja tunneb selle ära kui "veel üks AI-tekst".

### Mis on Claude'i loogika

`communication-style.md` annab Claude'ile reegleid ("kirjutan lühidalt"). Aga reeglid on **abstraktsed**. Mudel ei tea, mida "lühidalt" sinu kontekstis tähendab — kolm rida? Viis lõiku? Üks lause?

Kui pole näiteid, kasutab mudel oma vaikimisi-stiili "lühike Eesti professionaalne e-mail" ja see kõlab nagu Microsoft Office'i meili-mall. Reeglid teoorias, vaikimisi-stiil praktikas.

---

## Jõuline `communication-style.md` + `writing-samples.md`

`communication-style.md` lisame:

```markdown
## Konkreetsed reeglid

- 3 lõiku, ühe palvega lõpus
- "Tere [nimi]" või "Tere" — mitte "Lugupeetud"
- Esimene lause = põhjus, miks kirjutan. Mitte viisakusavaldus.
- Signatuur: "Triin / Rohejälg OÜ"
- Ei kasuta: "Loodan...", "Parimate soovidega", "Lugupeetud", "Usume, et..."
```

`writing-samples.md` Project Knowledge'isse, sees üks näide:

```markdown
## Näide — külm e-mail tootmisettevõttele (saadetud 2026-04, vastus tuli)

Tere Margus,

Saksa partnerfirma küsib Scope 3 andmeid — kuulsin seda
päringut juba kahelt teie sektori tegijalt sel kuul.
Kui te pole veel vaadanud, siis see küsimus jõuab teieni
varem kui hilisemalt.

Meil on raamistik, mis paneb Scope 3 andmed kokku 2-3 nädalaga
ilma uut süsteemi käivitamata. Kas tahaksite näha, kuidas
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

## Mis tuleb välja

```
Tere

CSRD-skoop laieneb 2026-2027 ja paljud inkubaatori cohort-firmad
jõuavad kasvades sinna jooksvalt sisse. Varakult ette valmistamine
on kordades odavam kui viimase hetke paanika.

Pakume tasuta 30-min sessiooni teie cohort'ile, kus näitame mis
CSRD on, kelle jaoks ja millal — nii et tiimid teaks õigeid
küsimusi õigel ajal küsida.

Kas leiame paari nädala jooksul 30 min, et arutada, kas see formaat
teie cohort'ile sobiks?

Triin
Rohejälg OÜ
```

Pane tähele:
- "Tere" ilma nimeta (sest nime ei tea — sama loogika nagu eelmises failis)
- Esimene lause = põhjus (CSRD-skoop laieneb), mitte tutvustus
- Kolm lõiku, üks palve
- Signatuur Triinu mustri järgi, mitte "Parimate soovidega"
- Toon: konkreetne, otsekohene, ei hedge'i

See kõlab nagu Triin. Saaja tunneb stiili ära.

---

## Kokkuvõte

1. **Miks see juhtub:** reeglid üksi ei ole piisavad. Mudel täidab "professionaalse e-mail" mustri, kui talle pole näha, kuidas sina päriselt kirjutad. Few-Shot Prompting (näited prompti sees) lööb rule-following'i.
2. **Kuidas seda märgata:** loe mustand valju häälega. Kui see kõlab nagu mistahes Eesti SME tegevjuht, mitte nagu sina — siis ongi probleem. Test: kas su kolleeg saaks aru, et see on sinult kirjutatud?
3. **Kuidas parandada:** lisa `writing-samples.md` Project Knowledge'isse. Vähemalt 2 näidet sellest kanalist, mida sa kasutad. Iga näide täismahus, koos saatja-konteksti reaga ("saadetud 2026-04, vastus tuli"). Mudel pattern-match'ib näiteid, mitte reegleid.
