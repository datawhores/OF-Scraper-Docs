---
description: These page is based on the ofscraper -h output
---

# Command Reference

Overview

## Global Args

### v, --version

```
show program’s version number and exit
```

```
Default: “2.4.5+main.8f998cd”
```

### cg, --config

```
Change location of config folder/file
```

### r, --profile

```
Change location of profile directory

This is where the auth information is held
```

### Logging

Arguments for output controls

#### l, --log

```
Possible choices: OFF, STATS, LOW, NORMAL, DEBUG
```

```
set log file level
```

```
Default: OFF
```

#### dc, --discord

```
Possible choices: OFF, STATS, LOW, NORMAL, DEBUG
```

```
set discord log level
```

```
Default: OFF
```

#### p, --output

```
Possible choices: PROMPT, STATS, LOW, NORMAL, DEBUG
```

```
set console output log level
```

```
Default: NORMAL
```

## Main Program

```
ofscraper  [global args] [main program args]
```

### General Arguments for scraper

#### u, --username

```
select which username to process (name,name2) Set to ALL (case-sensitive) for all users
```

#### -eu, --excluded-username

```
select which usernames to exclude (name,name2) This has preference over –username
```

#### -d, --daemon

```
run script in the background Set value to minimum minutes between script runs 
Overdue runs will run as soon as previous run finishes
```

#### -g, --original

```
don’t truncate long paths
```

```
Default: False
```

#### -c, --letter-count

```
intrepret config ‘textlength’ as max length by letter
```

```
Default: False
```

#### -a, --action

```
Possible choices: like, unlike
```

```
perform like or unlike action on each post
```

### Post

What type of post to scrape

#### -e, --dupe

```
Bypass the dupe check and redownload all files
```

```
Default: False
```

#### -o, --posts

```
Possible choices: highlights,all,archived,messages,
timeline,pinned,stories,purchased,profile,skip,labels
```

```
Download content from a model
```

```
Default:None
```



#### -sk, --skip-timed

```
skip promotional or temporary post
```

#### -ft, --filter

```
Filter post by text with inputed regex 
Note if you include any uppercase characters the search will be case-sensitive
```

```
Default: “.*”
```

#### -dt, --download type

```
Possible choices: protected,normal
```

```python
Filter what type of download you want 
None==Both,
protected=Files that need mp4decrpyt
Normal= Files that don't need mp4decrpyt

```

```
Default: None
```

####

#### -sp, --scrape-paid

```
scrape the entire paid page for content. This can take a very long time
```

```
Default: False
```

#### -lb,--label

```
scrape specific labels
```

```
Default: None
```

### filters

Filters out usernames based on selected parameters

#### -at, --account-type

```
Possible choices: paid, free
```

```
Filter Free or paid accounts paid and free correspond to your original price 
and not the renewal price
```

#### -rw, --renewal

```
Possible choices: active, disabled
```

```
Filter by whether renewal is on or off for account
```

#### -ss, --sub-status

```
Possible choices: active, expired
```

```
Filter by whether or not your subscription has expired or not
```

#### -be, --before

```
Process post at or before the given date general synax is 
Month/Day/Year 
Works for like,unlike, and downloading posts
```

#### -af, --after

```
Process post at or after the given date 
Month/Day/Year 

Works for like,unlike, and downloading posts
```

{% embed url="https://of-scraper.gitbook.io/of-scraper/batch-scraping-and-bot-actions/selecting-posts#filter-post-by-date" fullWidth="false" %}

### sort

Options on how to sort list

#### -st, --sort

```
Possible choices: Name, Subscribed, Expiring, Price
```

```
What to sort the model list by
```

```
Default: Name
```

#### -ds, --desc

```
Sort the model list in descending order
```

```
Default: False
```

### Advanced

Advanced Args

#### -uf, --users-first

```
Scrape all users first rather then one at a time. This only effects downloading posts
```

```
Default: False
```

#### -nc, --no-cache

```
disable cache
```

```
Default: False
```

#### -k, --key-mode

```
key mode override
```

```
default: auto
```

#### -dr, --dynamic-rules&#x20;

```
Dynamic signing
```

```
default: deviint
```

#### -pc,--part-cleanup

```
Cleanup part files
This will remove the ability to resume
```

```
default: false
```

## post\_check

Display a generated table of data with information about models post(s)

Multiple URLs can be passed via command-line or file

Cache lasts for 24 hours

```
ofscraper post_check [global args] [post_check args]
```

### -u, --url

```
Scan posts via url
```

### -f, --file

```
Scan posts via file

With line separated URL(s)
```

### -fo, --force

```
force retrieval of new posts info from API
```

```
Default: False
```

## msg\_check

Display a generated table of data with information about models messages(s)

Multiple URLs can be passed via command line or file

Cache lasts for 24 hours

```
ofscraper msg_check [global args] [msg_check args]
```

### -u, --url

```
Scan messages via url
```

### -f, --file

```
Scan messages via file

With line separated URL(s)
```

### -fo, --force

```
force retrieval of new messages info from API
```

```
Default: False
```

## paid\_check

Display a generated table of data with information about content purchased from model

Multiple usernames can be passed via command line or file

Cache lasts for 24 hours

```
ofscraper paid_check [global args] [paid_check args]
```

### -u, --username

```
Scan purchases via username
```

### -f, --file

```
Scan purchases via file

With line separated username(s)
```

### -fo, --force

```
force retrieval of new posts info from API
```

```
Default: False
```

## story\_check

Display a generated table of data with information about highlights and stories

Multiple usernames can be passed via command-line or file

Cache lasts for 24 hours

```
ofscraper story_check  [global args] [story_check args]
```

### -u, --username

```
Scan stories/highlights via username
```

### -f, --file

```
Scan stories/highlights via file
With line separated username(s)
```

### -fo, --force

```
force retrieval of new posts info from API
```

```
Default: False
```

## Manual

Manually download content via url or postid

### -f, --file

```
File with line separated list of 

links/postid to download
```

\-u, --url

```
url(s) to download
```
