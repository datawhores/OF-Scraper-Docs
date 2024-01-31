# Config Options

\


<details>

<summary>Example Config</summary>



<pre class="language-json"><code class="lang-json">{
    "config": {
        "main_profile": "main_profile",
        "metadata": "{configpath}/{profile}/.data/{model_username}_{model_id}",
        "discord": "",
        "file_options": {
            "save_location": "/home/james/Data/ofscraper",
            "dir_format": "/{model_username}/{responsetype}/{mediatype}/",
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
            "custom_values": {},
            "sanitize_text": false,
            "avatar": true,
            "temp_dir": null,           
<strong>            "disable_after_check": false,
</strong>            "default_user_list": "main",
            "default_black_list": ""
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
</code></pre>

</details>

## Config settings for save locations

**Customize the final file path for downloads**

{% content-ref url="file-output-options/customizing-save-path.md" %}
[customizing-save-path.md](file-output-options/customizing-save-path.md)
{% endcontent-ref %}

{% content-ref url="file-output-options/" %}
[file-output-options](file-output-options/)
{% endcontent-ref %}

## Media Filtering

**Customize which files are downloaded**

{% content-ref url="download-options/media-filtering-options.md" %}
[media-filtering-options.md](download-options/media-filtering-options.md)
{% endcontent-ref %}

## Key Options

**These settings are required for some files**

{% content-ref url="key-option.md" %}
[key-option.md](key-option.md)
{% endcontent-ref %}
