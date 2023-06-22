# Config Options

## Example Config

```
{
    "config": {
        "main_profile": "main_profile",
        "save_location": "/root/Data/ofscraper",
        "file_size_limit": 0,
        "dir_format": "{model_username}/{responsetype}/{mediatype}/",
        "file_format": "{filename}.{ext}",
        "textlength": 0,
        "space-replacer": " ",
        "date": "MM-DD-YYYY",
        "metadata": "{configpath}/{profile}/.data/{model_username}_{model_id}",
        "filter": [
            "Images",
            "Audios",
            "Videos"
        ],
        "threads": 8,
        "code-execution": false,
        "mp4decrypt": "/root/.config/ofscraper/bin/mp4decrypt",
        "ffmpeg": "/root/.config/ofscraper/bin/ffmpeg",
        "discord": "",
        "responsetype": {
            "timeline": "posts",
            "message": "messages",
            "archived": "archived",
            "paid": "messages",
            "stories": "stories",
            "highlights": "stories",
            "profile": "profile",
            "pinned": "posts"
        }
    }
}

```

### main\_profile

In most cases their is no need to changes this

Profiles are separated by directories in the config location. The value here is based on the name of the directory.

Each directory can correspond to a different auth file.

Note: each profile will share the same config

## save\_location

root save folder

## dir\_format

format for directory

## file\_format

format for files

## filter

Controls which kind of content you want to download

```
Options are Images,Audios,Videos case insensitive
```

## file\_size\_limit

Controls the max file to download

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

for more details about switching from DigitialCriminal's script



{% embed url="https://of-scraper.gitbook.io/of-scraper/migrating-from-digitalcriminals-script" %}

You will basically need to change this setting to map to your old metadata locations

## mp4decrypt

decryption is required for certain content use this to set the path mp4decrypt for you system

This is not installed with pip and must be retrieved &#x20;

{% embed url="https://www.bento4.com/downloads/" %}

you only need mp4decrypt or mp4decrypt.exe other files can be deleted

## ffmpeg

This is required to join audio and video parts of files used with mp4decrypt to output final file



{% embed url="https://ffmpeg.org/download.html" %}

## textlength

Restricts the length of text placeholder to the number of words `0` represents unlimited text

to restrict by letter count pass `--letter-count` argument

## space-replacer

All spaces within the filename will be replaced with this character Note: This only affects the filename, and not other parts of the path like parent directories

This can be used with the text placeholder

## Responsetype

This is only used for remapping values for the {responsetype} placeholder

Empty values or "" will use the the programs default values

The initial values match with the accepted values for --posts argument

#### Example

This is to show use the responsemap to group messages, and paid content into the same folder

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
Push updates to discord using webhooks
for setup see

https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks

You need to add the url, and pass the --discord argument when running the script
```

## threads

Number of threads to use for downloading

```
min=1
max=10
```

##

code-execution This allows for the execution of code when generating metadata path, file\_format, and dir\_format

all placeholders are available as placeholders the input for these options will be converted to an f- string

```
eval("f'{}'".format(config_.get_dirformat(config_.read_config())))
```

Any python code that returns a string should be acceptable

## Config settings for save locations

More details about these settings can be seen here



{% embed url="https://of-scraper.gitbook.io/of-scraper/config-options/customizing-save-path" %}
