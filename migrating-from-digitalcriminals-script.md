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

<pre class="language-markup"><code class="lang-markup"> "/<a data-footnote-ref href="#user-content-fn-1">Onlyfans/</a><a data-footnote-ref href="#user-content-fn-2">modelA/Messages/Free/Images/</a>"
</code></pre>

1. /Onlyfans is the save\_location
2. /modelA/Messages/Free/Images/ is the dir\_format

#### metadata

<pre><code>"metadata": "<a data-footnote-ref href="#user-content-fn-3">{save_location}</a>/{model_username}/Metadata"
</code></pre>

This refers to a directory path designated for storing 'user\_data.db'.

```
"OnlyFans/ModelA/Metadata"
```

```
{
    "config": {
        "main_profile": "main_profile",
        "save_location": "/root/Data/ofscraper",
        "file_size_limit": 0,
        "file_size_min": 0,
        "dir_format": "{model_username.upper()}/{responsetype}/{mediatype}/",
        "file_format": "{custom.get(filename,f'{date}-{text}.{ext}')}",
        "textlength": 0,
        "space-replacer": " ",
        "date": "MM-DD-YYYY",
        "metadata": "{configpath}/{profile}/.data/{model_username}_{model_id}",
        "filter": [
            "Images",
            "Audios",
            "Videos"
        ],
        "threads": 10,
        "code-execution": true,
        "custom": null,
        "mp4decrypt": "/root/.config/ofscraper/bin/mp4decrypt",
        "ffmpeg": "/root/.config/ofscraper/bin/ffmpeg",
        "discord": "",
        "private-key": "/root/.config/ofscraper/device/private_key.pem",
        "client-id": "/root/.config/ofscraper/device/client_id.bin",
        "key-mode-default": "manual",
        "keydb_api": "",
        "dynamic-mode-default": "deviint",
        "partfileclean": false,
        "backend": "aio",
        "download-sems": 10,
        "maxfile-sem": 0,
        "downloadbars": true,
        "cache-mode": "sqlite",
        "appendlog": false,
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

[^1]: save\_location

[^2]: dir\_format



[^3]: Save location from config

