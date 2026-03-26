
You can see the list of skills with `/skills`.

A skill is really just a prompt, saved.  It's useful if you find yourself using the same prompt over and over again.  For example, I always found myself getting to the end of a context window saying 
```
Give me the prompt for continuing this task in a fresh context
```
And CC would give me a short prompt to continue the task in hand after calling `/clear`.

So I created a skill by saying
```
Create a skill that takes the current task and creates a prompt to continue it in a fresh context, then saves it to a file which can be referenced in a fresh context.  It should be triggered when the user says something "let's continue this in a fresh prompt" or similar.  And we'll need to update your CLAUDE.md to remind yourself to look for this continuation prompt on launch.
```

So now I just say "let's continue this later", and wait for it to save the file.
Then `/clear`
Then `continue`

I have skills for things like sorting out my To Do notes at the end of the day, running code reviewers... any time I find myself with a useful little run of prompts I'm running again and again, I just ask "Can we wrap this up in a skill" and Claude Code will do it.

