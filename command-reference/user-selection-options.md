---
description: Specify users for scraping  with usernames, userlists, or blacklists
---

# User Selection Option

### -u, --username

```
Choose the usernames to process, separated by commas (e.g., name, name2). 
Use ALL (case-sensitive) to include all users.
```



### -eu, --excluded-username

```
Specify the usernames to exclude (e.g., name, name2). 
This takes precedence over the '--username' option.
```



### -ul, --user-list

```
Filter by userlists:

The default list is named "ofscraper.main." 
Other built-in lists include "ofscraper.active" and "ofscraper.disabled."

If no argument is provided, the default list will be "scrape." 
If an argument is passed, the default list won't be automatically scraped.
```

```
Default: []
```

### -bl, --black-list

```
Exclude all models listed in the provided userlists:

The default list is named "ofscraper.main." 
Other built-in lists include "ofscraper.active" and "ofscraper.disabled."
```

```
Default: []
```

