# Price Filtering/Sort

{% hint style="info" %}
Fallbacks are to utilized to enable easy sorting of list
{% endhint %}

{% hint style="info" %}
Fallbacks can be eliminated with proper filtering
{% endhint %}

## Current Price

{% hint style="info" %}
Best used with    --active-subscription
{% endhint %}

1. If there is an active subscription and its subscription price is available, use that price.
2. If there is no active subscription or the subscription price is not available, check for active promotions with a "claimable" tag. Use the lowest subscription price among these promotions.
3. If no "claimable" promotions are available, use the regular subscription price.
4. If none of the above methods provide a valid price, then 0 is used as a fallback

## _Renewal Price_

{% hint style="info" %}
Best used with    --active-subscription
{% endhint %}

1. Primary Source is the lowest claimable promotional subscription price.
2. If no "claimable" promotions are available, use the regular subscription price.
3. If none of the above methods provide a valid price, then 0 is used as a fallback

## Regular Price

1. Primary Source is the regular subscription price.
2. If that is not available then, then 0 is used as a fallback

## Promo Price

1. Primary Source is the lowest promotional subscription price.
2. If no promotions are available, use the regular subscription price.
3. If none of the above methods provide a valid price, then 0 is used as a fallback

