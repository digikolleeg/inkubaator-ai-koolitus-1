# Stardipakett — Digikolleeg AI praktikum

Selles kaustas on töötoa starditükid. Kasuta neid samm-sammult: kõigepealt seadista Project, siis kontekst, siis hakka kirjutama.

## Mis siin on

| Fail | Mille jaoks |
|---|---|
| `custom-instructions.md` | Kopeeri Claude Desktop Project'i "Custom instructions" välja. See annab agendile rolli ja reeglid. |
| `prospects-template.csv` | Näidisandmestik 15 müügikontaktiga (Eesti SME-d, fiktiivsed). Asenda oma kontaktidega kui valmis oled. |
| `prompt-skeleton.md` | Neli valmis-skeletti, mida promptida agenti. Põhineb RÜKV raamistikul. |

## Soovituslik järjekord

1. **Loo Claude Desktop'is uus Project.** Anna nimi (nt "Müügiassistent").
2. **Paste `custom-instructions.md` sisu** Project'i Custom instructions välja (kogu plokk alates "Sa oled outreach-agent...").
3. **Lae Project Knowledge'isse oma portfoolio failid:**
   - `identity.md`
   - `communication-style.md`
   - `writing-samples.md` (vähemalt 2 näidet — Few-Shot Prompting'i tooraine)
   - `team-and-relationships.md` (kui sa pead sõnumeid juba tuttavatele inimestele)
4. **Testi `prompt-skeleton.md` Skelett 1-iga.** Vali üks rida `prospects-template.csv`-st, täida skelett, küsi agendilt mustand. Vaata, kas hääl kõlab sinu kirjutamise näidetena.
5. **Kui hääl ei klapi**, vaata `prompt-skeleton.md` lõpuosa — "Mis siis kui mustand ei kõla õigesti" diagnostika RÜKV järgi.

## Kus on portfoolio failid

Töötoas ehitad need konteksti-looja Skill'iga repos `digikolleeg/isiklik-kontekst`. Kui sa veel pole, alusta sealt:

- ZIP-allalaadimine: https://github.com/digikolleeg/isiklik-kontekst → "Code" → "Download ZIP"
- `skills/konteksti-looja/` kaustas on Skill ja paigaldusjuhend

## Kuidas need failid omavahel klapivad

```
   Portfoolio failid (isiklik-kontekst repo, sinu vault)
            │
            ▼
   Project Knowledge (Claude Desktop)
            │
            ▼
   Custom instructions (paneb agendi rolli) + sinu prompt (Skelett 1-4)
            │
            ▼
   Mustand sinu hääles
```

## Edasiminek

Kui see toimib ühe kontakti puhul, proovi Skelett 3 (CSV läbikäik). Kui see toimib, vaata `next-steps.md` (eraldi handout) — seal on rajamärgid, kuidas sa selle päevatöös käima paned ja kus järgmised tööriistad (Connector, Cowork, Routines) väärtust juurde annavad.
