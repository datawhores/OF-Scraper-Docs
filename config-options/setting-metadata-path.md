# Setting metadata path

You can change the default metadata or where the script looks for database files in config.json

Using your old metadata files from DIGITALCRIMINALS' script allows for them to be used for dupe check right away additional new files will be appended to the files

## Config File Location

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

## Changing metadata location

Edit the metadata section in the config.json

You can use these placeholders

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{model_username} = The model's username.

{model_id}= unique id number for model
{configpath}= parent dir of config.json
{profile} = current profile 
{save_location} = returns the parsed path from 'save_location' option

```
