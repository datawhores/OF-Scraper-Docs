# Migrating from Digitalcriminal's script

{% embed url="https://of-scraper.gitbook.io/of-scraper/config-options/setting-metadata-path" %}

## Example

This is based on common settings from DC script

```
 "dir_format": "{model_username}/{responsetype}/{value}/{mediatype}/"
```

Means a path like&#x20;

```
 "dir_format": "modelA/Messages/Free/Images/"
```



\


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
