# Price Filtering/Sort

## Current Price

1. If there is an active subscription and its subscription price is available, use that price.
2. If there is no active subscription or the subscription price is not available, check for active promotions with a "claimable" tag. Use the lowest subscription price among these promotions.
3. If no "claimable" promotions are available, use the regular subscription price.
4. If none of the above methods provide a valid price, set the current price to 0.

## _Renewal Price_

1. Primary Source is the lowest claimable promotional subscription price.
2. If no "claimable" promotions are available, use the regular subscription price.
3. If none of the above methods provide a valid price, set the renewal price to 0.

## Regular Price

1. Primary Source is the regular subscription price.
2. If that is not available then, set the regular price to 0

## Promo Price

1. Primary Source is the lowest promotional subscription price.
2. If no promotions are available, use the regular subscription price.
3. If none of the above methods provide a valid price, set the promo price to 0.

