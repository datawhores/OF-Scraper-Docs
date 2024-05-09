# Model Filtering/Sorting

***

## Filter/Sort List By Price



{% content-ref url="price-filtering-sort.md" %}
[price-filtering-sort.md](price-filtering-sort.md)
{% endcontent-ref %}



***

## Selecting Specific models from command-line

You can provide a comma-separated list indicating the models you wish to scrape

```
 ofscraper --username name1,name
```

#### Selecting all users

```
 ofscraper --username ALL
```

'ALL' is influenced by filters, and it  is case-sensitive.





***

## Filtering username list

The following settings can be dynamically modified if using prompts.

{% content-ref url="../../using-prompts/" %}
[using-prompts](../../using-prompts/)
{% endcontent-ref %}

Furthermore, this adjustment doesn't alter the retrieval of usernames; it solely impacts the subset of usernames that are displayed\


> \
> If you wish to retrieve specific usernames, set up a collection on OnlyFans, then utilize the '--userlist' or '--blacklist' arguments accordingly



### Version >2.1

Now, '--username' takes precedence over any filters. Consequently, only the selected '--usernames' will be utilized, with the exception of 'ALL', which can still be filtered.

### Restrict by account type

This will limit the program to exclusively interact with and display free accounts

```
 ofscraper --current-price free --username ALL
```

### Restrict by subscription status

This demonstrates scraping messages from subscriptions that have expired

```
ofscraper --sub-status expired --posts messages --username ALL --action download
```

### Restrict by renewal status

You can utilize this option to exclusively scrape active accounts, considering the renewal status of their subscriptions.

```
ofscraper  --renewal disabled --username ALL
```



***

### Combining filters

Filters are commonly employed to scrape accounts that are scheduled for expiration.

```
ofscraper  --current-price paid --sub-status active --renewal expired --username ALL
```

Alternatively, you might choose to scrape only free accounts with active subscriptions

```
ofscraper  --current-price free --sub-status active --username ALL
```

### Exclude specific models

Please note that this takes precedence over '--username', including  '--username ALL'

```
ofscraper --excluded-username username
```

### Filter by regular price

```
ofscraper  --regular-price paid 
```

{% content-ref url="price-filtering-sort.md" %}
[price-filtering-sort.md](price-filtering-sort.md)
{% endcontent-ref %}



***

### Advanced filtering

{% content-ref url="../../../command-reference/scrape-metadata-options/account-filter-args/" %}
[account-filter-args](../../../command-reference/scrape-metadata-options/account-filter-args/)
{% endcontent-ref %}



***

## Sorting username list

The default setting is to sort alphabetically by name in ascending order



> Sorting effects the order of scraping, and not just the order that they appear in the prompt menu

### sort by account expiring date

```
ofscraper --sort expiring

```

### sort by account subscribed date

```
ofscraper --sort subscribed

```

#### sort by account name

```
ofscraper --sort name

```

### sort by promotional prices

```
ofscraper --sort promo-price

```

{% content-ref url="price-filtering-sort.md" %}
[price-filtering-sort.md](price-filtering-sort.md)
{% endcontent-ref %}

### desc option

By default, the sorting is in ascending order.&#x20;

Utilizing this changes the sorting to descending order.

```
ofscraper --sort price --desc

```



***

## Retrieving specific list

This option enables switching from the primary list of OnlyFans accounts to a previously designated collection of accounts.

```
ofscraper --userlist "tiktok"
```

You have the ability to merge multiple lists

```
ofscraper --userlist "tiktok" --userlist "tiktok2"
```



***

## Blocking list of Names

Collections offer the functionality to block a list of names

```
ofscraper --blacklist "tiktok" 
```

> Please note that this takes precedence over the '--userlist' option and also 'ALL' parameter
