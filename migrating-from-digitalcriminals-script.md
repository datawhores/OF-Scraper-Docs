# Migrating from Digitalcriminal's script

{% embed url="https://of-scraper.gitbook.io/of-scraper/config-options/setting-metadata-path" %}

## Example

This is based on common settings from DC script

#### save\_location

```
 "save_location": "/Onlyfans",
```

#### dir format

```
 "dir_format": "{model_username}/{responsetype}/{value}/{mediatype}/"
```

Means a full path like

<pre class="language-markup"><code class="lang-markup"> "/<a data-footnote-ref href="#user-content-fn-1">Onlyfans/</a><a data-footnote-ref href="#user-content-fn-2">modelA</a>/Messages/Free/Images/"
</code></pre>

1. /Onlyfans is the save\_location
2. /modelA/Messages/Free/Images/ is the dir\_fomrat

#### metadata

```
"metadata": "{save_location}/{model_username}/Metadata"
```

means a path for user\_data.db like

```
"OnlyFans/ModelA/Metadta"
```

```
{
    "config": {
        "main_profile": "main_profile",
        "save_location": "/Onlyfans",
        "file_size_limit": 0,
        "dir_format": "{model_username}/{responsetype}/{value}/{mediatype}/",
        "file_format": "{filename}.{ext}",
        "textlength": 0,
        "date": "MM-DD-YYYY",
        "metadata": "{save_location}/Metadata",
        "filter": [
            "Images",
            "Audios",
            "Videos"
        ],
        "mp4decrypt": "/root/ofscraper/bin/mp4decrypt",
        "discord": "",
        "responsetype": {
            "timeline": "Posts",
            "message": "Messages",
            "archived": "Archived",
            "paid": "Paid",
            "stories": "Stories",
            "highlights": "Highlights",
            "profile": "Profile",
            "pinned": "Posts"
        }
    }
}

```

[^1]: save\_location

[^2]: 
