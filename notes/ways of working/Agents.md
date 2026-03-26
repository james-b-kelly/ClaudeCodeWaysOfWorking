
You can see your agents with `/agents`.

In my opinion people get carried away with agents and having different roles and personalities and what not.  I've seen Github repos with a full company replicated in agents with all the different job roles - that's just CEO role play.  But they can be useful in one particular way:

### Agents have their own context windows
This is what can make agents useful - they don't share the context of Claude Code or each other.  So if you want to do a task like fetch a web page and save it's context as text to a notes file, you'd ask it to spawn an agent to do that.  Then the text from that website doesn't become part of your Claude Code session's context.  Agents are use-and-dismiss.

So you'd probably want to create one for, say, doing market research.   This is where you are chatting with Claude, you want it to go off and grab info about 3 competitors, and write it to an .md file in your notes, but you don't want to use up your context window on that.  You can throw it to a background agent, then Claude Code can read the concise output.

Like anything else with CC, you can just ask it to create agents.
```
Let's create an agent for doing market research in the domain of X
```
And it'll work with you to refine the prompt to set up the agent. 

### Agents in parallel

You can simply say `Let's have 5 of our market research agent look at these companies at the same time and write their findings to my notes`.

Often Claude Code will spin up multiple generic agents for certain things by itself.

