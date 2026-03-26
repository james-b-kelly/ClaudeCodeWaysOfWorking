
The `CLAUDE.md` file contains some context for Claude to look at whenever it is started (i.e. whenever you run `claude` from the terminal in that folder).

The context in this file is intended to "remind" Claude what to pay attention to for this project, what to remember for every session.  So this is it's central source of "who" it is and how to behave.

Some examples of what would go in your CLAUDE.md
- A description of the project, your role on it.
- General instructions on how to proceed when prompted (i.e. when the user references X, look at notes on Y).
- A high level overview of your project goals.

Some things NOT to put in your CLAUDE.md
- Extensive documentation / reference material.

Some points about CLAUDE.md
- Keep it fairly minimal.  This takes up context so it shouldn't be hundreds of lines long.
- **You don't have to write it yourself**.  Whenever you find a good way of working just ask CC "Can we add/set this up in your CLAUDE.md?".
- You can use it to refer to OTHER context files.  Ask CC "Set up a folder to keep context files for reference" and it'll do something like

```
CLAUDE.md
.claude/context
```

so you have a hidden folder with context files that Claude Code can reference - and which is can maintain itself.

So get hidden files and folders to show up, run

```
defaults write com.apple.finder AppleShowAllFiles TRUE ; killall Finder
```

So let's say you used CC to analyse a code base for structure, you could then say "Write this structure to a context file", and you might get

```
CLAUDE.md
.claude/context/codebase-structure.md
```

And so Claude Code knows where to look for these context files, you could say

```
Create an index in your CLAUDE.md file to track these context files and what they relate to.
```

This will cause CC to add a section to the CLAUDE.md with pointers to these files, and likely a line to remind itself to update when these files change.

This is essentially how you build a working system with Claude Code - if you think you might need a system for something, ask it what a good approach would be.

You can use this approach to create context files for things like current high level goals of the project, tone-of-voice guides for writing notes, emails, etc.  Really anything you want CC to have quickly to hand for reference (and you don't need to read it yourself, otherwise you can add it to your notes).

