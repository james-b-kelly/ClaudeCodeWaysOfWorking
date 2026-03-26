Model Context Protocol is one way for an LLM to call and API or service. It has the benefit of handling Auth without you needing an API key (which you don't want to give to Claude).

See what MCPs you have set up with
```
/mcp
```

To add an MCP you can generally just Google for that service + mcp, and hopefully you find something like this installation command for Linear:

```
claude mcp add --transport http linear-server https://mcp.linear.app/mcp
```

You run this in terminal in your project folder, then start Claude Code, and open your MCPs

```
/mcp
```

You'll see Linear.  Select it, and then select `Authenticate`.

This will open a browser window to authenticate you.

Once authenticated, you can ask things like
```
Tell me what tickets are in ToDo in Linear
```

MCPs are incredibly useful **but they can use a lot of context** - some more than others.  The Linear MCP seems to be fine, but the Atlassian one seems bloated.

### Alternatives to MCP

#### API 
You can get Claude to call APIs easily, but if you need to use an auth token you'll want to set that up in an environment variable on your system so it can use e.g. `$API_KEY` in calls.

#### CLI
If a product has a Command Line Interface it can sometimes be faster to use that - Supabase has a good CLI so I installed that, then just told Claude to remember about it in it's CLAUDE.md file.

