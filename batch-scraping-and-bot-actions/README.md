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

## Advanced Args

### au, --auth

This can be combined with --config

This option has preference over the auth path --config would have provided

```
Change location of auth file
```

### --users-first

Changes the order of downloading to retrieve links for all selected users first This means waiting longer for downloads to start, but this can be useful in certain situations

```
ofscraper --user-first
```

### multiple configs

```
ofscraper --config folder or file
```

This arg will try to parse whether the argument is a folder or file

There are two parts

config file: File that holds the config information config folder: Folder where config file recedes also has additional information like the file cache

1. Path is a current file

* config file path will be argument passed
* config folder will be the parent of the config file

2. Path does not exist, but the parent path exists as a directory

* config file will be generated using defaults
* config folder will be the parent path of the config folder

3. Path does not exist and parent path does not exists The parent path must not be a file else the program will crash

* config file will be generated using defaults
* config folder will be the path given, and will be created on run

#### Shared information

Two configs within the same folder can share

* Profiles
* log files
* cache
* authorization

### no cache

skips cache when retrieving post

```
ofscraper --no-cache
```

### Output Options

{% embed url="https://of-scraper.gitbook.io/of-scraper/controlling-output" %}
