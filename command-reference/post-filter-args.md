---
description: What type of post to scrape
---

# Post Filter Args

### -e, --dupe

```
Override the duplicate check and re-download all files.
```

```
Default: False
```

### -o, --posts

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



### -eo, --excluded-posts

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

### -sk, --skip-timed

```
Skipped temporary post
commonly used for promotions
```

#### -ms, --mass-skip

```
Filter downloads to exclusively include downloads labeled as mass messages.
```

### -mm, --mass-msg

<pre><code><strong>Exclude any downloads marked as mass messages
</strong></code></pre>

### -ok, --only-timed

```
Download only temporary posts,, mostly used for promo
```

### -ft, --filter

```
Filter posts using a provided regex pattern. 
Please note that including any uppercase characters will make the search case-sensitive. 
Posts will be included if they pass the filter test.
```

```
Default: “.*”
```

### -nf, --neg-filter

```
Use a regex pattern to filter posts by text. 
Note that including uppercase characters will make the search case-sensitive. 
Posts passing the filter test will be excluded.
```

```
Default: None
```

####

### -dt, --download type

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

### -sp, --scrape-paid

<pre><code><strong>Scrape the entire paid page for content. 
</strong>This process can take a substantial amount of time.
</code></pre>

```
Default: False
```

### -lb,--label

```
Scrape specific labelss
```

```
Default: None
```

### -be, --before

```
Process posts on or before a specific date. 
The general syntax is Month/Day/Year. 
This functionality works for actions like liking, unliking, and downloading posts
```

### -af, --after

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
Default: None
```
