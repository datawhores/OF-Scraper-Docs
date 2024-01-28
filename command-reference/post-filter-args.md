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



{% hint style="info" %}
**Exclude post by appending a hypthen(-)**
{% endhint %}

### -o, --posts

```
Possible choices: highlights,all,archived,messages,
timeline,pinned,stories,purchased,profile,labels
```

```
Perform action on certain content 
Can be used for like, unlike, and download
```

```
Default:None
```

### -la, --like-area

{% hint style="info" %}
**This will overide --posts for --action like or unlike**
{% endhint %}

```
Possible choices: all,archived,timeline,pinned,stories,labels
```

```
Perform like/unlike action on certain content
```

```
Default:None
```

### -da, --download-area

{% hint style="info" %}
**This will overide --posts for --action download**
{% endhint %}

```
Possible choices: highlights,all,archived,messages,
timeline,pinned,stories,purchased,profile,labels
```

```
Perform download action on certain content
```

```
Default:None
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

### -to,--protected-only

```python
Restrict downloads to content that specifically requires decryption
```

### -no,--normal-only

```
Restrict downloads to content that specifically does not require decryption
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
