---
description: >-
  These options allow you to control how usernames are searched for and the
  order in which users are processed during program actions
---

# Advanced Search & Processing Options

## Username Search Behavior

These options control how usernames are searched for during program actions.

### -uf, --users-first

* **Prioritizes:** Downloading posts by scraping all users at once instead of one at a time.
* **Effect:** This allows for gathering all required data before downloading or processing metadata
* **Default:** `False` (users are processed one by one)

### -fi, --force-individual

* **Enforces:** Searching each username provided with the `--username` argument as a separate request.
* **Default:** This behavior depends on the number of --usernames and the number of subscriptions on account
* **Use case:** This may be faster then retriving usernames in bulk

### -fl, --force-list

* **Processes:** The entire user list based on the currently enabled configuration settings for `userlist` or the `--user-list` argument.
* **Effect:** Separates usernames within the list
* **Default:** This behavior depends on the number of --usernames and the number of subscriptions on account
* **Use case:** This is useful if your retriving a large number of users

**Note:** Using `-fi` might lead to a large number of individual requests, potentially overloading the target server or encountering rate limits.
