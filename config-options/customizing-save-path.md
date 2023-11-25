# Customizing save path

You can adjust the file save path by editing the configuration file.

## Config Path

### Windows

I'm not someone who uses Windows on a daily basis, but it should be

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

The placeholders described below will substitute the {} values

### save\_location

This is the root of all saved files

### dir\_path

The  relative directory path within the save location where files are stored

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
{profile} = the current active profile
{my_username}=the username for the authorized account
{my_id} = the id for the authorized account
{label} = label of post if present
{download_type}= Protected or Normal based on need for decryption

```

### Filename

The file's name segment in the saved file\




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


{ext} = The media's file extension
{profile} = the current active profile
{my_username}=the username for the authorized account
{my_id} = the id for the authorized account
{label} = label of post if present otherwise empty ""
{download_type}= Protected or Normal based on need for decryption
```

#### <mark style="color:red;">**Warning**</mark>

```
When setting up filename make sure you have a unique element 
text,media_id,post_id,filename  are all unique element

Without this filenames will conflict
```

### date (optional)

\
The date syntax varies and doesn't utilize bracket notation; instead, it follows the Arrow implementation.

For more details, refer to the documentation at [https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens](https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens).&#x20;

If you require further assistance, consider opening an issue in the repository for support

### textlength

By default, it includes the maximum number of words

&#x20;You have the option to switch this to the maximum number of letters using the '--letter-count' argument

Keep in mind, specifying '0' equals to no limit.

## Remapping Responsetype

This functionality lets you group downloads using the 'responsetype' placeholder. It also allows combining different download types into a single folder or directing downloads to separate folders based on their 'responsetype'

For instance, you have the option to consolidate all 'stories' and 'highlights,' or categorize 'purchased' items and 'messages' within a designated folder named 'Premium.' Another possibility is to organize 'timeline posts' into a distinct folder titled 'posts.'

The initial value represents the response type it's mapped to, which shouldn't be altered. The second value determines what the 'responsetype' should be remapped to

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
