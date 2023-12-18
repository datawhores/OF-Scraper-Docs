---
description: These page is based on the ofscraper -h output
---

# Command Reference

## Syntax

```
ofscraper  [global args][Logging] [main program args]
```

{% content-ref url="command-reference/global-args.md" %}
[global-args.md](command-reference/global-args.md)
{% endcontent-ref %}

{% content-ref url="command-reference/logging.md" %}
[logging.md](command-reference/logging.md)
{% endcontent-ref %}

## Main Program Args

{% content-ref url="command-reference/general-scraper-args.md" %}
[general-scraper-args.md](command-reference/general-scraper-args.md)
{% endcontent-ref %}

{% content-ref url="command-reference/post-filters.md" %}
[post-filters.md](command-reference/post-filters.md)
{% endcontent-ref %}

{% content-ref url="command-reference/account-filters.md" %}
[account-filters.md](command-reference/account-filters.md)
{% endcontent-ref %}

###

###

###

###

###

###



##

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
