---
description: Options for generating metadata based on API response
---

# Metadata Options



***

{% hint style="warning" %}
**without --force-all or --force-model-unique media will be filter to only those that are set as not downloaded in the database**
{% endhint %}

### -md, --metadata

{% hint style="info" %}
**progress bar  shows  all downloads as skipped**
{% endhint %}

{% hint style="info" %}
**No change to download field for media entries in database**
{% endhint %}

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Does not change download status
```

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

