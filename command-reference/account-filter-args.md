---
description: Apply filters to the accounts list
---

# User List Filter Options

***

## pricing filters

{% content-ref url="../batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md" %}
[price-filtering-sort.md](../batch-scraping-and-bot-actions/model-selection-sorting/price-filtering-sort.md)
{% endcontent-ref %}

```
Filter accounts based on the pricing 
```

### -cp, --current-price

```
Possible choices: paid, free
```

### _--_ **rp, --**renewal-price

```
Possible choices: paid, free
```

### _--_ **pp, --promo-price**

```
Possible choices: paid, free
```

### **-- gp, --regular-price**

```
Possible choices: paid, free
```

***

## Account Flags

### **-lo, --last-seen-only**

```
Filter accounts to ones where last seen is visible
```

### **-ls, --last-seen-skip**

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

### **-ao, --all-promo-only**

```
Filter accounts to ones with any 
claimable promo price
```

### **-as, --all-promo-skip**

```
Filter accounts to ones without
any claimable promo price
```



***

## Subscription Type

### **-fo, --free-trail-only**

```
Filter accounts to only those 
currently in a free trial (normally paid)
```

### **-fs, --free-trail-skip**

```
Filter accounts to only those 
currently not in a free trial (normally paid)
```

### **-ts, --active-subscriptions**

```
Filter accounts to those with non-expired status
```

### **-es, --expired-subscription**

```
Filter accounts to those with expired status
```

### **-ro, --renew-on**

```
Filter accounts to those with the renew flag on
```

### **-rf, --renew-off**

```
Filter accounts to those with the renew flag off
```
