# Workshop repo — operating notes for Claude

Public repo for the Digikolleeg incubator AI praktikum (2026-06). Attendee-facing.

## What this repo is
- The Stardipakett: starter materials (CSV, prompts, custom instructions)
- mcp-setup.md: Filesystem Connector setup guide
- next-steps.md: Monday-morning one-pager source
- failure-modes/: walk-throughs of common AI output problems
- slides/: deck PDF
- assets/: QR code + images

## What this repo is NOT
- Not the planning hub (`~/Projects/workshop/` is)
- Not the konteksti-looja Skill or the portfolio system (`digikolleeg/isiklik-kontekst` is)
- Not Heigo's personal vault (private fork `iHeigo/digikolleeg-kontekst` is)

## Editing rules
- Attendee-facing copy is Estonian. Code, file paths, technical terms in English.
- Heigo writes the Estonian. Claude drafts in English if asked, but does not translate to Estonian — that output reads as a translation and is not usable.
- No real prospect data from Heigo's äriregister Group A / Group B lists.
- Don't add files speculatively. If a file isn't referenced from the deck or directly asked for, don't create it.

## Regenerating Stardipakett.zip after starter/ changes
```bash
cd ~/Projects/inkubaator-ai-koolitus-1
rm -f Stardipakett.zip
zip -r Stardipakett.zip starter/
```

## Related repos
- `digikolleeg/isiklik-kontekst` — Estonian fork of the personal-context-portfolio system + konteksti-looja Skill
- Planning hub: private, at Heigo's `~/Projects/workshop/`
- Heigo's personal vault: private fork `iHeigo/digikolleeg-kontekst`, cloned at `~/Projects/digikolleeg-kontekst/`
