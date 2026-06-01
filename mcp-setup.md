# Connectori seadistamine — Claude Desktop ja sinu infobaas (vault)

See juhend aitab sul seadistada Claude Desktopi nii, et ta saaks sinu arvutis asuvaid faile (infobaasi) otse lugeda ja muuta. See on oluline, et konteksti-looja Skill saaks su portfoolio faile automaatselt ehitada – muidu pead sa Claude'i pakutud tekste ise käsitsi failidesse kleepima.

**Aeg:** ~5 minutit.
**Mida sul vaja läheb:** Paigaldatud Claude Desktop, sinu arvutis asuv kaust ja Claude Pro pakett (Filesystem Connector eeldab Pro versiooni).

## Mis see MCP ehk Connector tegelikult on?

Iseseisvalt näeb Claude Desktop ainult seda infot, mille sa talle otse vestlusaknasse kleepid. **Connectorid** annavad Claude'ile käed — need lubavad tal suhelda välismaailmaga, olgu selleks siis failid sinu arvutis, API-d või muud teenused. **Filesystem Connector** on spetsiifiline tööriist, mis annab Claude'ile lugemis- ja kirjutamisõiguse sinu valitud kaustale. Ülejäänud arvutile tal ligipääsu ei ole.

Kui see on seadistatud, saad öelda näiteks: *"Loe mu `identity.md` faili ja uuenda seal minu rolli kirjeldust."* Claude avab faili, loeb selle läbi ja salvestab muudatused ise. See ongi vahe AI-l, kes ainult räägib sinu tööst, ja AI-l, mis päriselt teeb sinu tööd.

## Samm 1 — Leia oma infobaasi kaust

Sinu vault on kaust, kus asub `portfolio/` kataloog (milles on omakorda `identity.md`, `communication-style.md` jne). Kui sa tegid töötoas kõik sammud kaasa, on see sama kaust, mille sa `isiklik-kontekst` repost alla laadisid ja lahti pakkisid.

Tüüpilised asukohad:
- `~/Documents/isiklik-kontekst/`
- `~/Projects/isiklik-kontekst/`
- `~/Desktop/isiklik-kontekst/` (kui sa laadisid ZIP-faili just täna alla)

Kopeeri selle kausta täispikk failitee (path) — sul läheb seda 3. sammus vaja.

## Samm 2 — Lülita Filesystem Connector sisse

1. Ava Claude Desktop.
2. Klõpsa vasakul all nurgas oma profiilipildile → **Settings**.
3. Leia **Connectors** sektsioon.
4. Lülita **Filesystem** sisse.

> Märkus: Connectorid eeldavad Claude Pro olemasolu. Kui sa neid ei näe, veendu, et oled sisse logitud ja sinu Pro on aktiivne.

## Samm 3 — Suuna Connector oma vault-kaustale

1. Filesystem Connectori seadete all klõpsa **Add folder** (või midagi sarnast).
2. Otsi üles oma vault-kaust (sammus 1 kopeeritud asukoht) ja vali see.
3. Kinnita valik.

Nüüd näeb Claude Desktop ainult seda ühte kausta. Ta ei pääse ligi ühelegi teisele failile sinu arvutis.

## Samm 4 — Testime, kas töötab

Ava uus vestlus ja kirjuta:

> *"Loe palun faili `portfolio/identity.md` ja võta ühe lausega kokku, kes ma olen."*

Kui Claude vastab kokkuvõttega sinu identity failist, siis Connector töötab. Kui saad vastuseks midagi stiilis *"I don't have access to files"*, mine tagasi ja kontrolli 3. sammu.

## Samm 5 — Kuidas seda Skilliga kasutada

Kui Connector on aktiivne, saab konteksti-looja Skill kirjutada otse sinu vault-kausta. Kui Skill küsib, kuhu andmed salvestada, vasta lihtsalt *"kirjuta see vault-faili"* — ta kasutab Connectorit, et kirjutada andmed õigesse kohta ja õiges formaadis.

## Mis siis, kui Connector ei tööta?

Saad Skilli ikkagi kasutada — varuvariant on lihtne: Skill annab sulle uue faili sisu vestlusaknas ja sa kopeerid selle ise õigesse faili. See on natuke aeglasem, aga töötab iga paketi ja iga seadistusega.

Manuaalse töövoo juhised leiad Skilli README-failist asukohas `digikolleeg/isiklik-kontekst` (vaata `skills/konteksti-looja/`).

## Levinumad probleemid

- **Connectori valikut ei ole näha** → Claude Pro ei ole aktiivne. Kontrolli oma tellimuse või prooviperioodi staatust.
- **"No access to files" pärast seadistamist** → Probleem kausta õigustega. MacOS-is võib Claude Desktop vajada failidele ligipääsuks Full Disk Access luba (System Settings → Privacy & Security alt).
- **Connector näeb kausta, aga Claude ei suuda kirjutada** → Fail võib olla mõnes teises programmis (nt Obsidian, VSCode) avatud ja lukus. Sulge see ja proovi uuesti.
- **Tahad, et Claude EI näeks mõnda alamkausta** → Tõsta see kaust vault'ist välja või lisa sinna `.claudeignore` fail (kui sinu Claude'i versioon seda toetab).
