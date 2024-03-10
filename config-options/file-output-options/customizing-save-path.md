# Placeholders

{% hint style="warning" %}
**If you want to recheck files**\
**--metadata-update after updating the config**
{% endhint %}

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
```



</details>

The placeholders described below will substitute the {} values

Each file will be saved to&#x20;

```
/home/James/Data/ofscraper/{model_username}/{responsetype}/
{mediatype}/{filename}.{ext}
```

***

{% hint style="info" %}
**Placeholders are generally the same between options here**
{% endhint %}

## dir\_path and filename

{% hint style="info" %}
**You may use placeholders without any underscores (\_)**
{% endhint %}

```

{response_type}=Posts,Messages,Paid,etc
{post_id}= ID of post
{media_id} =ID of media

{file_name} = the filename, videos wills include the quality i.e source,720
{only_file_name}= the filename,videos will not include quality
{original_filename}= filename as sent by onlyfans, may or may not include source

{media_type}=Images,Audios,Videos
{quality} = quality of the media, none videos will always be source

{value}=The content's value: Whether it's categorized as Paid or Free.

{model_id}= Unique identification number for model

{first_letter}= first letter of model's username

{site_name} = Onlyfans
{text} = The text within the media. Truncation of file names has been tested to fit within OS limits, 
still it's advisable to establish a text length limit.
{date}= The date of the post, outputed in the config date format

{model_username} = The model's username
{username} = The model's username
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
{args}= the passed arguments namespace, keys can be access 
with the dot (.) syntax
{config}= the config arguments dictionary, keys can be access 
with the [] syntax
{modelObj} = model data class via class folder, properties can be access 
via the dot (.) syntax
{configPath} = path to current config directory

```

### dir\_path

The  relative directory path within the save location where files are stored

{% hint style="info" %}
**No unique placeholders**
{% endhint %}



### filename

The file's name segment in the saved file

{% hint style="info" %}
**When configuring filenames, ensure a unique element such as text, media ID, post ID, or filename is added to avoid naming conflict**
{% endhint %}

```
{ext} = The file extension of the media

```



***

## Text Placeholders

{% hint style="info" %}
**Text mediatype will most likely need a overwrite to work properly**
{% endhint %}

Text files are based on posts and have access to all the same placeholders as other media **except for**

* any filename related placeholders
* media\_id&#x20;
* media\_type
* quality
* download type



{% content-ref url="../../batch-scraping-and-bot-actions/downloading-text-files.md" %}
[downloading-text-files.md](../../batch-scraping-and-bot-actions/downloading-text-files.md)
{% endcontent-ref %}

{% content-ref url="../mediatype-overwrites.md" %}
[mediatype-overwrites.md](../mediatype-overwrites.md)
{% endcontent-ref %}

***

## metadata

Controls where metadata is save

{% content-ref url="../setting-metadata-path.md" %}
[setting-metadata-path.md](../setting-metadata-path.md)
{% endcontent-ref %}

***

## response\_type placeholder

{% content-ref url="remapping-responsetype.md" %}
[remapping-responsetype.md](remapping-responsetype.md)
{% endcontent-ref %}
