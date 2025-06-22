# Migrating from Digitalcriminal's script



***

## Set Medatadata&#x20;

{% hint style="info" %}
**Your previous metadata files are compatible so only the path needs to match**
{% endhint %}

{% content-ref url="config-options/setting-metadata-path.md" %}
[setting-metadata-path.md](config-options/setting-metadata-path.md)
{% endcontent-ref %}



***

## Set save path

{% hint style="info" %}
**Most settings should be transferable**\
**Including the defaults**
{% endhint %}

{% content-ref url="config-options/file-output-options/" %}
[file-output-options](config-options/file-output-options/)
{% endcontent-ref %}

##

## Example

See the advanced DC config

{% content-ref url="config-options/example-configs.md" %}
[example-configs.md](config-options/example-configs.md)
{% endcontent-ref %}

### save\_location

```
 "save_location": "/Onlyfans",
```

### dir format

```
 "dir_format": "{model_username}/{responsetype}/{value}/{mediatype}/"
```

Means a full path like

<pre class="language-markup"><code class="lang-markup"> "/<a data-footnote-ref href="#user-content-fn-1">Onlyfans/</a><a data-footnote-ref href="#user-content-fn-2">modelA/Messages/Free/Images/</a>"
</code></pre>

1. /Onlyfans is the save\_location
2. /modelA/Messages/Free/Images/ is the dir\_format

### metadata

<pre><code>"metadata": "<a data-footnote-ref href="#user-content-fn-3">{save_location}</a>/{model_username}/Metadata"
</code></pre>

This refers to a directory path designated for storing 'user\_data.db'.

```
"OnlyFans/ModelA/Metadata"
```

[^1]: save\_location

[^2]: dir\_format



[^3]: Save location from config

