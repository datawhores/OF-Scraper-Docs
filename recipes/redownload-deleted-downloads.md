# Redownload Deleted Downloads

## With metadata

{% hint style="info" %}
**Recommended**
{% endhint %}

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

* add additional args if needed

2. Download normally

