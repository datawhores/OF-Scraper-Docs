# Config Options

## Example Config

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

### main\_profile

In most cases, there's no need to modify this setup. Profiles are organized into directories within the config location, with the value being derived from the directory name. Each directory can correspond to a distinct authentication file.&#x20;

Note: all profiles will share the same configuration.

## save\_location

root save folder

## dir\_format

format for directory

## file\_format

format for files

## filter

Determines the type of content you wish to download.

```
Options are Images,Audios,Videos case insensitive
```

## file\_size\_limit

Controls the maximum allowable file size for downloads

Note: This is in bytes

## file\_size\_min

Controls the minimum allowable file size for downloads

Note: This is in bytes



## metadata

Controls where metadata is saved

You can use these placeholders

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{model_username} = The model's username.

{model_id}= unique id number for model
{configpath}= parent dir of config.json
{profile} = current profile 

```

### Migrating From Digitalcriminals' Script

For more detailed information regarding the transition from DigitialCriminal's script

{% embed url="https://of-scraper.gitbook.io/of-scraper/migrating-from-digitalcriminals-script" %}

Essentially, you'll need to adjust this setting to align with your previous metadata locations.



## mp4decrypt

Decryption is necessary for specific content. Utilize this to establish the path for 'mp4decrypt' on your system.

Please note, it's not available through pip and must be obtained separately.

{% embed url="https://www.bento4.com/downloads/" %}

You'll only require 'mp4decrypt' or 'mp4decrypt.exe'

other files can be deleted.

\


## ffmpeg

This is necessary to combine audio and video parts of files utilized with mp4decrypt, resulting in the final output file

{% embed url="https://ffmpeg.org/download.html" %}

## textlength

Sets a cap on the text placeholder to a certain number of words, with 0 indicating an unrestricted text length

to restrict by letter count pass `--letter-count` argument

## space-replacer

This character will replace all spaces within the filename.

&#x20;Note: This change applies exclusively to the filename and doesn't affect other path components like parent directories.

It should be employed in conjunction with the text placeholder.

## appendlog

If set to False, each run will generate a new log. If set to True, logs will be combined into one file per day.

## Responsetype

This setting solely remaps values for the {responsetype} placeholder

Empty values or "" will default to the program's preset values

#### Example

This configures the responsemap to consolidate messages and paid content into a unified folder.

```
"timeline": "Posts",
"message": "Premium",
"archived": "Archived",
"paid": "Premium",
"stories": "Stories",
"highlights": "Stories",
 "profile": "Profile"
```

```
dir_format": "{model_username}/{responsetype}/{mediatype}/"
```

```
timeline -> maps to posts -> files save to "{model_username}/Posts/{mediatype}/"
messages -> maps to premium -> files save to "{model_username}/Premium/{mediatype}/"
archived -> maps to archived -> files save to "{model_username}/Archived/{mediatype}/"
paid -> maps to premium -> files save to "{model_username}/Premium/{mediatype}/"
stories -> maps to stories -> files save to "{model_username}/Stories/{mediatype}/"
highlight -> maps to stories  -> files save to "{model_username}/Stories/{mediatype}/"
profile -> maps to archived  -> files save to "{model_username}/Profile/{mediatype}/"
```

## discord

```

To send updates to Discord using webhooks, 
follow the setup guide at
https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks.
  
You'll need to add the URL provided in the setup 
and include the --discord argument when executing the script.
```



## Config settings for save locations

Further details about these settings are available here

{% embed url="https://of-scraper.gitbook.io/of-scraper/config-options/customizing-save-path" %}

Key Options
