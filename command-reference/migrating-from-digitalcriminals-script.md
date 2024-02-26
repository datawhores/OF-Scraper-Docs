# Migrating from Digitalcriminal's script

***

## Set Medatadata&#x20;

{% hint style="info" %}
**Your previous files are compatible so only the path needs to match**
{% endhint %}

{% content-ref url="../config-options/setting-metadata-path.md" %}
[setting-metadata-path.md](../config-options/setting-metadata-path.md)
{% endcontent-ref %}



***

## Set save path

{% hint style="info" %}
**Most settings should be transferable**\
**Including the defaults**
{% endhint %}

{% content-ref url="../config-options/file-output-options/" %}
[file-output-options](../config-options/file-output-options/)
{% endcontent-ref %}

##

## Example

This is based on common settings from DC script

<details>

<summary>Example Digitalcriminals Config</summary>



```json
{
    "config": {
        "main_profile": "main_profile",
        "metadata": "{save_location}/{model_username}/Metadata",
        "discord": "",
        "file_options": {
            "save_location": "//home/james/Data/ofscraper",
            "dir_format": "{model_username}/{responsetype}/{value}/{mediatype}/",
            "file_format": "{filename}.{ext}",
            "textlength": 0,
            "space-replacer": " ",
            "date": "MM-DD-YYYY",
            "text_type_default": "letter",
            "truncation_default": true
        },
        "download_options": {
            "file_size_limit": 0,
            "file_size_min": 0,
            "filter": [
                "Images",
                "Audios",
                "Videos"
            ],
            "auto_resume": false,
            "system_free_min": 0,
            "number_retries": 10
        },
        "binary_options": {
            "mp4decrypt": "//home/james/.config/ofscraper/bin/mp4decrypt",
            "ffmpeg": "//home/james/.config/ofscraper/bin/ffmpeg"
        },
        "cdm_options": {
            "private-key": "//home/james/.config/ofscraper/device/private_key.pem",
            "client-id": "//home/james/.config/ofscraper/device/client_id.bin",
            "key-mode-default": "manual",
            "keydb_api": ""
        },
        "performance_options": {
            "download-sems": 10,
            "threads": 10
        },
        "advanced_options": {
            "code-execution": true,
            "dynamic-mode-default": "dc",
            "backend": "aio",
            "downloadbars": false,
            "cache-mode": "sqlite",
            "appendlog": false,
            "custom_values": {"MAXFILE_SEMAPHORE":10,"SHOW_AVATAR":false,
            "import":"exec('import ofscraper.filters.models.selector as selector23')",
            "list":"exec('modelObjs=C)')",
            "model_price":"'fallback' if len(modelObjs)==0 else 'Paid' if modelObjs[0].final_current_price>0 else 'Free'"
        },
            "sanitize_text": false,
            "avatar": true,
            "temp_dir": null
        },
        "responsetype": {
            "timeline": "Posts",
            "message": "Messages",
            "archived": "Archived",
            "paid": "Messages",
            "stories": "Stories",
            "highlights": "Stories",
            "profile": "Profile",
            "pinned": "Posts"
        }
    }
}
```

</details>

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

