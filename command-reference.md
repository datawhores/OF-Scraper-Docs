---
description: These page is based on the ofscraper -h output
---

# Command Reference

Overview

## Global Args

### -v, --version

```
Display the program's version number and then exit
```

```
Default: “2.4.5+main.8f998cd”
```

### -cg, --config

```
Modify the location of the configuration folder or file
```

### -r, --profile

```

Alter the location of the profile directory, 
which houses the authentication information
```

### Logging

Arguments for output controls

#### -l, --log

```
Possible choices: OFF, STATS, LOW, NORMAL, DEBUG
```

```
Establish the log file level
```

```
Default: OFF
```

### -dc, --discord

```
Possible choices: OFF, STATS, LOW, NORMAL, DEBUG
```

```
Adjust the Discord log level
```

```
Default: OFF
```

### -p, --output

```
Possible choices: PROMPT, STATS, LOW, NORMAL, DEBUG
```

```
Adjust the log level for console output
```

```
Default: NORMAL
```

## Main Program

```
ofscraper  [global args] [main program args]
```

### General Scraper Args

#### -u, --username

```
Choose the usernames to process, separated by commas (e.g., name, name2). 
Use ALL (case-sensitive) to include all users.
```

#### -eu, --excluded-username

```
Specify the usernames to exclude (e.g., name, name2). 
This takes precedence over the '--username' option.
```

#### -d, --daemon

```
Execute the script in the background. Set the value for the minimum duration between script runs. 
Overdue runs will commence immediately after the previous run finishes.
```

#### -g, --original

```
Do not truncate lengthy paths
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

<pre><code><strong>Execute a like or unlike action on each post
</strong></code></pre>

### Post Filters

What type of post to scrape

#### -e, --dupe

```
Override the duplicate check and re-download all files.
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
Download content from a specific model
```

```
Default:None
```



#### -eo, --excluded-posts

```
Possible choices: highlights,archived,messages,timeline,pinned,stories,purchased,profile,skip,labels
```

```
Exclude certain posts from download
has preference over --post
```

```

Omit specific posts from the download process
Has priority over the '--post' option.
```

#### -sk, --skip-timed

```
Skipped temporary post
commonly used for promotions
```

#### -ms, --mass-skip

```
Filter downloads to exclusively include downloads labeled as mass messages.
```

#### -mm, --mass-msg

<pre><code><strong>Exclude any downloads marked as mass messages
</strong></code></pre>

#### -ok, --only-timed

```
Download only temporary posts,, mostly used for promo
```

#### -ft, --filter

```
Filter posts using a provided regex pattern. 
Please note that including any uppercase characters will make the search case-sensitive. 
Posts will be included if they pass the filter test.
```

```
Default: “.*”
```

#### -nf, --neg-filter

```
Use a regex pattern to filter posts by text. 
Note that including uppercase characters will make the search case-sensitive. 
Posts passing the filter test will be excluded.
```

```
Default: None
```

####

#### -dt, --download type

```
Possible choices: protected,normal
```

```python
Specify the download type:

None: Both types
Protected: Files requiring mp4decrypt
Normal: Files not needing mp4decrypt

```

```
Default: None
```

####

#### -sp, --scrape-paid

<pre><code><strong>Scrape the entire paid page for content. 
</strong>This process can take a substantial amount of time.
</code></pre>

```
Default: False
```

#### -lb,--label

```
Scrape specific labelss
```

```
Default: None
```

#### -be, --before

```
Process posts on or before a specific date. 
The general syntax is Month/Day/Year. 
This functionality works for actions like liking, unliking, and downloading posts
```

#### -af, --after

```
Process posts on or after a specified date in the format Month/Day/Year. 
This functionality applies to actions like liking, unliking, and downloading posts.
```

{% embed url="https://of-scraper.gitbook.io/of-scraper/batch-scraping-and-bot-actions/selecting-posts#filter-post-by-date" fullWidth="false" %}

### -mt,--mediatype



```
Possible choices: Videos,Audio,Images
```

```

Override the mediatype filter specified in the configuration file
```

```
Default: None
```

### -sx,--size-max



```
Filter files larger than the specified size. 
This filter accepts human-readable strings like "10GB".

```

```
Default: None
```

### -sm,--size-min

```
Filter files smaller than the specified size. 
This filter accepts human-readable strings like "10GB".

