---
description: >-
  This section outlines various options for specifying content targets, actions,
  and filters within the program.
---

# Content Options

## Targeting Content

### **-o, --posts** \[argument]

* Specify the type of content to target for actions (like, unlike, download).
* **Possible choices:** `highlights`, `all`, `archived`, `messages`, `timeline`, `pinned`, `stories`, `purchased`, `profile`, `labels`.
* **Defaults:** to `None`.

### **-la, --like-area** \[argument]

* Define the area for like/unlike actions (overrides `--posts`).
* **Possible choices:** `all`, `archived`, `timeline`, `pinned`, `stories`, `labels`.
* **Defaults**: to `None`.

### **-da, --download-area** \[argument]

* Specify the area for download actions (overrides `--posts`).
* **Possible choices:** `highlights`, `all`, `archived`, `messages`, `timeline`, `pinned`, `stories`, `purchased`, `profile`, `labels`.
* **Defaults** to `None`.

***

## Filtering Content

### **-sk, --skip-timed**

* Skips temporary posts (commonly used for promotions).

### **-ms, --mass-skip**

* Filters downloads to include only those labeled as mass messages.

### **-mm, --mass-msg**

* Excludes downloads marked as mass messages.

### **-ok, --only-timed**

* Downloads only temporary posts (mostly used for promotions).

### **-ft, --filter** \[argument]

* Filter posts using a provided regular expression pattern.
* Case-sensitive if uppercase characters are included.
* Posts matching the pattern are included.
* **Defaults:** to `".*"` (matches all posts).

### **-nf, --neg-filter** \[argument]

* Filter posts to exclude based on a regular expression pattern.
* Case-sensitive if uppercase characters are included.
* Posts matching the pattern are excluded.
* **Defaults:** to `None` (no exclusion)

### **-to, --protected-only**

* Restricts downloads to content requiring decryption.

### **-no, --normal-only**

* Restricts downloads to content that does not require decryption.

### **-lb, --label**

* Scrape content with specific labels.
* **Defaults:** to `None` (no specific label).

### **-pd, --post-id \[argument]**

* Filters content based on post ID
* **Arguments:** One or more comma-separated (",") post IDs. You can also provide URLs containing a valid post ID
* **Defaults:** None
* **Note:** In certain situation this will allow direct search of content, namely for timeline and message related posts and if the number is less then 10
* **Note:** you can also use manual if you want to process post for multiple users

### -tls, --timeline-strict

* Filters timeline to only include non-pinned and non-archived posts
* **Default: False**

***

## AD Filter

### **-ba, --block-ads**

* Filter posts with regex to block posts with common words for advertisements
*   **Regex :**

    ```python
    r"(#(?:ad|ads|AD|advertising|sponsored|promotion)|trial|discount|exclusive\s+offer|giveaway|limited\s+time|\Buser\s+promo|shoutout|endorsement)"

    ```
* **Defaults:** None

### **-nf, --neg-filter** \[argument]

* Filter posts to exclude based on a regular expression pattern.
* Case-sensitive if uppercase characters are included.
* Posts matching the pattern are excluded.
* **Defaults:** to `None` (no exclusion)



***

### Date Range



{% embed url="https://of-scraper.gitbook.io/of-scraper/using-the-scraper/batch-scraping-and-bot-actions/selecting-posts#valid-inputs" %}
Valid Date Inputs
{% endembed %}

### **-be, --before** \[argument]

* Process posts on or before a specified date (format: Month/Day/Year).

### **-af, --after** \[argument]

* Process posts on or after a specified date (format: Month/Day/Year).

***

## Other Options

### **-e, --force-all**

* Downloads all files regardless of database presence.
* **Defaults:** to `False`

### **-fl,--force-like**

* Like posts regardless of status in cache&#x20;
* **Defaults:** to `False`

### **-eq, --force-model-unique**

* Downloads files only if not present for the current model.
* **Defaults:** to `False`.

### **-sp, --scrape-paid**

* Scrapes the entire paid page for content (can be time-consuming).
* **Defaults:** to `False`.

### **-it, --item-sort** \[argument]

* Defines the order for processing media sort order before actions.
* Uses default action sorting if `None`.
* **Defaults are:**
  * Date for likes/unlikes (always)
  * Date for normal downloader
  * Shuffled for batch downlooader
* **Possible choices:**&#x20;
  * `random`: Randomize order&#x20;
  * `text-asc`: Sort by post text in ascending order&#x20;
  * `text-desc`: Sort by post text in descending order
  * `date-asc`: Sort by media date in ascending order
  * `date-desc`: Sort by media date in descending order

### **-xc ,--max-count** \[argument]

* Sets the maximum number of posts to like or download.
* **Defaults:** to `None` (no limit).
