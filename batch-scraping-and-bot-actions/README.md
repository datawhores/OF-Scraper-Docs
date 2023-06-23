---
description: Options for automation
---

# Batch Scraping and Bot Actions

## Basic Run

This will allow you to select args through the prompt menus

```
ofscraper
```

{% embed url="https://of-scraper.gitbook.io/of-scraper/batch-scraping-and-bot-actions/selecting-posts" %}

{% embed url="https://of-scraper.gitbook.io/of-scraper/batch-scraping-and-bot-actions/model-selection-sorting" %}

## Liking/Unliking content

```
 ofscraper --action like
```

```
 ofscraper --action unlike
```

## Performing multiple actions

These actions can be combined together

* posts
* likes or unlike (only 1 because liking and unliking all posts doesn't make sense)

The command here will download all wall posts for selected model, and also like all posts

```
 ofscraper --posts all --action like
```

## Bypass all prompts

You need to pick at least one scraping method and username to bypass all prompts

```
 ofscraper --posts all --username ALL
```

## Running command in the background

You need to pick at least one scraping method for daemon mode to work

```
 ofscraper --daemon 10 --posts all
```

The script will run at minimum every 10 minutes. If it takes longer then 10 minutes to finish. Then the next run will start as soon as the last run finishes

Daemon mode will ask you to pick a username if the --username argument is not passed This only needs to be done once, and your settings are remember each time the daemon loops

## Modifications to Filename

### Toggle letter count for textlength

By default textlength will correspond to the number of words max you want

pass in the --letter-count arg to change this to max number of letters

```
ofscraper --letter-count
```

### Skip truncation

Truncation use common operating system file length restrictions to determine the best place to cut off a long file name to use the original file names pass --original pass in the --letter-count arg to change this to max number of letters

```
ofscraper --original
```



### Output Options

{% embed url="https://of-scraper.gitbook.io/of-scraper/controlling-output" %}
