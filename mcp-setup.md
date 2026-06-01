# Connector setup — Claude Desktop + your vault

> **EN DRAFT — Heigo to Gemini-translate to EE before workshop.**

This guide gets Claude Desktop reading and writing files in your vault folder, so the konteksti-looja Skill can build your portfolio files for you (instead of you copy-pasting chat output into files manually).

**Time:** ~5 minutes.
**You need:** Claude Desktop installed, a vault folder on your Mac, Claude Pro (Filesystem Connector is a Pro feature).

## What MCP / Connector actually is

Claude Desktop on its own can only see what you paste into the chat. **Connectors** let it reach outside the chat — to files on your computer, to APIs, to services. The **Filesystem Connector** specifically gives Claude read/write access to a folder you choose. Nothing else on your machine is visible to it.

Once enabled, you can say things like *"read my identity.md and update the role section"* and Claude will literally open the file, read it, and write the change back. That's the difference between an AI that talks about your work and one that touches your work.

## Step 1 — Find your vault folder

Your vault is the folder containing `portfolio/` (with your `identity.md`, `communication-style.md`, etc.). If you followed the workshop, this is the folder you unzipped from the `isiklik-kontekst` repo.

Typical paths:
- `~/Documents/isiklik-kontekst/`
- `~/Projects/isiklik-kontekst/`
- `~/Desktop/isiklik-kontekst/` (if you just downloaded the ZIP today)

Copy the full path — you'll paste it in Step 3.

## Step 2 — Enable Filesystem Connector

1. Open Claude Desktop
2. Click your avatar (bottom-left) → **Settings**
3. Find the **Connectors** section
4. Enable **Filesystem**

> Note: Connectors require Claude Pro. If you don't see them, check that you're signed in and your Pro trial is active.

## Step 3 — Point Filesystem at your vault

1. In the Filesystem Connector settings, click **Add folder** (or similar)
2. Navigate to your vault folder (the path from Step 1)
3. Confirm

Claude Desktop now sees only this folder. It doesn't have access to anywhere else on your machine.

## Step 4 — Test it works

Open a new chat. Type:

> *"Loe palun fail `portfolio/identity.md` ja võta üheks lauseks kokku, kes ma olen."*

If Claude returns a summary of your identity file, the Connector is working. If you get *"I don't have access to files"* or similar, recheck Step 3.

## Step 5 — Use it with the Skill

With Connector active, the konteksti-looja Skill can write directly to your vault. When the Skill asks where to save, say *"kirjuta see vault-faili"* — it will use the Connector to write the file in the right location, with the right frontmatter.

## If Connector doesn't work

You can still use the Skill — the fallback path is: the Skill outputs each file's content as a chat code block, you copy-paste it into the file manually. Slower, but works on any plan and any setup.

See the Skill's README at `digikolleeg/isiklik-kontekst` under `skills/konteksti-looja/` for the manual flow.

## Troubleshooting

- **Connector option missing** → Claude Pro not active. Check your subscription / trial status.
- **"No access to files" after setup** → folder permissions. On macOS, Claude Desktop may need Full Disk Access in System Settings → Privacy & Security.
- **Connector sees folder but Claude won't write** → the file might be open in another app (Obsidian, VSCode). Close it, try again.
- **You want Claude to NOT see a sub-folder** → move it outside the vault root, or add to a `.claudeignore` if supported in your version.
