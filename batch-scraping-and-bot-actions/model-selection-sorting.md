# Model Selection/Sorting

### Selecting from Commandline

You can provide a comma-separated list indicating the models you wish to scrape

```
 ofscraper --username name1,name
```

#### Selecting all users

```
 ofscraper --username ALL
```

'ALL' is influenced by filters, and it  is case-sensitive.

### Filtering username list

The following settings can be dynamically modified if using prompts.

```
---account-type,--sub-status and renewal
```

{% embed url="https://of-scraper.gitbook.io/of-scraper/using-prompts" %}

Furthermore, this adjustment doesn't alter the retrieval of usernames; it solely impacts the subset of usernames that are displayed\
\
If you wish to retrieve specific usernames, set up a collection on OnlyFans, then utilize the '--userlist' or '--blacklist' arguments accordingly



#### Version >2.1

Now, '--username' takes precedence over any filters. Consequently, only the selected '--usernames' will be utilized, with the exception of 'ALL', which can still be filtered.

#### Restrict by account type

This will limit the program to exclusively interact with and display free accounts

```
 ofscraper --account-type free --username ALL
```

#### Restrict by subscription status

This demonstrates scraping messages from subscriptions that have expired

```
ofscraper --sub-status expired --posts messages --username ALLf
```

#### Restrict by renewal status

You can utilize this option to exclusively scrape active accounts, considering the renewal status of their subscriptions.

```
ofscraper  --renewal disabled --username ALL
```

#### Combining filters

Filters are commonly employed to scrape accounts that are scheduled for expiration.

```
ofscraper  --account-type paid --sub-status active --renewal expired --username ALL
```

Alternatively, you might choose to scrape only free accounts with active subscriptions

```
ofscraper  --account-type free --sub-status active --username ALL
```

### Exclude specific models

Please note that this takes precedence over '--username', including '--username ALL'.

```
ofscraper --excluded-username username
```

### Sorting username list

The default setting is to sort alphabetically by name in ascending order

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

* The main data source for the 'price' field is the current subscription cost.
* If the current subscription price isn't available, the 'lowest promo price' retrieved from the API is returned instead.
* If the lowest promotional price isn't available, the regular membership price is retrieved instead
*   If none of the above is available, the value returned will be zero.



```
ofscraper --sort price

```

### desc option

By default, the sorting is in ascending order.&#x20;

Utilizing this changes the sorting to descending order.

```
ofscraper --sort price --desc

```

### Retrieving specific list

This option enables switching from the primary list of OnlyFans accounts to a previously designated collection of accounts.

```
ofscraper --userlist "tiktok"
```

You have the ability to merge multiple lists

```
ofscraper --userlist "tiktok" --userlist "tiktok2"
```

### Blocking list of Names

Collections offer the functionality to block a list of names

```
ofscraper --blacklist "tiktok" 
```

Please note that this takes precedence over the '--userlist' option and also 'ALL' parameter
