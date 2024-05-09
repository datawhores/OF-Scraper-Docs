---
description: >-
  These options allow you to define which users (models) the program should
  process for scraping actions. You can combine these methods for granular
  control.
---

# User Selection Options

## Specifying Usernames

### -u, --username \[argument]

* **Selects:** Specific usernames to process, separated by commas (e.g., `name1,name2`).
* **Case-sensitive:** Usernames are matched based on exact case.
* **ALL (case-sensitive):** Use `ALL` to include all available usernames in the program's data.

**Example:** With `-u user1,user2`, only users "user1" and "user2" will be processed.



### -eu, --excluded-username \[argument]

* **Excludes:** Specific usernames from processing, separated by commas (e.g., `name1,name2`).
* **Precedence:** Excluded usernames take priority over usernames specified with `-u`.

**Example:** With `-u user1,user2` and `-eu user2`, only "user1" will be processed (excluding "user2").



***

## Using User Lists

### -ul, --user-list \[argument] (optional)

* **Filters:** Users based on entries in a user list.
* **Default list:** "ofscraper.main" (if no argument provided).
* **Built-in lists:** The program also has built-in lists "ofscraper.active" and "ofscraper.disabled"\
  corresponding to active and expired account respectively
* **Argument behavior:**
  * If no argument is provided, the default list ("scrape") will be used.
  * If an argument is provided (e.g., "myuserList"), only the specified list will be processed.

**Example:** With `-ul myUserList`, only users in the "myUserList" list will be processed.

### -bl, --black-list \[argument] (optional)

* **Excludes:** Users based on entries in a user list.
* **Blacklist behavior:** Similar to user lists, but excludes all users from the specified list
* **Default list:** None
* **Argument behavior:**
  * If an argument is provided (e.g., "inactiveUsers"), only users from the specified blacklist will be excluded.

**Example:** With `-bl inactiveUsers`, users in the "inactiveUsers" blacklist will be excluded from processing
