# Example Configs

## Example 1

<pre><code><strong>{
</strong>    "config": {
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
            "mp4decrypt": "/home/james/.config/ofscraper/bin/mp4decrypt",
            "ffmpeg": "/home/james/.config/ofscraper/bin/ffmpeg"
        },
        "cdm_options": {
            "private-key": "/home/james/.config/ofscraper/device/private_key.pem",
            "client-id": "/home/james/.config/ofscraper/device/client_id.bin",
            "key-mode-default": "manual",
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
            "custom_values":null
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
</code></pre>

## Digitialcriminals Example

```
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
        },
        "performance_options": {
            "download-sems": 10,
            "threads": 10
        },
        "advanced_options": {
            "code-execution": true,
            "dynamic-mode-default": "dc",
            "logs_expire_time": 0.0
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
     "script_options": {
        "post_download_script": null,
        "post_script": null
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
