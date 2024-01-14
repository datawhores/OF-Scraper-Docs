# Customizing save path

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

Each file will be saved to `/home/James/Data/ofscraper/{model_username}/{responsetype}/{mediatype}/{filename}.{ext}`

The placeholders described below will substitute the {} values

## save\_location

This is the root of all saved files

## dir\_path

The  relative directory path within the save location where files are stored

```
{date}=
The creation date of the post, refer to the 'date' section for formatting guidelines. 
Please open an issue if further assistance is required.

{responsetype}=Posts,Messages,Paid,etc

{mediatype}=Images,Audios,Videos

{value}=The content's value: Whether it's categorized as Paid or Free.

{model_id}= Unique identification number for model

{first_letter}= first letter of model's username

{sitename} = Onlyfans

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

```

## Filename

The file's name segment in the saved file

{% hint style="info" %}
```
When configuring filenames, ensure a unique element 
such as text, media ID, post ID, or filename to avoid naming conflicts
```
{% endhint %}

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{post_id} = The posts' ID

{media_id} = The media's ID

{model_username} = The model's username

{responsetype} = Posts,Messages,Paid,etc

{mediatype} = Images,Audios,Videos,etc

{filename} = The media's filename

{value} = The content's value: Whether it's categorized as Paid or Free

{text} = The text within the media. Truncation of file names has been tested to fit within OS limits, 
still it's advisable to establish a text length limit.
{date} = The date when the post was created.
{model_id}= Unique identification number for model


{ext} = The file extension of the media
{profile} = The currently active profile
{my_username}=The authorized account's username
{my_id} = The identification number 
for the  authorized account
{label} =  The label assigned to the post, if available
{download_type}= Protected if decryption required otherwhise normal

{current_price}= Free if current price is 0 dollars else paid
{regular_price}=Free if regular price is 0 dollars else paid
{promo_price}= Free if promo price is 0 dollars else paid
{renewal_price}= Free if renewal price is 0 dollars else paid
```



## date&#x20;

\
The date syntax doesn't use bracket notation; it adheres to the Arrow implementation.&#x20;

For more information, check the documentation at [https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens](https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens). If you need additional help, feel free to open an issue in the repository for support.

## textlength&#x20;

As a default, it is the maximum number of words. You can switch this to the maximum number of letters by using the '--letter-count' argument.&#x20;

Remember, specifying '0' equates to no limit.

## Remapping responsetype&#x20;

This feature enables you to group downloads using the 'responsetype' placeholder. It allows combining various download types into a single folder or segregating downloads into separate folders based on their 'responsetype.'

For example, you can merge 'stories' and 'highlights' into one folder or categorize 'purchased' items and 'messages' into a folder named 'Premium.' Another option is to organize 'timeline posts' into a separate folder labeled 'posts.'

The initial value indicates the mapped response type, which should remain unchanged. The second value determines the remapped 'responsetype.'

#### Example

```
"timeline": "posts",
"message": "premium",
"archived": "archived",
"paid": "premium",
"stories": "stories",
"highlights": "stories",
 "profile": "profile"
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

These default settings are crafted to ensure maximum compatibility with Digitalcriminal's script.
