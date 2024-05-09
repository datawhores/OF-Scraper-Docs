# Metadata Check Mode Options

{% hint style="info" %}
**Metadata Mode inherits mosts options from the main/scraper mode, with a few options removed because they don't make sense outside of downloading**
{% endhint %}

***

{% hint style="info" %}
**without --force-all or --force-model-unique media will be filter to only those that are set as not downloaded in the database**
{% endhint %}

### -md, --metadata \[argument]

The `--metadata` argument is used to specify how metadata mode updates the db

**Available Modes:**

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available

### -ms, --mark-stray-locked  \[argument]

Marks unmatched media items as locked.

**Details:**

* This flag is designed to identify and manage media items retrieved using the `--after` and `--before` options (date range filtering) that cannot be retrieved again through the API (potentially due to deletion).
* Media items with labels are excluded from being marked as locked.
* Locking is applied on a per-API type basis,  Timeline, Archived Posts, and Messages
* This has no effect if --scrape-paid is the only argument

**Use Case:**

Use this option to manage media items that aren't retrievable via the APIs. Marking them as locked prevents main scraper from using these items to set the minimum date



***

### -sp, --scrape-paid  \[argument]&#x20;

The `--scrape-paid` argument is used to specify how metadata mode updates the db, for scrape paid content

The options are the same as --metadata

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available



**Available Modes:**

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available