```

```
```

```
Default: None
```

###

### account filters

Apply filters to usernames based on the chosen parameters.\


####

***

#### pricing filters

{% content-ref url="batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md" %}
[price-filtering-sort.md](batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md)
{% endcontent-ref %}

```
Filter accounts based on the pricing 
```

#### -cp, --current-price

```
Possible choices: paid, free
```

_--_ **rp, --renew-price**

```
Possible choices: paid, free
```

_--_ **pp, --promo-price**

```
Possible choices: paid, free
```

**-- gp, --regular-price**

```
Possible choices: paid, free
```

***

#### promo filters

**--promo**

```
Possible choices: yes,no
```

<pre><code><strong>Filter accounts based on the presence of claimable promotions
</strong></code></pre>

**--all-promo**

<pre><code><strong>Filter accounts based on the presence of any promotions
</strong></code></pre>



***

#### Other filters

#### -rw, --renewal

```
Possible choices: active, disabled
```

```
Filter accounts depending on their renewal status, either turned on or off.
```

#### -ss, --sub-status

```
Possible choices: active, expired
```

```
Filter based on the expiration status of your subscription.
```

#### -ul, --user-list

```
Filter by userlists:

The default list is named "ofscraper.main." 
Other built-in lists include "ofscraper.active" and "ofscraper.disabled."

If no argument is provided, the default list will be "scrape." 
If an argument is passed, the default list won't be automatically scraped.
```

```
Default: []
```

#### -bl, --black-list

```
Exclude all models listed in the provided userlists:

The default list is named "ofscraper.main." 
Other built-in lists include "ofscraper.active" and "ofscraper.disabled."
```

```
Default: []
```





#### -st, --sort

```
Controls the order of the model selection list and the scraping order
```

```
Possible choices: name, subscribed, expired,current-price,promo-price
regular-price,renew-pric

```

<pre><code><strong>Specify the sorting criteria for the model list
</strong></code></pre>

```
Default: Name
```

Note: If account is set to renew then expired is the same as renewal date

#### -ds, --desc

```
Arrange the model list in descending order
```

```
Default: False
```

###

### Advanced

Advanced Args

#### -uf, --users-first

```
Prioritize downloading posts by scraping all users at once instead of one at a time
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
Override the key mode in the configuration file
```

```
default: auto
```

#### -db, --download-bars&#x20;

```
Override the download-bars setting in the configuration file
```

```
default: None
```

#### -sd, --download-sems

```
Override the download-sems setting in the configuration file
```

```
default: None
```

#### -sd, --download-threads

```
Override the download-threads setting in the configuration file

Setting the value to zero will force the use of the main thread for downloading. 
The main thread is also utilized if downloads cannot fill the download-sems.
```

```
default: None
```

#### -pc,--part-cleanup

```

Override the tempfile clean setting in the configuration
file, eliminating the ability to resume downloads.
```

```
default: false
```

#### -dr,--dynamic-rules

```
Override the dynamic-rules setting in the configuration file; 
it's utilized for signing requests
```

```
default: false
```

### -md, --metadata

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database.
```

## post\_check

Display a generated table of data showcasing model posts. Accept multiple URLs through command-line input or a file.

&#x20;The cached information will be stored for 24 hours.

```
ofscraper post_check [global args] [post_check args]
```

### -u, --url

```
Scan posts via url
```

### -f, --file

```
Scan posts using a file containing URLs separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on posts
```

```
Default: False
```

## msg\_check

Display a generated table displaying data regarding model messages. Accept multiple URLs through command-line input or a file.&#x20;

Information retrieved will be cached for 24 hours

```
ofscraper msg_check [global args] [msg_check args]
```

### -u, --url

```
Scan messages via url
```

### -f, --file

```
Scan messages using a file containing URLs separated by lines
```

### -fo, --force

```
Force the API to retrieve updated information on messages
```

```
Default: False
```

## paid\_check

Display a generated table featuring information on purchased content from models.&#x20;

Allows multiple usernames to be entered via command-line input or a file. Retain cached data for 24 hours.

```
ofscraper paid_check [global args] [paid_check args]
```

### -u, --username

```
Scan purchases via username
```

### -f, --file

```
Scan paid content using a file containing usernames separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on paid content
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
Scan stories/highlist using a file containing usernames separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on stories/highlights
```

```
Default: False
```

## Manual

Retrieve content manually using either a URL or a post ID

### -f, --file

```
File containing a list of links or post IDs separated by lines
```

### -u, --url

```
url(s) to download
```
