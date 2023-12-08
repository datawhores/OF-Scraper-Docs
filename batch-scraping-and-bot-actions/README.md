---
description: Options for automation
---

# Batch Scraping and Bot Actions

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

##

## Performing multiple actions

You can combine these actions together

* posts
* likes or unlike (only 1 because liking and unliking all posts doesn't make sense)

This command will download all wall posts for the selected model and simultaneously like all the posts

```
 ofscraper --posts all --action like
```

## Bypass all prompts

Selecting at least one scraping method and providing a username will bypass all prompt

```
 ofscraper --posts all --username ALL
```

## Running command in the background

For daemon mode to function, you must select at least one scraping method

```
 ofscraper --daemon 10 --posts all
```

The script will operate at least every 10 minutes. If a run extends beyond 10 minutes, the subsequent run begins immediately after the prior one concludes.

&#x20;In daemon mode, if the --username argument isn't provided, it will prompt you to pick a username. This step is a one-time requirement as your settings are retained for each loop in the daemon.

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



### Output Options

{% content-ref url="../controlling-output.md" %}
[controlling-output.md](../controlling-output.md)
{% endcontent-ref %}
