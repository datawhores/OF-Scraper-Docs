---
description: >-
  These options allow you to refine the list of user accounts displayed and
  processed by the program. You can combine multiple filters to create specific
  selections.
---

# User List Filter Options

## Pricing Filters

{% hint style="info" %}
**Refer to the dedicated documentation for detailed information on price filtering and sorting**
{% endhint %}

{% content-ref url="../using-the-scraper/batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md" %}
[price-filtering-sort.md](../using-the-scraper/batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md)
{% endcontent-ref %}

These options allow you to filter accounts based on their current price, renewal price, promotional price (if available), and regular price (if available).

### -cp, --current-price \[argument]

* **Possible choices:**
  * `paid`: Filters for accounts with a paid current price.
  * `free`: Filters for accounts with a free current price.

### -rp, --renewal-price \[argument]

* **Possible choices:**
  * `paid`: Filters for accounts with a paid renewal price.
  * `free`: Filters for accounts with a free renewal price.

### -pp, --promo-price \[argument]

* **Possible choices:**
  * `paid`: Filters for accounts with a claimable promotional price.
  * `free`: Filters for accounts without a claimable promotional price.

### -gp, --regular-price \[argument]

* **Possible choices:**
  * `paid`: Filters for accounts with a regular price (if applicable).
  * `free`: Filters for accounts without a regular price (if applicable).

## Account Flags

These options filter accounts based on specific flags or properties.

### -lo, --last-seen-only

* **Filters:** Accounts where the "last seen" date/time is visible.

### -ls, --last-seen-skip

* **Filters:** Accounts where the "last seen" date/time is hidden.

### -po, --promo-only

* **Filters:** Accounts with any claimable promotional price.

### -ps, --promo-skip

* **Filters:** Accounts without any claimable promotional price.

### -ao, --all-promo-only

* **Filters:** Accounts with any claimable promotional price, regardless of current or renewal status.

### -as, --all-promo-skip

* **Filters:** Accounts without any claimable promotional price, regardless of current or renewal status.

## Subscription Type

These options filter accounts based on their subscription status.

### -fo, --free-trial-only

* **Filters:** Accounts currently in a free trial (normally paid accounts).

### -fs, --free-trial-skip

* **Filters:** Accounts that are not currently in a free trial (normally paid accounts).

### -ts, --active-subscriptions

* **Filters:** Accounts with active, non-expired subscriptions.

### -es, --expired-subscription

* **Filters:** Accounts with expired subscriptions.

### -ro, --renew-on

* **Filters:** Accounts with the "renew" flag enabled.

### -rf, --renew-off

* **Filters:** Accounts with the "renew" flag disabled.

This revised version incorporates clear descriptions, links to potentially existing detailed documentation for complex filters, and avoids unnecessary underscores in option names.
