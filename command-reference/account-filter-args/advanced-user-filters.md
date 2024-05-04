---
description: >-
  Precise user filtering with price ranges (current/renewal/regular/promo), last
  seen dates, expiration dates, and subscription dates.
---

# Advanced User Filters

### -ppm, --promo-price-max

```
Filter accounts to those where the lowest promo price matches 
or falls below the provided value
```

### -ppn, --promo-price-min

```
Filter accounts to those where the lowest promo price matches 
or falls above the provided value
```

### -gpm, --regular-price-max

```
Filter accounts to those where the regular price matches 
or falls below the provided value
```

### -gpn, --regular-price-min

```
Filter accounts to those where the regular price matches 
or falls above the provided value
```

### -gpm, --regular-price-max

```
Filter accounts to those where the regular price matches 
or falls below the provided value
```

### -cpn, --current-price-min

```
Filter accounts to those where the current price matches 
or falls above the provided value
```

### -cpm, --current-price-max

```
Filter accounts to those where the curren price matches 
or falls below the provided value
```

### -rpn, --renewal-price-min

```
Filter accounts to those where the renewal price matches 
or falls above the provided value
```

### -rpm, --renewal-price-max

```
Filter accounts to those where the renewal price matches 
or falls below the provided value
```

### -lsa,--last-seen-after

```
Filter accounts by last seen being at 
or after the given date
```

### -lsb,--last-seen-before

```
Filter accounts by last seen being at 
or before the given date
```



### -ea,--expire-after

{% hint style="info" %}
**If account is set to renew then expired is the same as renewal date**
{% endhint %}

```
Filter accounts by expiration/renewal being at 
or after the given date
```

### -eb ,--expire-before

{% hint style="info" %}
**If account is set to renew then expired is the same as renewal date**
{% endhint %}

```
Filter accounts by expiration/renewal being at 
or before the given date
```

### -sa,--subcribed-after

```
Filter accounts by sub date being at 
or after the given date

Note: The most accurate data point for 
expired accounts is expired date
```

### -sb ,--subscribed-before

```
Filter accounts by sub date being at 
or before the given date

Note: The most accurate data point for 
expired accounts is expired date
```

