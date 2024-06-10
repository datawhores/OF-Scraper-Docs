# Liking/Unliking Post

***

## Liking/Unliking content

```
 ofscraper --action like
```

```
 ofscraper --action unlike
```



***

## Selecting Posts

### By post type

A comma-separated list indicating the posts from which you wish to download content.

```
 ofscraper --action like --posts pinned,timeline
```

multiple calls

```
 ofscraper --action like --posts pinned --posts timeline
```

### Multiple actions

{% hint style="info" %}
**--post is a short hand for selecting both --like-area and --download-area**&#x20;
{% endhint %}

{% hint style="info" %}
**--like-area and --download area have preference over --post**
{% endhint %}

```
ofscraper --action like,download --like-area pinned --download-area timeline
```

### Options

* timeline
* archived
* pinned
* labels

#### Special Options

* all (adding this option means scraping timeline,archived,,pinned)
* labels\* or labels+ (This means scraping all+labels)

#### remove post type

You can add remove a post type by prepending the type with a hyphen (-). This will override any other selection, including those from 'all'

## Limits

### Onlyfans rate limit

estimated to be around 1000 per day

### Limit in program

* Each like/unlike requests will have a delay&#x20;
* Which will prevent the program from just spamming likes to the onlyfans server, and prevent log outs
* The limit is about a second, but is randomized





