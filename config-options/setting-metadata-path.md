# Setting metadata path

In the config.json file, you can modify the default metadata location or adjust where the script searches for database files

Using your existing metadata files from DIGITALCRIMINALS' script enables immediate utilization for dupe checks, with any new files added subsequently being appended to the existing ones

## Config File Location

### Windows

I'm not someone who uses Windows on a daily basis, but it should be&#x20;

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

Replace "username" with your login name

## Changing metadata location

Modify the metadata section in the config.json file using these placeholders

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{model_username} = The model's username.

{model_id}= unique id number for model
{configpath}= parent dir of config.json
{profile} = current profile 
{save_location} = returns the parsed path from 'save_location' option
{profile} = currently active profile
{my_username}=the username for the authorized account
{my_id} = the id for the authorized account
```
