# Prompt-skeleton — RÜKV raamistik

**Mida see fail teeb:** annab sulle valmis-skeletid promptide jaoks, mida saad Project'is müügiassistendiga kasutada. Igal skeletil on sama struktuur — RÜKV.

---

## RÜKV — mis see on

Neli osa, mis igal töötaval promptil olema peab:

| Osa | Mis see on | Kus see sinu süsteemis elab |
|---|---|---|
| **R**oll | Kes agent on | Custom instructions ("Sa oled outreach-agent...") |
| **Ü**lesanne | Mida teha | Sinu sõnum chat'is |
| **K**ontekst | Mida teada | Project Knowledge (portfoolio failid) + sinu lisanduvad faktid |
| **V**orm | Kuidas väljund peab nägema | Custom instructions + sinu sõnumis täpsustus |

**Näide** (Few-Shot Prompting) on viies osa, mis lisab kõige rohkem väärtust hääle täpsuses. See juba on Project Knowledge'is `writing-samples.md` failina — sa ei pea seda iga promptiga uuesti andma.

Kui prompt ei tööta nagu loodad, küsi: mis neljast osast on **kontekstis** puudu või **vormis** ebatäpne?

---

## Skelett 1 — Üks kontakt, kirjuta otse

```
Koosta [vorm: email / LinkedIn sõnum / kõne avajalik] [nimi] ettevõttest [ettevõte].

Kontekst:
- Roll: [nende ametinimetus, kui tead]
- Miks just nemad: [üks konkreetne põhjus — uudis, signaal, jagatud probleem]
- Miks just nüüd: [ajastuse põhjus, kui olemas]

Eesmärk: [mida tahad et nad teeksid — vasta, broneeri kohtumine, edastaks kolleegile]

Lisainfo, mida võiksid kasutada: [mistahes spetsiifika, mida communication-style üksi ei kata]
```

**Kasutus:** otse chat'i Project'is. Agent peaks puuduva info küsima, mitte välja mõtlema.

---

## Skelett 2 — Sama lähenemine, aga uuri enne veebist

```
Enne mustandi koostamist uuri ettevõtet [URL].
Vaata: mida nad teevad, kellele teenivad, hiljutised uudised või signaalid.
Refereeri leitut mustandis konkreetselt.

Seejärel koosta [vorm] [nimi]-le, [ametinimetus].
Eesmärk: [mida tahad et nad teeksid].

Kui uuringus ei leia midagi märkimisväärset, ütle mulle ja küsi enne mustandi tegemist.
```

**Kasutus:** kui kontakt on uus ja sa pole jõudnud nende veebilehte vaadata. Web search tööriist peab Project'is sees olema.

---

## Skelett 3 — CSV läbikäik

```
Loe see CSV [pasta või lae üles fail]. Veerud: ettevõte, nimi, roll, valdkond, suurus, linn, kanal, haakekoht, markmed.

Iga rea jaoks koosta üks [vorm] mustand.

Reeglid:
1. Tee esimene mustand ja näita mulle enne ülejäänutega jätkamist.
2. Iga mustand järgib custom instructions reegleid ja writing-samples häält.
3. Kui rea andmed on liiga õhukesed (haakekoht puudub vms), ütle mulle ja jäta vahele, mitte ära fantaseeri.
4. Lõpus tee kokkuvõte: mitu mustandit valmis, mitu vahele jätsid ja miks.
```

**Kasutus:** kui sul on müügivihjete nimekiri (`prospects-template.csv` formaadis) ja tahad korraga mitu mustandit.

---

## Skelett 4 — Vastuse koostamine

```
Saaja [nimi] vastas mulle. Tema sõnum:

[pasta nende sõnum siia]

Konteks:
- Meie eelmine suhtlus: [üks lause või "esimene kontakt"]
- Mida ma tahan saavutada: [järgmine samm — kohtumine, vastuse selgitus, pakkumine]

Koosta vastus. Tsiteeri lühidalt, millele vastad, aga ära jäta tsitaati mustandisse sisse.
```

**Kasutus:** kui keegi vastab külmale kontaktile või järelkajastusele.

---

## Mis siis kui mustand ei kõla õigesti

Diagnostika RÜKV järgi:

- **Liiga formaalne / võõras hääl** → Kontekst-probleem. Kas `writing-samples.md` on Project Knowledge'is? Kas seal on 2+ näidet sellest kanalist (e-mail, LinkedIn vmt)?
- **Üldine, ei haaku saajaga** → Ülesanne-probleem. Sa andsid liiga vähe konteksti saaja kohta. Lisa "miks just nemad" rida.
- **Liiga pikk, peenutab** → Vorm-probleem. Lisa promptisse "max 3 lõiku, üks palve, ei mingit small-talk".
- **Hallutsineerib jagatud kogemusi või nimesid** → Custom instructions reegel 6 ei kehti. Märgi mustandis "[fakti puudub — palun täienda]" ja küsi agendilt seda mustrit järgima.
