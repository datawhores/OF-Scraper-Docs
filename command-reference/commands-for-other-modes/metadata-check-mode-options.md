# Metadata Check Mode Options

{% hint style="info" %}
**Metadata Mode inherets mosts options from the main mode, with a few options removed because they don't make sense outside of downloading**
{% endhint %}

***

{% hint style="info" %}
**without --force-all or --force-model-unique media will be filter to only those that are set as not downloaded in the database**
{% endhint %}

### \[-md, --metadata] **METADATA\_MODE**&#x20;

The `--metadata` argument is used to specify how metadata mode updates the db

**Available Modes:**

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available



***

### \[-sp, --scrape-paid]  **METADATA\_MODE**&#x20;

The `--scrape-paid` argument is used to specify how metadata mode updates the db, for scrape paid content



**Available Modes:**

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available



