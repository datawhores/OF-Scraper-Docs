---
description: >-
  These options are used with specific subcommands of the program that perform
  content checks for different data types (posts, messages, purchased content,
  stories/highlights)
---

# Content Check Modes Options

{% hint style="info" %}
&#x20;**Cached information is generally stored for around 3 days to improve efficiency**
{% endhint %}



***

## Syntax

```
ofscraper [subcommand_name] [subcommand_options]
```

### example

```
ofscraper post_check --url test
```

## General Options

{% content-ref url="shared-options/common-option-groups/" %}
[common-option-groups](shared-options/common-option-groups/)
{% endcontent-ref %}

## Subcommand Options

Each content check subcommand (`post_check`, `msg_check`, `paid_check`, `story_check`) accepts common arguments for specifying content sources and controlling update behavior.

### Specifying Content Source

* **-u, --url \[argument]:** (all subcommands)
  * Scans content from one or more URLs provided as arguments (separate URLs with spaces).
* **-f, --file \[argument]:** (all subcommands)
  * Scans content from a file containing entries (URLs or usernames) separated by lines.

### Forcing Update

* **-fo, --force \[argument]:** (all subcommands)
  * **Default:** `False` (uses cached data if available).
  * Sets `True` to force the API to retrieve the latest information, bypassing the cache.

### Text

### **-tn, --text** \[argument]

* Specify to  download text with any media tied to that text

### **-tp, --text-only** \[argument]

* Specify to  download only text, skipping any media

## Subcommand Descriptions

**Here's a summary of each content check subcommand:**

* **post\_check:** Analyzes data associated with posts from specified URLs or a file. It generates a table displaying relevant information about the posts.
* **msg\_check:** Analyzes data associated with messages from specified URLs or a file. It generates a table displaying relevant information about the messages.
* **paid\_check:** Analyzes data associated with purchased content from specified usernames or a file. It generates a table displaying relevant information about the purchased content.
* **story\_check:** Analyzes data associated with stories and highlights from specified usernames or a file. It generates a table displaying relevant information about the stories/highlights.

