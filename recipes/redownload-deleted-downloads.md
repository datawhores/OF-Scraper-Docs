# Redownload Deleted Downloads

## With metadata (recommended)

{% hint style="info" %}
**use the same (--posts or --download-area) and --usernames for both steps**
{% endhint %}

Recommended run&#x20;

1. use the 'metadata-update' argument

* This will update files on system based on config, if a file does not exist on system it will be marked as undownloaded in config
* Much faster then --dupe, since no files are writing to disk, and the number of requests required is greatly reduced

```
ofscraper --metadata-update
```

* add additional args if needed for example --after 2000

2. Download normally

## With dupe

```
ofscraper --dupe
```

* This will redownload all files from scan regardless of if the file exists on the system



