# Migrating from Digitalcriminal's script



{% embed url="https://of-scraper.gitbook.io/of-scraper/config-options/setting-metadata-path" %}



## Example

Lets say you have this common setup for storing metadata /Onlyfans/Modelx/Metadata where ModelX can be replaced with any username

This is a config that could be used in this case Pay attention to the save\_location and metadata arguments

```
{
    "config": {
        "main_profile": "main_profile",
        "save_location": "/Onlyfans",
        "file_size_limit": 0,
        "dir_format": "{model_username}/{responsetype}/{mediatype}/",
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
