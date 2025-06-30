---
description: >-
  This options allow for custom scripts to run during certain parts of the
  scripts flow
---

# Script Options

{% content-ref url="../../../getting-started/config-options/script-options.md" %}
[script-options.md](../../../getting-started/config-options/script-options.md)
{% endcontent-ref %}

### -ds, --after-action-script \[argument]

**Executes:** A user-defined script after an action is completed on a model

**Runs:**

* rafter each model is downloaded in the main scraper
* after each model's metadata is processed in metadata mode
* &#x20;after each model is processed in manual mode
* for each unique model, after the current cart is downloaded in check mode

### -ps, --post-script \[argument]

**Executes:** A user-defined script once the script finishes an action&#x20;

**Runs:**

* once all models are downloaded or liked in scrape mode
* once all the post from manual mode are completed
* After the current cart downloads are processed in check mode, and after the download-script is processed for each user
* after all metadata for  all users is processed in metadata mode&#x20;

### -ns, --naming-script \[argument]

**Executes:** A script that dynamically generates the final filename&#x20;

**Runs:**

* when the temporary .part filename is generated for a download
* when the final filename is being generated for a download
* when the final filename is being generated for a text download
* after all metadata for  all users is processed in metadata mode&#x20;

### -sdl, --skip-download-script \[argument]

**Executes:**  A script that determines whether to skip or continue a download

**Runs:**

* Just before a download starts

### -adl, --after-download-script \[argument]

**Executes:**  A script that runs after a download has completed

**Runs:**

* Just before a download starts

