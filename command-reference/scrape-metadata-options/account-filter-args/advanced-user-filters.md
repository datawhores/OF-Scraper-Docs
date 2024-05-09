---
description: >-
  These options allow for highly granular filtering of user accounts based on
  various criteria. You can combine these filters to create very specific
  selections
---

# Advanced User Filters

## Advanced Pricing Filters

These filters allow you to target accounts based on specific price ranges for different pricing models (promotional, regular, current, and renewal

### -ppm, --promo-price-max \[argument]

* **Filters:** Accounts where the lowest available promotional price matches or falls below the specified value

### -ppn, --promo-price-min \[argument]

* **Filters:** Accounts where the lowest available promotional price matches or falls above the specified value

### -gpm, --regular-price-max \[argument]

* **Filters:** Accounts where the regular price (if available) matches or falls below the specified value

### -gpn, --regular-price-min \[argument]

* **Filters:** Accounts where the regular price (if available) matches or falls above the specified value

#### -cpm, --current-price-max \[argument]

* **Filters:** Accounts where the current price matches or falls below the specified value

### -cpn, --current-price-min \[argument]

* **Filters:** Accounts where the current price matches or falls above the specified value

### -rpm, --renewal-price-max \[argument]

* **Filters:** Accounts where the renewal price (if applicable) matches or falls below the specified value

### -rpn, --renewal-price-min \[argument]

* **Filters:** Accounts where the renewal price (if applicable) matches or falls above the specified value



***

## Advanced Account Attributes

These filters allow you to target accounts based on specific dates related to their activity or subscription status

### -lsa, --last-seen-after \[argument]

* **Filters:** Accounts where the "last seen" date/time is at or after the provided date

### -lsb, --last-seen-before \[argument]

* **Filters:** Accounts where the "last seen" date/time is at or before the provided date

**Note:** The "last seen" date/time might not be available for all accounts

{% hint style="info" %}
**When a model is set to renew, the expired date refers to the renewal date**
{% endhint %}

### -ea, --expire-after \[argument]

* **Filters:** Accounts with an expiration or renewal date at or after the provided date

### -eb, --expire-before \[argument]

* **Filters:** Accounts with an expiration or renewal date at or before the provided date

{% hint style="info" %}
**The subscription date might not always be the most accurate indicator for expired accounts. Consider using the `-ea` or `-eb` filters instead.**
{% endhint %}

### -sa, --subscribed-after \[argument]

* **Filters:** Accounts with a subscription date at or after the provided date (format: YYYY-MM-DD)

### -sb, --subscribed-before \[argument]

* **Filters:** Accounts with a subscription date at or before the provided date (format: YYYY-MM-DD)
