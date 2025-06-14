# Creating Metadata

Metadata is automatically created when you download data. The tables and their structure are determined by the API you're using and the version of the script you're running

## metadata  mode

{% hint style="info" %}
**you can use the --anon option to gather metadata without logging in, however this means you lose access to most media data**
{% endhint %}

metadata mode can be entered with the metadata subcommand

```
ofscraper metadata [args]
```

This will update metadata without having to download files

{% content-ref url="../command-reference/shared-options/scrape-metadata-options/" %}
[scrape-metadata-options](../command-reference/shared-options/scrape-metadata-options/)
{% endcontent-ref %}

{% content-ref url="../command-reference/metadata-check-mode-options.md" %}
[metadata-check-mode-options.md](../command-reference/metadata-check-mode-options.md)
{% endcontent-ref %}
