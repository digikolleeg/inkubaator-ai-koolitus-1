# Töötoa repo — tööjuhised Claude'ile

See on avalik repo Digikolleegi inkubaatori AI praktikumi jaoks (juuni 2026). See on suunatud osalejatele.

## Mis siin repos on?
- `starter/` (Stardipakett): baasmaterjalid (CSV, käsklused, kohandatud juhised).
- `mcp-setup.md`: Filesystem Connector'i paigaldusjuhend.
- `next-steps.md`: "Esmaspäeva hommiku" meelespea.
- `failure-modes/`: näited, kus AI väljund läheb viltu, ja kuidas neid vigu ära tunda.
- `slides/`: esitluse PDF.
- `assets/`: QR-kood ja abistavad pildid.

## Mida see repo EI OLE
- See ei ole konteksti-looja Skill ega portfoolio süsteem (need on `digikolleeg/isiklik-kontekst` repos).

## Reeglid redigeerimisel
- Osalejatele suunatud tekstid on alati eestikeelsed. Kood, failiteed ja tehnilised terminid jäävad ingliskeelseks.
- Ära loo faile huupi. Kui faili pole slaididel mainitud või pole otsest käsku antud, siis ära seda loo.

## Kuidas `Stardipakett.zip` faili uuendada, kui `starter/` muutub
```bash
cd ~/Projects/inkubaator-ai-koolitus-1
rm -f Stardipakett.zip
zip -r Stardipakett.zip starter/
```

## Seotud repod
- `digikolleeg/isiklik-kontekst` — Eesti keelde kohandatud isikliku konteksti-portfoolio süsteem ja konteksti-looja Skill.
