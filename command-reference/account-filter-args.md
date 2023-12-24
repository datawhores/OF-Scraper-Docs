# Account Filtering Args

## account filters

{% hint style="info" %}
If account is set to renew then expired is the same as renewal date
{% endhint %}

Apply filters to the accounts list\


***

### pricing filters

{% content-ref url="../batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md" %}
[price-filtering-sort.md](../batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md)
{% endcontent-ref %}

```
Filter accounts based on the pricing 
```

#### -cp, --current-price

```
Possible choices: paid, free
```

_--_ **rp, --renew-price**

```
Possible choices: paid, free
```

_--_ **pp, --promo-price**

```
Possible choices: paid, free
```

**-- gp, --regular-price**

```
Possible choices: paid, free
```

***

### Account Flags

**-lo, --last-seen-only**

```
Filter accounts to ones where last seen is visible
```

**-ls, --last-seen-skip**

```
Filter accounts to ones where last seen is hidden
```

**-po, --promo-only**

```
Filter accounts to ones with any 
claimable promo price
```

**-ps, --promo-skip**

```
Filter accounts to ones without
any claimable promo price
```

**-ao, --all-promo-only**

```
Filter accounts to ones with any 
claimable promo price
```

**-as, --all-promo-skip**

```
Filter accounts to ones without
any claimable promo price
```

### Subscription Type

**-fo, --free-trail-only**

```
Filter accounts to only those 
currently in a free trial (normally paid)
```

**-fs, --free-trail-skip**

```
Filter accounts to only those 
currently not in a free trial (normally paid)
```

**-ts, --active-subscriptions**

```
Filter accounts to those with non-expired status
```

**-es, --expired-subscription**

```
Filter accounts to those with expired status
```

**-ro, --renew-on**

```
Filter accounts to those with the renew flag on
```

**-rf, --r**xpired-subscription**enew-off**

```
Filter accounts to those with the renew flag on
```

### List Filters

#### -ul, --user-list

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

#### -bl, --black-list

```
Exclude all models listed in the provided userlists:

The default list is named "ofscraper.main." 
Other built-in lists include "ofscraper.active" and "ofscraper.disabled."
```

```
Default: []
```

### Advanced User Filters

#### -ppn, --promo-price-min

```
Filter accounts to those where the lowest promo price matches 
or falls above the provided value
```

#### -gpm, --promo-price-max

```
Filter accounts to those where the lowest promo price matches 
or falls below the provided value
```

#### -gpn, --regular-price-min

```
Filter accounts to those where the regular price matches 
or falls above the provided value
```

#### -gpm, --regular-price-max

```
Filter accounts to those where the regular price matches 
or falls below the provided value
```

#### -cpn, --current-price-min

```
Filter accounts to those where the current price matches 
or falls above the provided value
```

#### -cpm, --current-price-max

```
Filter accounts to those where the curren price matches 
or falls below the provided value
```

#### -rpn, --renewal-price-min

```
Filter accounts to those where the renewal price matches 
or falls above the provided value
```

#### -rpm, --renewal-price-max

```
Filter accounts to those where the renewal price matches 
or falls below the provided value
```

#### -lsa,--last-seen-after

```
Filter accounts by last seen being at 
or after the given date
```

#### -lsb,--last-seen-before

```
Filter accounts by last seen being at 
or before the given date
```

#### -ea,--expire-after

```
Filter accounts by expiration/renewal being at 
or after the given date
```

#### -eb ,--expire-before

```
Filter accounts by expiration/renewal being at 
or before the given date
```



#### -sa,--subcribed-after

```
Filter accounts by sub date being at 
or after the given date

Note: The most accurate data point for 
expired accounts is expired date
```

#### -sb ,--subscribed-before

```
Filter accounts by sub date being at 
or before the given date

Note: The most accurate data point for 
expired accounts is expired date
```
