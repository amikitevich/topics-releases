---
name: tcs
description: Use the tcs CLI for anything about the user's topics: Markdown outlines of items with notes and a done state, also shown in the Things web app. Use it when the user asks to list, read, add, edit, move, resolve, reopen or delete topics or topic items, or pastes a Things link (/topics/NAME?item=ID) or a `tcs get` command, even if they do not name tcs.
---

# Topics: use the tcs CLI

When the user talks about a topic, their topics, or items in a topic, they mean their tcs vault. Do the work with `tcs`; the vault is already configured.

1. Run `tcs --help` first, and `tcs help COMMAND` before you use a command. The help has the options, examples and rules.
2. Find targets with `tcs list --json` and `tcs outline TOPIC --json`. Use item IDs, not titles or indexes.
3. After a change, read the result back.

If `tcs` is not found, tell the user to install Topics or add `~/.local/bin` to PATH.
In a source checkout of Topics, run `bun run --silent tcs` instead of `tcs`.

## Rules

- Change only what the user asked for. A pasted link or reference is not a request to change it.
- Deletion is permanent and does not ask. If a title matches more than one item, ask which one.
- Do not edit topic files directly or call the web app's HTTP API.
- If you did not see a write's JSON result, read the topic before you retry. A repeated `append` duplicates text.
- Do not run `tcs config set vault`. Never delete lock or journal files.
