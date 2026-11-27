---
name: file-chat
description: Saves the current conversation, or a single fact, into this second brain. Writes or updates one dated note beside the right hub page, updates the hub, then commits and pushes. Use when the owner says "file this", "file this chat", "save this to my second brain", "remember this" or "remember that ...".
---

# File a chat or a fact

If `START-HERE.md` is at the top of this folder, stop and follow it before anything else. Read `AGENTS.md` first (structure, hub pages, tags, privacy, writing rules). New hubs start from `hub-template.md` in this skill's folder.

## Which one?
- "file this" / "save this to my second brain": a **chat note** (below).
- "remember that X" about one fact: a **single line** (below).

## Chat note
**First:** say the plan in one line (which hubs you update, which notes you create), then carry on without waiting; the owner can stop you if the place is wrong (AGENTS.md, Filing).

A conversation held here has no original to store. A chat pasted in from elsewhere goes into `source/chats/` first, after the checks in `AGENTS.md`, Filing, step 1. A pasted document or email is not a chat: use the file-document skill for it.

1. Find the hub the conversation is about (check `README.md` and each hub's `aliases`). If none fits, propose one in one line: a folder from "Folders" in `AGENTS.md` and a name. Create it from the hub template once the owner agrees. If "Folders" still says "Not decided yet", tell the owner the folders haven't been chosen, offer to choose them together now, and file the note once that is done. Never file outside a listed folder, `people/` or `knowledge/` without asking.
2. Already filed earlier in this conversation? Update that note. Otherwise check the hub's folder for a note on the same topic from today.
3. Write or update `<hub folder>/YYYY-MM-DD-<topic>.md`:
   ```markdown
   ---
   title:
   type: chat
   date: YYYY-MM-DD
   keywords: []
   ---
   ## Summary
   Where things stand now, 3 to 6 lines. Rewritten at every filing.

   ## Checkpoints
   - [decision] YYYY-MM-DD: what changed, and why. Only ever add lines here; never edit old ones.
   ```
4. If the chat produced something (a plan, a draft, a list), save it in full as its own file beside the note and link it from the note. Never only summarise it.
5. Update the hub: add the note under `## Notes` (newest first); carry new decisions and changed facts into `## Summary` as tagged lines; a replaced line moves unchanged to the hub's `## History`. Each person the chat involved who already has a page gets one dated line there linking to the note; a new spelling of their name goes into that page's `aliases`. Ideas and positions the owner stated go into the note in their exact words, quoted.
6. Todos: list the ones you would add, one line each, and add only those the owner confirms.

## Single line
1. Find the hub it belongs to. None fits? Ask. A new person page may start from one fact; other hubs need more substance.
2. Add one dated, tagged line under that hub's `## Summary`: `- [fact] YYYY-MM-DD: ...`. If it replaces an existing line, move the old line to the hub's `## History` list (see "Hub pages" in `AGENTS.md`).

## Always
- Leave out passwords, keys, codes and account numbers (see Privacy in `AGENTS.md`). Anything on the owner's `## Ask first` list: ask before saving it.
- Add the hub to `README.md` if it is new, and one line to `log.md`.
- Back up to GitHub as in `AGENTS.md`, Filing, step 6: first `git pull --ff-only` (other Claude chats save here too; if that fails because both sides changed, `git pull --no-rebase`, and if it reports a conflict, stop and tell the owner in one plain line that two versions need joining and that someone who knows git can help), then commit and push with a short message. If this folder has no `.git` folder, the backup isn't set up yet: skip this and tell the owner in one line that the note is saved on this computer only. If the push fails (offline, sign-in expired), keep the local commit, tell the owner in one plain line that it is saved on this computer and will go to GitHub next time, and stop there. Never force-push, reset or rebase.
- Reply with the file path and one line on what was saved.
