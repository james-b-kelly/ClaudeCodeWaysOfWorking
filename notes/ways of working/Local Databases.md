This might only be useful in some circumstances, but you can ask Claude Code to set up local databases for you to store info in while discussing things with it.

For example, you find yourself exploring a large codebase over and over again and it's tough for Claude Code to keep track of all of those components. Even with context files that can end up being a lot of text to explain relationships between components and functionality.  You'll find it doing loads of `grep` calls over and over.

So you can ask it to set up a local SQL database to contain information about components and their relationships. 

```
I want you to set up a local SQL database so that we can save information about components in the codebase and how they relate to one another and, briefly, their functionality. As we explore the code base over time, we should add to this and maintain it. So for example if we delete a component, we have to remember to remove it from this database. Make sure to keep track of this database in your CLAUDE.md file. 
```

Claude can then just interact with this database, but it's a bit cleaner to wrap it in an MCP - this will give it a set of 'commands' (almost like api endpoints) it can use to access the database.

```
I want you to set up an MCP locally to wrap around this database. 
```

It'll then work with you to create that.

So now when you say "What components are associated with Search?".  It can produce an answer in seconds and not burn through an ocean of tokens to find it

### Vector Databases
This is a very specific use case but I found it extremely valuable in one case.

 it's very useful where you have a large set of unstructured textual data that you can fetch and save locally.   In our case it was 3,000 ProductBoard notes  consisting of email chains and other bits of text from users, that nobody was ever going to wade through.

First take a look at the [[Scripting]] note for how I downloaded all our customer feedback notes from Product Board to local JSON.

Vector databases allow you to look up rows in a table based on semantic similarity.

So these two can match
"the app crashed" -> "it froze on iOS"

This involves embedding the text into a vector database using a language model.

This is the extent of what I knew about vector databases before trying this out - I had no idea if this would be possible, or would involve expensive API calls to "train" this database. So I just chatted with CC to see:

```
Is there a way I can take this JSON file and somehow embed it in a Vector database so that we can get insights about customer notes?
```

What Claude Code suggested
- Use open source ChromaDB and it's built in local embedding model.
- Chunk the json into sentences.
- Embed them by running the model locally, referencing the original note and its url.

It took about ten minutes.  And now I can ask things like:

```
How often do users complain about the app sync time?
```

And I get:

```
Based on the ProductBoard data, sync time/speed is a recurring but moderate-frequency complaint - not the most common issue,
  but it surfaces consistently, especially from enterprise clients with large datasets. Here's what I found:

  Sync time/speed complaints

  ~6-8 directly relevant notes across the ~50 results, spanning 2023-2024. The key ones:

  1. Esther Schipper (Jan 2024) - Described syncing as "incredibly pressured" and "stressful". Complained the new app's update status is "unclear and seems unreliable" with no visibility into download times remaining.
  2. Greene Naftali (Nov 2024) - "there's something with the update times that slows things down" - attributed to having a lot of artwork and images. Noted that constant system updates mean the app frequently needs re-syncing.
  3. Stephen Friedman (Jan 2024) - "Syncing is one of the major issues we've had. Inconsistency - appearing as done (downloaded and synced) but not actually being so."
  4. Palace Enterprise (Jun 2024) - "Would love much faster / instant updates" re: delays and syncing issues.
  5. Ben Brown (Jan 2024) - Referenced sync taking "three hours or two hours" as a pain point.
  6. Kamel Mennour (Jan 2024) - Listed syncing issues as a blocker serious enough they still use a competitor (Art Binder) despite having 8 Artlogic app users.

  Pattern

  The complaints cluster around enterprise clients with large inventories, and the pain is sharpest at art fairs where speed and reliability are critical. The issues are less about raw sync time and more about:
  - Lack of progress visibility (no ETA, unclear status)
  - Perceived unreliability (appears synced but isn't)
  - Large dataset performance (galleries with thousands of records)

  It's not the #1 most frequent complaint, but it's high-impact - it drove at least one client (Kamel Mennour) to keep using a
  competitor.
```


After this initial result, I can then say "Write up a report to my notes with details on the most relevant notes, **making sure to link to the original note in Product Board**" because of course you have to check if they exist.