# Model Selection/Sorting

### Selecting from Commandline

comma separate list of which model you want to scrape

```
 ofscraper --username name1,name
```

#### Selecting all users

```
 ofscraper --username ALL
```

'ALL' is effected by filters it is also case sensitive

### Filtering username list

\


The following are can be change dynamically if using prompts

```
---account-type,--sub-status and renewal
```

{% embed url="https://of-scraper.gitbook.io/of-scraper/using-prompts" %}

Additionally this does not change the retrieval of usernames \
only the subset of returned usernames that are return\
\
To retrieve only specific usernames setup a collection on onlyfans, and use the --userlist or --blacklist args



#### Version >2.1

\--username now has preference over any filters The result is that only the --usernames selected will be used The only exception is ALL which can be filtered

#### Restrict by account type

This will restrict the program to only interact with free accounts

```
 ofscraper --account-type free --username ALL
```

#### Restrict by subscription status

This can be used to scrape for example messages from expired accounts

```
ofscraper --sub-status expired --posts messages --username ALLf
```

#### Restrict by renewal status

You can use this option to scrape only accounts that will expire

```
ofscraper  --renewal disabled --username ALL
```

#### Combining filters

A common way to use filters might be to only scrape accounts that are set to expire

```
ofscraper  --account-type paid --sub-status active --renewal expired --username ALL
```

Alternatively maybe only free accounts with active subscriptions

```
ofscraper  --account-type free --sub-status active --username ALL
```

### Exclude specific models

Note this takes preference over --username including --username ALL

```
ofscraper --excluded-username username
```

### Sorting username list

Default is by name in asc order

#### sort by account expiring date

```
ofscraper --sort expiring

```

#### sort by account subscribed date

```
ofscraper --sort subscribed

```

#### sort by account name

```
ofscraper --sort name

```

#### sort by account price

* Price is current subscription price
* if that can not be found lowest promo price return from API
* if that is not available normal membership price
* if that is not found zero

```
ofscraper --sort price

```

### desc option

Normal sort will be asc

This changes the sort to be desc

```
ofscraper --sort price --desc

```

Retriving specific list
