One good use for agents is in code review (or plan review).

For code review, you probably want to do it from multiple angles:
- Coding guidelines
- Component reuse
- Completeness
- Security regressions
- ...

So, just ask the robot

```
I want to set up some code review agents for checking changes I make to my codebase.  What domains of review would you suggest - I'm thinking coding guidelines, component reuse, completeness, security regressions, obsolete code removal...
```

... and just go from there.  Have it write the set-up prompts for the agents, and you'll end up with a handful of review bots.  You can imagine this same process for creating other types of review agents for plans etc.

Now you can wrap these agents in a skill
```
Create a skill that employs these agents and reports findings to you for summarisation called 'code-review'
```

So then after all that you can just invoke that skill:

```
/code-review
```