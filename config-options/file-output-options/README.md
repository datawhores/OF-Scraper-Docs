# File  Output Options

## save\_location

root save folder

## dir\_format

format for directory

## file\_format

format for files

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



## textlength

Sets a cap on the text placeholder to a certain number of words, with 0 indicating an unrestricted text length

to restrict by letter count pass `--letter-count` argument

## space-replacer

This character will replace all spaces within the filename.

It should be employed in conjunction with the text placeholder.

> &#x20;This change applies exclusively to the filename and doesn't affect other path components like parent directories.

## appendlog

If set to False, each run will generate a new log. If set to True, logs will be combined into one file per day.

## responsetype

This setting solely remaps values for the {responsetype} placeholder

Empty values or "" will default to the program's preset values

#### Example

This configures the response map to consolidate messages and paid content into a unified folder.

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

##
