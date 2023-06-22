# Customizing save path

You can edit the save path of files by editing the config file



### Windows

Not a daily windows user, but it should be

```
C:/Users/username/.config/ofscraper/config.json
```

### Linux

```
/home/username/.config/ofscraper/config.json
```

or

```
/root/.config/ofscaper/config.json
```

where username is your login name

### Change config location

This can also be changed with the --config option

## Editing Save path

```
{
    "config": {
        "main_profile": "main_profile",
        "save_location": "/root/Data/ofscraper",
        "file_size_limit": 0,
        "dir_format": "{model_username}/{responsetype}/{mediatype}/",
        "file_format": "{filename}.{ext}",
        "textlength": 0,
        "date": "MM-DD-YYYY",
        "metadata": "{configpath}/{profile}/.data/{model_username}_{model_id}",
        "filter": [
            "Images",
            "Audios",
            "Videos"
        ],
        "responsetype": {
            "timeline": "Posts",
            "message": "Messages",
            "archived": "Archived",
            "paid": "Paid",
            "stories": "Stories",
            "highlights": "Highlights",
            "profile": "Profile",
            "pinned": "Pinned"

        }
    }
}
```

Each file will be saved to `/root/Data/ofscraper/{model_username}/{responsetype}/{mediatype}/{filename}.{ext}`

where the {} values will be replaced with the placeholders described below

### save\_location

This is the root of all saved files

### dir\_path

relative path within save\_location to save files

```
{date}=The post's creation date, see date section for formatting
open issue if you need help

{responsetype}=Posts,Messages,Paid,etc

{mediatype}=Images,Audios,Videos

{value}=Value of the content. Paid or Free.

{model_id}= unique id number for model

{first_letter}= first letter of model's username

{sitename} = Onlyfans

{model_username} = The model's username
```

### Filename

The filename part of saved file

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{post_id} = The posts' ID.

{media_id} = The media's ID.

{model_username} = The model's username.

{responsetype} = Posts,Messages,Paid,etc

{mediatype} = Images,Audios,Videos,etc

{filename} = The media's filename.

{value} = Value of the content. Paid or Free.

{text} = The media's text. Truncation of file names has been tested to fit with OS limits. However, it is still recommended to set a textlength limit.


{date} = The post's creation date.
{model_id}= unique id number for model


{ext} = The media's file extension.
```

### date (optional)

The synax for date is different, and does not use bracket syntax is based on arrow implementation

see https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens

open issue in repo if you need help

### textlength

default is max number of words to include

You can change this to max number of letters with --letter-count arg

Note: 0 corresponds to no limit

## Remapping Responsetype

This feature allows you to use the responsetype placeholder to group downloads, but to go further and group multiple types of downloads in the same folder. Or remap downloads into a different folder based on responsetype.

For example you could group all stories and highlights, or put purchased and messages into a folder called 'Premium'. Another option would be to put timeline post into a folder called posts.

The first value is the type of response it mapping too, you should not change this value. The second value is what value responsetype should remap to

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

The default settings here are designed to maximize compatibility with Digitalcriminal's script
