# Continue this project in Codex on Kali

This folder carries the working conversation context. It is readable Markdown, not a native Codex session import. The full site is a separate encrypted backup in the repository.

## Get the current repository

```sh
git clone --branch codex/wordpress-backup --single-branch https://github.com/Aishpra/Kuntrooversie.git
cd Kuntrooversie
```

If you already cloned it, run `git pull` in that clone before starting. Open this project folder in your Codex environment. Read `AGENTS.md` and the two handoff Markdown files.

## Starter message to paste into the new chat

> Continue the Kuntroversie project from this handoff. Read AGENTS.md, handoff/CONVERSATION-SUMMARY.md, handoff/CURRENT-STATE.md, and RESTORE-INSTRUCTIONS.md first. Inspect this Kali environment, verify the encrypted backup volumes, and help restore the full WordPress database and site into an isolated local test setup. I will provide the archive password privately if needed. Preserve all original layouts, full animations, Elementor edits, Blocksy integration and WooCommerce data. Verify the restored pages and commerce before further edits. Merchant/hosting details and new factual product content are deferred; do not invent them or activate live payments.

## Portable ZIP supplied in the original chat

The owner also received a local `KUNTROVERSIE-KALI-CONVERSATION-HANDOFF.zip`. It contains these context documents, screenshots/review notes and a private restore-key file. **Do not upload that ZIP or its key to the public repository.** It does not duplicate the large site archives; download those from GitHub.

Codex project instructions reference: https://developers.openai.com/codex/guides/agents-md
