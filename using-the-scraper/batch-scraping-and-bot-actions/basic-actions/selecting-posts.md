# Downloading Content

## Selecting Posts

### By post type

A comma-separated list indicating the posts from which you wish to download content.

```
 ofscraper --action download --posts highlights,timeline
```

multiple calls

```
 ofscraper --action download --posts highlights --posts timeline
```

Duplicates will be removed

### Options

* profile
* highlights
* timeline
* archived
* stories
* messages
* purchased
* pinned
* labels

#### Special Options

* all (adding this option means scraping highlights,timeline,archived,stories,pinned,purchased and messages)
* labels\* or labels+ (This means scraping all+labels)

#### remove post type

You can add remove a post type by prepending the type with a hyphen (-). This will remove any selection, including those from all







***

## Bypass dupe check

By default, content is stored in a database to prevent duplicate downloads. If you wish to download all available content for the current model, include the '--force-all' argument.

```
ofscraper --action download --force-all
```



***

## Filter Post by Date

{% hint style="info" %}
**x should be a valid date**
{% endhint %}

### Before

Filters  posts on or before the specified date. It functions for downloading, liking, and unliking posts.

```
ofscraper --action download --before X
```

### After

Filter  posts on or after the specified date. It functions for downloading, liking, and unliking posts.

```
ofscraper --action download --after X
```

### **Valid Inputs**

{% hint style="info" %}
**Read arrow documentation/repo for all valid inputs**
{% endhint %}

`YYYY-MM-DD, YYYY-M-DD, YYYY-M-D, YYYY/MM/DD, YYYY/M/DD, YYYY/M/D, YYYY.MM.DD, YYYY.M.DD, YYYY.M.D, YYYYMMDD, YYYY-DDDD, YYYYDDDD, YYYY-MM, YYYY/MM, YYYY.MM, YYYY`

### Dehumanize Strings

We can convert certain strings into dates The general rules seem to be (number) (timeframe) (ago)

**timeframes**

* week
* month
* year
* second

You can enhance granularity by including a comma. When utilizing debuggers, the output will display in UTC, offering greater detail.

```
1 year ago, 1 month ago
```



***

## Filtering Timed Post (Promotional)

skip all timed post

```
ofscraper --action download --skip-timed
```

### Filtering by text content

This feature can accept regex patterns, but you might need to enclose the string in quotes to escape the input properly. Additionally, using a capital letter will initiate a case-sensitive search.

#### Filter

This will include only post that match the provided regex patter

```

ofscraper --action download --filter X
```

#### Neg Filter:&#x20;

This will exclude any posts that match the provided regex pattern.

```
ofscraper --action download --negfilter X
```



***

## Search entire paid page

This option is designed to manage situations like when a model account has been deleted

```
ofscraper --action download --scrape-paid
```

To exclusively scrape the paid page and skip other prompts

```
ofscraper --scrape-paid
```
