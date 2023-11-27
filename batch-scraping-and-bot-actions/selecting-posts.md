# Selecting Posts

### By post type

A comma-separated list indicating the posts from which you wish to download content.

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

By default, content is stored in a database to prevent duplicate downloads. If you wish to download all available content for a specific model, include the '--dupe' argument.

```
ofscraper --dupe
```

### Filter Post by Date

#### Before

Filters  posts on or before the specified date. It functions for downloading, liking, and unliking posts.

```
ofscraper --before date
```

#### After

Filter  posts on or after the specified date. It functions for downloading, liking, and unliking posts.

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

You can enhance granularity by including a comma. When utilizing debuggers, the output will display in UTC, offering greater detail.

```
1 year ago, 1 month ago
```

### Filtering Timed Post

skip all timed post

```
ofscraper --skip-timed
```

### Filtering by text content

This feature can accept regex patterns, but you might need to enclose the string in quotes to escape the input properly. Additionally, using a capital letter will initiate a case-sensitive search.

```
ofscraper --filter 
```

#### Neg Filter Note:&#x20;

This will exclude any posts that match the provided regex pattern.

### Search entire paid page

This option is meant for handle situations where for example a model account has been deleted

```
ofscraper --scrape-paid
```

If you want to skip the other prompts and only scrape the paid page

```
ofscraper --scrape-paid --post None
```
