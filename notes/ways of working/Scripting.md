For things you want to do that need to be *deterministic* - like calculating totals from several spreadsheets or... anything to do with numbers where you can't easily check the accuracy without doing the work yourself, use scripts.

```
Write a script to take these files, and sum up the numbers on each line
```

Or if you find yourself transforming images to a specific format size all the time.  CC will usually just run command line tools with your input, but you can script it to avoid the overhead and get the same results guaranteed every time.

`Write a script to resize a given image to 1080 x 1920 in PNG format`

And then you could wrap that in a skill to run it on all the images in a given folder.  So you can drop some screenshots in `/process-for-app-store` , and just run a skill to convert them.

`Create a skill that uses this script, in parallel, on all images in `/process-for-app-store` whenever I say "resize for Instagram"`


### For calling APIs
If you find yourself asking Claude Code to call an API for data a lot, it might be good to set up a script.  E.g. I want to call the API for Product Board every day and get any tickets that have been added since the last time I called the API, and save them to a json file.
***Be wary of giving CC any API Keys though.***  Ask it how you can set up an environment variable instead so it can reference that instead of reading your key directly.

### Scripts for hiding info from context
You want to download a bunch of user data from a CRM platform and do some analysis.  

This data contains phone numbers and emails.  

If you ask Claude Code to hit the API/MCP and download that data, it will "see" the data being downloaded - it'll be part of it's context window, and you can't guarantee where that data might end up.  This is not ideal for privacy.

Ask it to write a script instead
```
I want to download the 3000 notes from ProductBoard via the API, but I don't want you to see that data or have it pass through your context.  Can you write a script that downloads the notes in batches and saves them to one .json file?
```

And then another to strip out the sensitive data

```
Write a script to process this JSON, removing any email addresses and phone numbers based on regex.
```

So now you have a set of data in JSON format with redacted emails/phone numbers, safer to run Claude against to analyze.