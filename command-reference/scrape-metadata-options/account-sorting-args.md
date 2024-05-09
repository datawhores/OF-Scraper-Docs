---
description: >-
  These options allow you to control how models are displayed in the list and
  the order in which they are processed during program actions (e.g., liking
  posts, downloading content)
---

# Model Sorting & Processing Options

{% hint style="info" %}
&#x20;**When a model is set to renew, the "expired" option refers to the renewal date**
{% endhint %}



## Sorting Criteria

#### -st, --sort \[argument]

* **Controls:** The order of the model list and processing order.
* **Possible choices:**
  * `name`: Sorts by model name (default).
  * `subscribed`: Sorts by whether the model is currently subscribed&#x20;
  * `expired`: Sorts by the renewal date
  * `current-price`: Sorts by the current price of the model.
  * `promo-price`: Sorts by the promotional price of the model (if available).
  * `regular-price`: Sorts by the regular price of the model (if available).
  * `renew-price`: Sorts by the renewal price of the model (if applicable).
  * `last-seen`: Sorts by the last time the model was seen&#x20;
* **Example:** With `-st expired`, models with expiring subscriptions will be processed first.

### -ds, --desc

* **Arranges:** The model list in descending order.
* **Default:** `False` (ascending order)
* **Use case:** You might use this option to prioritize models at the bottom of the list (e.g., with `-st last-seen -ds`).
