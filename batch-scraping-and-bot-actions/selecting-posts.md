# Selecting Posts



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
