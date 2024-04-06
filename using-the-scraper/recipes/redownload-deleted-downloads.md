# Redownload Deleted Downloads

## With metadata (recommended)

{% hint style="warning" %}
**make sure to use the same exact settings for both steps to make sure the same posts are being effected**
{% endhint %}

Recommended run&#x20;

1. **use the 'metadata-update' argument**

* This will update files on system based on config, if a file does not exist on system it will be marked as not downloaded in data
* Much faster then --dupe, since no files are writing to disk, and the number of requests required is greatly reduced

```
ofscraper --metadata-update
```

* add additional args if needed for example --after 2000

2. **Download normally**

* If any files are missing now they will be redownloaded

## Force all downloads

```
ofscraper --force-all
```

this will force all downloads to be processed



