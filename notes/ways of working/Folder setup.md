Claude Code runs in a given folder, so if I'm working a project "Omega" and it has an iOS app and a React app, I'll structure a folder like this:

```
/omega
	(git repo)
	
/omega/notes
	
/omega/ios-repo
	(git repo, in the main repo's .gitignore)
	
/omega/react-repo
	(git repo, in the main repo's .gitignore)
```

I will run Claude Code in the `/omega` folder, and by default it will pay attention to what happens in this folder and its subfolders.

When Claude Code launches, ask it to

```
Set up your CLAUDE.md file
```

See what the [[CLAUDE.md]] file is for.

