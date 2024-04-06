---
description: Automate liking & downloading OnlyFans posts
---

# Basic Automations

***

## Basic Run

This enables you to choose arguments using the prompt menus.

```
ofscraper
```

{% content-ref url="selecting-posts.md" %}
[selecting-posts.md](selecting-posts.md)
{% endcontent-ref %}

{% content-ref url="model-selection-sorting/" %}
[model-selection-sorting](model-selection-sorting/)
{% endcontent-ref %}

{% content-ref url="liking-unliking-post.md" %}
[liking-unliking-post.md](liking-unliking-post.md)
{% endcontent-ref %}



***

## Performing action(s)

{% hint style="info" %}
**--post is a short hand used for all actions unless an --like-area or --download-area command is passed**
{% endhint %}

You can combine these actions together

* likes or unlike (only 1 because liking and unliking all posts doesn't make sense)
* combine the previous with download

This command will download all wall posts for the selected model and simultaneously like all the posts

```
 ofscraper --posts all --action like,download
```

This command will only download

```
ofscraper --posts all --action download
```

### Selecting different areas

You can use&#x20;

* like-area specifically for like/unlike action
* download-area specifically for the download action

This command will download all post, but only like pinned

```
 ofscraper --download-area all --like-area pinned --action like,download
```

or&#x20;

```
 ofscraper --posts all --like-area pinned --action like,download
```



***

## Bypass all prompts

{% hint style="info" %}
**You must pick timeline,pinned, or archived to bypass the like area prompt when doing action**&#x20;

**like or unlike**
{% endhint %}

To bypass prompts

* Select at least one scraping method
* Provide a username(s)
* Providing the areas to scan

```
 ofscraper --posts all --username ALL --action like,download
```





***

## Running command in the background

For daemon mode to function, you must select at least one scraping method

{% hint style="info" %}
&#x20;**In daemon mode, if the --username argument isn't provided, it will prompt you to pick a username only once**
{% endhint %}

{% hint style="info" %}
**In daemon mode, if the --post or --scrape-paid argument isn't provided, it will prompt you to  them only once**
{% endhint %}

```
 ofscraper --daemon 10 --posts all --action like,download
```

The script will operate at least every 10 minutes. If a run extends beyond 10 minutes, the subsequent run begins immediately after the prior one concludes.





***

## Modifications to Filename

### Toggle letter count for textlength

By default, 'textlength' corresponds to the maximum number of words you desire. To modify this to represent the maximum number of letters, use the '--letter-count' argument.

```
ofscraper --letter-count
```

### Skip truncation

To utilize the original file names, include the '--original' flag.

```
ofscraper --original
```



***

### Output Options

{% content-ref url="../controlling-output.md" %}
[controlling-output.md](../controlling-output.md)
{% endcontent-ref %}
