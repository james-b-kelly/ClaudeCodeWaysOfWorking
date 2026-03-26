
LLMs make predictions on the next token in a string of tokens by dropping that string of tokens though it's massive black box of numbers (from it's initial training data).

Each word you prompt, and each word it responds with, gets appended to that string of tokens and dropped back through the black box for the next token.

The current string of tokens is it's "context", and it can only be so big.  CC has a context window of 1 million tokens.

Every time you start Claude Code it has a fresh context window (albeit with some initial hidden context like guard rails etc. that Anthropic have put it).

You can clear the context window yourself with `/clear`.

You can set up Claude Code to show the % of context used/available with the command 
```
/statusline
```

What this means is:
- **You have to be mindful of keeping a given context window constrained to one subject/topic/problem**.  You do not want to keep one context window going for multiple topics - this is where you will start to get hallucinations, since it's predicting tokens based on stuff not related to your current conversation. 
	- Long context windows increase the chance of hallucinations.  Like humans, LLMs pay more attention to the beginning and end of a conversation and less to the middle, so the longer the context, the less it can put it all to use in predicting well. 
- Once the context window gets to about 60%, wrap that session up and call `/clear`.

