# Using your second brain from any Claude chat

Claude Code works in this folder directly. Every other Claude chat (the Claude app on your computer, claude.ai in a browser, the app on your phone) reaches it through GitHub: the chat opens your private repo, reads the rules in it and pushes what it saves. The small skill in [second-brain/](second-brain/SKILL.md) tells those chats where your second brain is.

You do these steps once, on your computer. The menus in Claude change now and then, so each step links to Anthropic's own help page; follow what the page shows if it differs from the wording here.

1. **Check the skill names your repo.** Open [second-brain/SKILL.md](second-brain/SKILL.md). It should name your own repo, like `yourname/second-brain`, in two places. If it still says `<owner/repo>`, or an old name after a rename, ask Claude Code in this folder to "set my repo name in the pointer skill".
2. **Zip the `second-brain` folder** that sits beside this file, so the zip holds the folder with `SKILL.md` inside it. On a Mac: right-click the folder in Finder and choose Compress; on another system, use its own way of making a zip. The zip appears beside the folder; it is only for uploading and is left out of your notes' backup.
3. **Add it to Claude as a skill.** [Use skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude) shows where to upload it. Make sure it is switched on.
4. **Connect GitHub in Claude, for this one repo.** Add the GitHub connector and install the Claude GitHub App on your account when Claude offers it. On GitHub's page, choose **Only select repositories** and pick this repo, so Claude can reach nothing else. [Use the GitHub integration](https://support.claude.com/en/articles/10167454-using-the-github-integration) has the details.
5. **Switch on code execution and file creation** in Claude's settings. Skills need it. See [Create and edit files with Claude](https://support.claude.com/en/articles/12111783-create-and-edit-files-with-claude).
6. **Try it.** In a new, normal chat, send: `Use my second-brain skill: add a line to the end of log.md in my second brain, in the log's own format, saying this was a test from a Claude chat, and push it.` Claude may ask your permission to open the repo. Then look at `log.md` on GitHub, or pull in this folder, and check the line is there.

After that, "file this", "remember that ..." and "what does my second brain say about ..." work in any Claude chat. If you ever rename the repo, do steps 1 to 3 again.
