# Stardipakett — Digikolleeg AI praktikum

Siin on sinu töötoa stardipakett. Kasutame neid samm sammult: algul Project, siis kontekst ja seejärel saad hakata mustandeid looma. 

## Mis karbis on?

| Fail | Milleks see on? |
|---|---|
| `custom-instructions.md` | Sinu agendi aju ja mängureeglid. Kopeeri see otse Claude Desktop Project'i "Custom instructions" välja. |
| `prospects-template.csv` | 20 suvalist Eesti ettevõtet testimiseks. Hiljem asenda need oma päris klientidega. |
| `prompt-skeleton.md` | Neli valmis skeletti agendi käivitamiseks. |

## Kuidas alustada?

1. **Tee Claude Desktopis uus Project.** Anna talle nimi, mis ütleb, mida ta teeb (näiteks "Müügiassistent").
2. **Kopeeri `custom-instructions.md` sisu.** Kleebi see Projecti "Custom instructions" kasti. Kõik alates sõnadest "Sa oled outreach-agent...".
3. **Lisa oma kontekst.** Lae Project Knowledge'i alla oma portfoolio failid:
   - `identity.md` (Kes sa oled)
   - `communication-style.md` (Kuidas sa räägid)
   - `writing-samples.md` (Anna talle vähemalt 2 päris näidet, muidu ta hakkab improviseerima)
   - `team-and-relationships.md` (Kui tahad kirjutada inimestele, keda sa juba tead)
4. **Tee esimene test.** Võta `prompt-skeleton.md` ja kasuta Skelett 1-te. Vali testandmetest üks rida, täida lüngad ja vaata, mis välja tuleb. Kas kõlab nagu sina?
5. **Kui hääl ei klapi...** Siis vaata faili `prompt-skeleton.md` lõppu – seal on diagnostika, mis näitab sulle, kuskohas asi viltu võib minna.

## Kust ma oma portfoolio failid saan?

Töötoas me ehitame need valmis. Kasutame selleks spetsiaalset konteksti-looja Skilli, mis elab siin: `digikolleeg/isiklik-kontekst`. 

Kui sul seda veel pole, siis tee nii:
- Lae alla siit: https://github.com/digikolleeg/isiklik-kontekst → "Code" → "Download ZIP"
- Ava `skills/konteksti-looja/` kaust ja järgi juhendit.

## Kuidas need klotsid omavahel suhtlevad?

```
   Sinu portfoolio (isiklik-kontekst, sinu enda failid)
            │
            ▼
   Project Knowledge (Claude Desktop)
            │
            ▼
   Custom instructions + sinu prompt (Skelett 1-4)
            │
            ▼
   Mustand sinu enda häälega
```

## Mis edasi?

Kui see toimib ühe kontakti puhul, proovi Skelett 3, mis võtab ette terve CSV nimekirja. Kui ka see toimib, siis loe läbi `next-steps.md`. Sealt saad selged juhised, kuidas see süsteem päriselt oma igapäevatöösse integreerida.
