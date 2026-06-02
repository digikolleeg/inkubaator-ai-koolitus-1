# Prompt-skeleton — müügiassistendi mallid

**Mida see fail teeb:** Annab sulle valmis-skeletid promptide jaoks, mida saad Project'is müügiassistendiga kasutada.

---

## Kolm küsimust, mis iga töötava prompti taga on

| Küsimus | Näide |
|---|---|
| **Mida tahad juhtuda?** | "Jõuda 20-minutilise kõneni" |
| **Mida Claude peab teadma?** | Sinust + saajast + päästikust |
| **Mis kujul?** | Pikkus, keel, stiil |

**Näide (Few-Shot Prompting)** on neljas element ja kõige olulisem. See tagab, et hääl ei kõla nagu masin. See peaks juba olema `writing-samples.md` failina Project'i sees — sa ei pea seda iga promptiga uuesti andma.

Kui vastus ei tule sellisena, nagu lootsid — vaata allpool "Miks see ei töötanud?" sektsiooni.

---

## Skelett 1 — Otse ja asja kallale

```
Kirjuta mulle [vorm: email / LinkedIn sõnum / telefonikõne avasõnad] inimesele nimega [nimi], ettevõttest [ettevõte].

Kontekst, mis sa teadma pead:
- Nende roll: [ametinimetus, kui sul on see teada]
- Miks just nemad: [üks selge põhjus — mingi uus uudis, selge signaal või probleem, mis neil on]
- Miks just praegu: [ajastuse põhjus, kui olemas]

Eesmärk: [mida tahad et nad teeksid — vasta, broneeri kohtumine, edastaks kolleegile]

Lisainfo: [kui on midagi spetsiifilist, mida su tavaline stiilijuhend ei kata, maini seda siin]
```

**Kus kasutada:** Otse chat'i Project'is. Agent peaks puuduva info küsima, mitte välja mõtlema.

---

## Skelett 2 — Tee enne eeltöö ära

```
Enne kui mustandit kirjutama hakkad, uuri palun seda ettevõtet [URL / ettevõtte nimi].
Otsi üles: mida nad teevad, kes on nende klient, kas neil on olnud hiljuti mõni oluline uudis.
Too see info kirjas ka konkreetselt välja, ära jää üldsõnaliseks.

Kui eeltöö on tehtud, kirjuta [vorm] inimesele nimega [nimi], tema roll on [ametinimetus].
Eesmärk: [mida me tahame saavutada].

Kui sa ei leia veebist mitte midagi märkimisväärset, siis ütle seda mulle ja küsi, kuidas me edasi läheme.
```

**Kus kasutada:** Kui kontakt on uus ja sa pole jõudnud nende veebilehte vaadata. Web search tööriist peab Project'is sees olema.

---

## Skelett 3 — Anna CSV nimekiri ja lase masinal töötada

```
Siin on CSV nimekiri [kleebi siia või lae fail üles]. Veerud on failis.

Iga rea kohta kirjuta üks [vorm] mustand.

Reeglid:
1. Tee esimene mustand ja näita mulle enne ülejäänutega jätkamist.
2. Iga mustand peab vastama minu "Custom instructions" reeglitele ja "writing-samples" häälele.
3. Kui rea andmed on liiga nõrgad ja sa ei suuda head teksti teha, jäta see rida vahele ja anna mulle sellest teada. Ära mõtle välja fakte mida sa ei tea.
4. Lõpus tee kokkuvõte: mitu tükki valmis said ja mitu tükki sa vahele jätsid (ja miks).
```

**Kus kasutada:** Kui sul on valmis tabel (näiteks `prospects-template.csv`) ja sa tahad korraga mitu mustandit.

---

## Skelett 4 — Vastuse kokkupanek

```
Saaja nimega [nimi] vastas mulle. Siin on tema sõnum:

[kleebi vastus siia]

Kontekst:
- Eelmine suhtlus: [näiteks: esimene email või LinkedIn sõnum]
- Minu eesmärk: [mis on meie järgmine loogiline samm — lepime kohtumise kokku, vastan küsimusele, saadan pakkumise]

Kirjuta talle vastus. Võid tsiteerida üks või kaks lühikest lauset tema tekstist, et näidata, millele sa vastad.
```

**Kus kasutada:** Ideaalne järelkajastuseks või kui keegi päriselt su esimesele kirjale vastab.

---

## Miks see ei töötanud?

- **Kõlab liiga formaalselt või "võõralt"** → Kontekst-probleem. Kas `writing-samples.md` on Project Knowledge'is? Kas seal on 2+ näidet sellest kanalist (email, LinkedIn, DM)?
- **Tekst on liiga üldine, ei haaku saajaga** → Sa andsid liiga vähe konteksti saaja kohta või veebist ei tulnud midagi konkreetset. Täpsusta "miks just nemad" rida.
- **Liiga pikk ja lohisev** → Kirjuta prompti selgelt: "Maksimaalselt 3 lõiku, üks palve, ära aja niisama juttu."
- **Agent mõtleb fakte ja inimesi välja** → Ta rikub Custom instructions reeglit. Märgi mustandis `[fakt puudub — palun täienda]` ja tuleta talle meelde, et kõik info peab põhinema faktidel.
