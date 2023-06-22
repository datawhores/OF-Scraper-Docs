---
description: Options for automation
---

# Batch Scraping and Bot Actions

## Basic Run

This will allow you to select args through the prompt menus

```
ofscraper
```

## Model Selection

### Selecting from Commandline

comma separate list of which model you want to scrape

```
 ofscraper --username name1,name
```

#### Selecting all users

```
 ofscraper --username ALL
```

'ALL' is effected by filters it is also case sensitive

### Filtering username list

#### Version >2.1

\--username now has preference over any filters The result is that only the --usernames selected will be used The only exception is ALL which can be filtered

#### Restrict by account type

This will restrict the program to only interact with free accounts

```
 ofscraper --account-type free --username ALL
```

#### Restrict by subscription status

This can be used to scrape for example messages from expired accounts

```
ofscraper --sub-status expired --posts messages --username ALLf
```

#### Restrict by renewal status

You can use this option to scrape only accounts that will expire

```
ofscraper  --renewal disabled --username ALL
```

#### Combining filters

A common way to use filters might be to only scrape accounts that are set to expire

```
ofscraper  --account-type paid --sub-status active --renewal expired --username ALL
```

Alternatively maybe only free accounts with active subscriptions

```
ofscraper  --account-type free --sub-status active --username ALL
```

### Exclude specific models

Note this takes preference over --username including --username ALL

```
ofscraper --excluded-username username
```

### Sorting username list

Default is by name in asc order

#### sort by account expiring date

```
ofscraper --sort expiring

```

#### sort by account subscribed date

```
ofscraper --sort subscribed

```

#### sort by account name

```
ofscraper --sort name

```

#### sort by account price

* Price is current subscription price
* if that can not be found lowest promo price return from API
* if that is not available normal membership price
* if that is not found zero

```
ofscraper --sort price

```

### desc option

Normal sort will be asc

This changes the sort to be desc

```
ofscraper --sort price --desc

```

## Selecting Posts

### By post type

comma separate list of what you which posts you want to download content from

```
 ofscraper --posts highlights,timeline
```

multiple calls

```
 ofscraper --posts highlights --posts timeline
```

Duplicates will be removed

### Options

* profile
* hightlights
* timeline
* archived
* stories
* messages
* purchased
* pinned
* all (adding this option means scraping highlights,timeline,archived,stories,pinned,purchased and messages)

### Bypass dupe check

By default content will be saved to a database to prevent duplicate downloads If you need to download all of the content available for a specific model pass the --dupe arg

```
ofscraper --dupe
```

### Filter Post by Date

#### Before

Filters at or before the given date also Works for downloading, liking posts, and unliking posts

```
ofscraper --before date
```

#### After

Filters at or after the given date Works for downloading, liking posts, and unliking posts

```
ofscraper --after date
```

**Valid Inputs**

`YYYY-MM-DD, YYYY-M-DD, YYYY-M-D, YYYY/MM/DD, YYYY/M/DD, YYYY/M/D, YYYY.MM.DD, YYYY.M.DD, YYYY.M.D, YYYYMMDD, YYYY-DDDD, YYYYDDDD, YYYY-MM, YYYY/MM, YYYY.MM, YYYY`

#### Dehumanize Strings

We can convert certain strings into dates The general rules seem to be (number) (timeframe) (ago)

**timeframes**

* week
* month
* year
* second

You can also get more granularity by passing a comma If you use one of the debuggers you can see the output in UTC

```
1 year ago, 1 month ago
```

### Filtering Timed Post

skip all timed post

```
ofscraper --skip-timed
```

### Filtering by text content

Note this can accept regex, but most likely you will have to quote the string as a way to escape the input Capital Letter will trigger a case sensitive search

```
ofscraper --filter 
```

### Search entire paid page

This option is meant for handle situations where for example a model account has been deleted

```
ofscraper --scrape-paid
```

If you want to skip the other prompts and only scrape the paid page

```
ofscraper --scrape-paid --post None
```

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

## output options

see: https://github.com/datawhores/ofscraper/wiki/Controlling-Output-Level
