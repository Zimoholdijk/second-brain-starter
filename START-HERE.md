# Start here

For the AI working in this folder. The owner has opened this folder for the first time and wants it set up as their second brain. Work through the steps in order, one at a time, in plain words. Each step first checks whether it is already done, so this file is safe to run again after a break.

## 0. Is this their own private copy?

Run every command in this file from the folder that holds this file. First check that this folder is itself a git repo: `git rev-parse --show-prefix` must succeed and print nothing. If it fails, or prints a path (this folder sits inside some other repo, for example a download unpacked there), treat it as "no origin" below.

Then run `git remote get-url origin` and take the owner and repo name from the address, whatever its form (https or ssh, with or without `.git`), ignoring capitals.

- **The address names `Zimoholdijk/second-brain-starter`, or there is no origin.** This folder is the starter itself or a download of it, not someone's second brain. File nothing, save nothing, and skip every step below. If they want their own second brain, tell them how to get a copy: on the starter's GitHub page, "Use this template", choose Private, clone that copy and open it instead. If they are editing the starter itself, make the edits they ask for and nothing more, and commit only when they ask. If they ask you to file something here anyway, explain why not and still don't: a note saved here has no private copy of their own behind it.
- **Otherwise,** check the copy is private with `gh repo view <owner>/<repo> --json visibility,isInOrganization`, naming the owner and repo you took from the origin.
  - If `visibility` is anything other than `PRIVATE` (public, or "internal" inside an organisation): stop. Nothing is saved or pushed until it is private. They can make it private in the repo's settings on GitHub. If it is a fork, GitHub does not allow that: they make a fresh copy with "Use this template" and Private chosen, and open that one.
  - If the check cannot run (`gh` is missing or not signed in, the origin is not on GitHub, or `gh` cannot find the repo): stop and say what is needed. Never carry on unchecked.
  - If `isInOrganization` is true: the repo belongs to an organisation, so its owners, and possibly its members, can read it even though it is private. Tell them that in one line and carry on only if they say that is what they want; otherwise they make a copy under their own account.
  - Only if `visibility` is exactly `PRIVATE`: carry on.
- Check `git config user.name` and `git config user.email` both answer. If either is empty, ask them to set a name and an email address for their saves before the first commit. GitHub's private no-reply address keeps their real address out of every save: `gh api user --jq '"\(.id)+\(.login)@users.noreply.github.com"'` prints it.

## 1. Put the index in place

If `INDEX-TEMPLATE.md` exists: replace the contents of `README.md` with the contents of `INDEX-TEMPLATE.md`, then delete `INDEX-TEMPLATE.md`. From now on `README.md` is the index of their notes.

## 2. A few lines about them

`preferences.md` is the first thing any AI reads here, so no conversation starts cold. Two sections are filled now, "About me" and "Talking to me". For each of the two that still has its example line (a line in italics starting `_For example` or `_A few lines`), ask its questions one at a time and write the answers in their own words as lines under the heading. Remove the example line only when both of the section's questions are answered, so a break leaves it in place. Leave a section that has no example line.

- "About me": who are you, and what kind of work do you do? What do you want this second brain to help you with?
- "Talking to me": how do you like answers, short or detailed, with or without examples? Is there anything an AI assistant does that annoys you?

"Writing in my name" keeps its example line until they bring it up; don't ask about it here.

## 3. Their folders

This step has three parts, each with its own check, so a break in the middle is picked up where it stopped.

If `AGENTS.md` still says `_Not decided yet._` under `## Folders`:

- Ask what their work and life consist of right now: what they are working on, what they are planning, what they keep losing track of. One question at a time. Don't suggest folder names before you have heard them.
- Propose three to six top-level folders (lowercase, dashes), each with one line on what goes in it and one example page taken from what they said. Let them change, merge or drop folders until it fits.
- First write the map: in `AGENTS.md`, replace only the line `_Not decided yet._` with a table with the columns "It's about...", "Goes to" and "For example", one row per folder, plus rows for `people/` and `knowledge/`. The examples are page names taken from what they told you; where they named nothing that fits a row, leave its example empty and never invent a person.

For each folder in the map that does not exist yet: create it, with a one-line `README.md` inside.

If `README.md` still has the `<!-- Your own folders ... -->` comment:

- Replace that comment with one `## <Folder>` heading per folder in the map, each followed by `What goes here: [<folder>/](<folder>/README.md).` and `_No pages yet._`.

## 4. Name their repo in the pointer skill

Open `claude-app/second-brain/SKILL.md`. Read the repo name it holds now, in the sentence "My second brain is the private GitHub repo ..." (it is `<owner/repo>` until someone fills it in). Replace every occurrence of that name in the file with this repo's current name, the owner and name you took from the origin in step 0.

## 5. Finish

In this order:

- If `log.md` has no `first setup` line yet, add one in its own format: today's date, `manual`, `first setup`, and the files and folders created.
- Remove this file and commit everything in one command: `git rm -q START-HERE.md && git add -A && git commit -m "Set up my second brain"`.
- Push with `git push origin main`. If the push fails, keep the commit and say so in one line, as "Filing" in `AGENTS.md` describes.

Then:

- Tell them in a few lines what they now have: saying "file this" at the end of a conversation saves it here; pasting a document or an email and saying "file this" works too; and `claude-app/README.md` explains how to use this folder from any Claude chat, also on their phone.
- If their first message asked for something else (to file a note, to look something up), do that now.
