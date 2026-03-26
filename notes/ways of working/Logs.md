I'm not sure if this is still entirely necessary since Claude Code does have a memory function where you can say 
`remember x` 
and it is supposed to remember.

But what I like to do is have an explicit log of decisions made, things worked on, things discussed but not necessarily resulting in actual work or code changes.

Honestly the best way to get this done is just ask
```
What's a good approach to creating a work-log system so I can explicitly ask you "log this" and you add a concise, LLM readable log to a context file.
```

And you should end up with something workable.  The key things you want would be:
- Not just a single log file that grows forever - it fills context when it has to be read by Claude.
- Ideally a system where one log file can only hold say 10 items, and then another file is created, with the date as it's filename.

Experiment with `remember` first as logging may now be just unnecessary overhead.  You should only really worry about it if you find yourself saying "remember the thing we worked on two days ago?" and it has no idea and starts searching your notes etc.

