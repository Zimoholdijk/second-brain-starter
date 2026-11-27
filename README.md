# Second brain starter

I'm Zimo Holdijk, and I made this starter so you can set up a second brain of your own: a folder of plain notes that Claude reads and writes for you, so that what you decide and learn in one conversation is still there the next time you need it. You make your own private copy of it on GitHub, and from then on it holds your notes.

It is free to use and adapt for yourself; selling it or offering it as a paid service needs my agreement (see [Licence](#licence)).

This starter is for people who are comfortable in a terminal. Everything happens through Claude Code, which needs a paid Claude plan or API credits, and it works on any platform with GitHub. If that isn't you, have a look at [Want help?](#want-help) further down before you start.

## What's inside

- [AGENTS.md](AGENTS.md) holds the rules Claude follows in the folder. It says how notes are named and linked and where each kind of thing goes, it keeps passwords and keys out altogether, it asks you before saving things like your health or your money, and it has Claude commit and push each save to your private repo, so your notes are backed up.
- The starting files and folders: `preferences.md` for how you like to be spoken to and written for, a log of what was saved, and folders for people, know-how and untouched originals. Your own folders are decided with you the first time you open it.
- Two skills for saving, in `.claude/skills/`. One files a conversation or a single fact when you say "file this", and the other files a document or an email you paste in.
- A pointer skill in [claude-app/](claude-app/README.md). Once your second brain is set up, it lets other Claude chats read it and save to it as well, including the app on your phone.

## How to start

You need three things on your computer first: [git](https://git-scm.com/), GitHub's command-line tool [gh](https://cli.github.com/) (signed in with `gh auth login`), and [Claude Code](https://code.claude.com/docs/en/setup).

1. On this page, click **Use this template**, then **Create a new repository**. Create it under your own account, give it a name such as `second-brain` and choose **Private**, because your notes will live there.
2. Clone your new repo and go into it: `gh repo clone <your-name>/second-brain && cd second-brain`.
3. Start Claude Code with `claude` and say: `Read START-HERE.md and follow it.`

Claude first checks that your copy really is private and stops if it isn't. Then it asks a few questions about you, agrees with you which folders fit your work and life, and saves the result to your repo with a first commit. You can change any of it later by asking.

One thing to know: in your copy, this page is replaced by the index of your own notes during that setup. You can always come back here to read it.

After that, say "file this" at the end of a conversation worth keeping, or paste a document or an email and say the same. To use it from other Claude chats too, follow [claude-app/README.md](claude-app/README.md).

## Filling it

Your second brain starts empty. If you have old Claude chats worth keeping, you can bring them in. The starter has no skill for that, but you can do it by hand with Claude Code: request an export of your data in Claude's settings, unpack it somewhere outside your second brain, and go through the chats together in small batches, deciding per chat whether it is worth finding again. It helps to agree first what "worth keeping" means for you and to write that under "What's worth keeping" in `AGENTS.md`, so that everyday filing follows the same rules.

## Want help?

For people who would rather not set this up alone, I offer a guided setup that needs no technical background, and coaching on working with a second brain day to day. You can reach me through [zimoholdijk.com](https://zimoholdijk.com).

If something in the starter doesn't work or could be clearer, please open an issue on GitHub. I don't merge pull requests for now.

## Licence

The files in this repository are © 2026 Zimo Holdijk and licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/); the full text is in [LICENSE](LICENSE). In short, you may share them, changed or unchanged, as long as you credit me, don't use them commercially and share them under the same licence. The notes you add yourself are your own and are not covered by this licence.

Two things I want to be clear about:

You may use and adapt these files to keep your own notes, including notes about your own job, business and clients.

You may not sell these files, or offer them as part of a paid product or service, such as a paid setup, workshop or course, without my agreement.

If you want to do something the licence doesn't allow, get in touch through [zimoholdijk.com](https://zimoholdijk.com).
