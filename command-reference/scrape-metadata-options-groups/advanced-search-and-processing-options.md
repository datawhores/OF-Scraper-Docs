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
* **Effect:** This can be faster for large user lists but might overload the target server or encounter rate limits.
* **Default:** `False` (users are processed one by one)

### -fi, --force-individual

* **Enforces:** Searching each username provided with the `--username` argument as a separate request.
* **Default:** This behavior is the default when no search flags are specified.
* **Use case:** You might use this option if the website handles bulk username searches differently.

### -fl, --force-list

* **Processes:** The entire user list based on the currently enabled configuration settings for `userlist` or the `--user-list` argument.
* **Effect:** Separates usernames within the list and searches for them individually.
* **Use case:** This is useful if your user list contains usernames separated by specific delimiters (e.g., newlines).

**Note:** Using `-fl` might lead to a large number of individual requests, potentially overloading the target server or encountering rate limits.

This revised version adheres to your request of having only a single level 1 header for the main title and promoting all sub-categories ("Username Search Behavior" and individual options) to level 2 headers using `##`.
