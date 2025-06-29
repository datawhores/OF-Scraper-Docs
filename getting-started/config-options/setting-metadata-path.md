# Setting metadata path

In the config.json file, you can modify the default metadata location or adjust where the script searches for database files

Using your existing metadata files from DIGITALCRIMINALS' script enables immediate utilization of the dupe checker, with any new files added subsequently being appended to the existing ones

***

## Config File Location

{% content-ref url="config-location.md" %}
[config-location.md](config-location.md)
{% endcontent-ref %}

## Changing metadata location

Adjust the metadata section in the config.json file by inserting the appropriate locations or paths using the provided placeholders

```
{sitename} = Onlyfans

{first_letter} = first letter of model's username

{model_username} = The model's username.

{model_id}= Unique identification number for model
{config_path}= The directory containing the config.json file
{profile} =The currently active profile
{save_location} = This option retrieves the parsed path specified in the 'save_location' 
option
{my_username}=The authorized account's username
{my_id} = The identification number assigned to the authorized account

{current_price}= Free if current price is 0 dollars else paid
{regular_price}=Free if regular price is 0 dollars else paid
{promo_price}= Free if promo price is 0 dollars else paid
{renewal_price}= Free if renewal price is 0 dollars else paid
```
