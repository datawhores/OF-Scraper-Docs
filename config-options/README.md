# Config Options

## Example Config

```
{
    "config": {
        "main_profile": "main_profile",
        "metadata": "{configpath}/{profile}/.data/{model_username}_{model_id}",
        "discord": "",
        "file_options": {
            "save_location": "/root/Data/ofscraper",
            "dir_format": "{model_username}/{responsetype}/{mediatype}/",
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
            "system_free_min": 0
        },
        "binary_options": {
            "mp4decrypt": "/root/.config/ofscraper/bin/mp4decrypt",
            "ffmpeg": "/root/.config/ofscraper/bin/ffmpeg"
        },
        "cdm_options": {
            "private-key": "/root/.config/ofscraper/device/private_key.pem",
            "client-id": "/root/.config/ofscraper/device/client_id.bin",
            "key-mode-default": "manual",
            "keydb_api": ""
        },
        "performance_options": {
            "download-sems": 10,
            "threads": 10
        },
        "advanced_options": {
            "code-execution": true,
            "dynamic-mode-default": "deviint",
            "backend": "aio",
            "downloadbars": false,
            "cache-mode": "sqlite",
            "appendlog": false,
            "custom_values": {},
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

###



## Config settings for save locations

Further details about these settings are available here

{% content-ref url="file-output-options/customizing-save-path.md" %}
[customizing-save-path.md](file-output-options/customizing-save-path.md)
{% endcontent-ref %}



{% content-ref url="file-output-options/" %}
[file-output-options](file-output-options/)
{% endcontent-ref %}

## Media Filtering



{% content-ref url="media-filtering-options.md" %}
[media-filtering-options.md](media-filtering-options.md)
{% endcontent-ref %}

## Key Options

{% content-ref url="key-option.md" %}
[key-option.md](key-option.md)
{% endcontent-ref %}
