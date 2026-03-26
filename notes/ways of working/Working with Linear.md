I use Linear for working with tickets with Claude Code.

You can work with Jira to similar end, but Atlassian's MCP is pretty slow.

See the [[MCP]] section for instructions on how to install the Linear MCP.

## Labels
I use labels to mark stages of a workflow. 

In Linear, go to Account (your account icon/name), Settings.

Scroll down on the left and select your team (you'll only have one to start), 

In the main panel choose Members, and add Claude as a member.

Then select "Issue Labels".

These are how I configure my labels - the workflow labels are under a group, which in Linear means only one can be selected at a time.

![[Image 26-03-2026 at 12.13.png]]

After setting these up, with descriptions next to them, I just asked Claude to take a look at them and help me set up a way of working with them:

```
Take a look at my team labels on Linear.  I want to set up a way of working where you are able to know what to do with a ticket based on its label, and are able to move the ticket to the next stage of development.
Also take into account who a ticket is assigned to and what status it's in: e.g. if it's assigned to you, in ToDo, and Ready for Evaluation, you can consider that ticket 'actionable'.  If it's in the backlog, it's not actionable unless I ask you specifically to look at it. 
```

You get the idea.  The point is to have a conversation with Claude Code to build into itself the context it needs to know what the labels mean and what order they can transition.

What I ended up with was in CLAUDE.md it has a list of the labels, their IDs, and when to transition between them, etc. 

So now, if I have an idea of a feature I want to build I will:
- Create a ticket, write a brief description.
- Assign it to Claude.
- Put it in Todo.
- Give it the *Ready for Evaluation* label.
- Run Claude and say "Let's look actionable tickets".
- Claude will then evaluate the feature, write up an initial plan or outline, then assign to me with *Ready for Evaluation*.
- I then review that, and assign it back to Claude with *Ready for Planning*.
- CC plans it out more thoroughly, suggesting breaking it down into work units, assigning back to me for a final check.

And so on - refinement into sub tickets - and then implementing in a fresh context.

For big plans or things you just want to back-and-forth on, it's usually better to just do it with Obsidian.  Ask CC to plan something out, and write it to your notes under a `/plans` folder.  Then you can work with it to refine it.  Then you could say "Make a ticket for this".