# Placeholders

{% hint style="info" %}
**If you want to move files use** \
**--metadata or --metadata-complete after updating the config**
{% endhint %}

## Example

<details>

<summary>Example Config</summary>

```json
{
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

<details>

<summary><mark style="color:red;">Windows path warning</mark></summary>

<mark style="color:red;">**`\ should be escaped or replaced with a \\ or /`**</mark>

<mark style="color:red;">**`Not doing this could lead to an error`**</mark>

<mark style="color:red;">**`Examples:`**</mark>

```
C:\Users\John.config\ofscraper\bin\ffmpeg.exe => 
```

```
C:\Users\John.config\ofscraper\bin\ffmpeg.exe => 
C:/Users/John.config/ofscraper/bin/ffmpeg.exe
```

</details>

The placeholders described below will substitute the {} values

Each file will be saved to&#x20;

```
//home/James/Data/ofscraper/{model_username}/{responsetype}/
{mediatype}/{filename}.{ext}
```

***

## dir\_path and filename

{% hint style="info" %}
**Placeholders are generally the same between options here**
{% endhint %}

```

{responsetype}=Posts,Messages,Paid,etc

{filename} = the filename, videos wills include the quality i.e source,720
{only_filename}= the filename,videos will not include quality

{mediatype}=Images,Audios,Videos

{value}=The content's value: Whether it's categorized as Paid or Free.

{model_id}= Unique identification number for model

{first_letter}= first letter of model's username

{sitename} = Onlyfans
{text} = The text within the media. Truncation of file names has been tested to fit within OS limits, 
still it's advisable to establish a text length limit.

{model_username} = The model's username
{profile} = The currently active profile
{my_username}=The authorized account's username
{my_id} = The identification number 
for the  authorized account
{label} = The label assigned to the post, if available
{download_type}= Indication of whether it's protected or normal, 
determined by the necessity for decryption

{current_price}= Free if current price is 0 dollars else paid
{regular_price}=Free if regular price is 0 dollars else paid
{promo_price}= Free if promo price is 0 dollars else paid
{renewal_price}= Free if renewal price is 0 dollars else paid
{args}= the passed arguments namespace, keys can be access with the dot (.) syntax
{config}= the config arguments dictionary, keys can be access with the [] syntax
```

### dir\_path

The  relative directory path within the save location where files are stored

{% hint style="info" %}
**No unique placeholders**
{% endhint %}



### filename

The file's name segment in the saved file

{% hint style="info" %}
**When configuring filenames, ensure a unique element such as text, media ID, post ID, or filename to avoid naming conflict**
{% endhint %}

```
{ext} = The file extension of the media
```

***

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

***

## response\_type placeholder

{% content-ref url="remapping-responsetype.md" %}
[remapping-responsetype.md](remapping-responsetype.md)
{% endcontent-ref %}
