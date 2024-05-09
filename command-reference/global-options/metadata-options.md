---
description: Options for generating metadata based on API response
---

# Metadata Options



***

{% hint style="warning" %}
**without --force-all or --force-model-unique media will be filter to only those that are set as not downloaded in the database**
{% endhint %}

### \[-md, --metadata]  **METADATA\_MODE**

{% hint style="info" %}
**progress bar  shows  all downloads as skipped**
{% endhint %}

{% hint style="info" %}
**No change to download field for media entries in database**
{% endhint %}

The `--metadata` argument is used to specify how to handle metadata for a particular area. It requires two parts separated by a comma&#x20;

1. **MODE:** This defines the overall action for metadata handling.

**METADATA\_MODE:** This specifies the specific area for which the metadata will be managed.

**Available Modes:**

* **check** - Updates metadata fields for the specified area via an API. This option does not check for new filenames.
* **update** - This mode performs two actions:
  1. Updates download status and filenames based on the presence of actual files.
  2. Updates metadata fields for the specified area via an API.
* **complete** - Marks the download as complete and updates metadata fields via an API. It also uses a new filename if one is available.

### -mc, --metadata-complete

{% hint style="info" %}
**progress bar shows all download mediatypes**
{% endhint %}

{% hint style="info" %}
**Marks all media entries in database as downloaded by setting the "download" field to True**
{% endhint %}

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Additionally marks each media as downloaded
```

### -mu, --metadata-update

{% hint style="info" %}
**progress bar marks downloads without files as skipped**

**progress bar marks downloads with files as based on mediatype**
{% endhint %}

{% hint style="info" %}
**Media entries in the database will have their "download" field flagged as False upon verification that the corresponding files are missing**
{% endhint %}

```

This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Marks every download based on presence on file system
```

