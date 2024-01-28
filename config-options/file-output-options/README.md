---
description: Settings for File Names
---

# File Output Options

## Save Path Options

{% content-ref url="customizing-save-path.md" %}
[customizing-save-path.md](customizing-save-path.md)
{% endcontent-ref %}

### save\_location

root save folder

### dir\_format

format for directory

### file\_format

format for files

### textlength

Sets a cap on the text placeholder to a certain number of words, with 0 indicating an unrestricted text length

to restrict by letter count pass `--letter-count` argument

### space-replacer

{% hint style="info" %}
&#x20;**This change applies exclusively to the filename and doesn't affect other path components like parent directories.**
{% endhint %}

This character will replace all spaces within the filename.

It should be employed in conjunction with the text placeholder.

### text\_type\_default

Whether to count text based on words on letters

### truncation\_default

* If set to true text that is calculated to be over system limit will be shorted
* Files whose paths are over the limit may still fail

### date&#x20;

\
The date syntax doesn't use bracket notation; it adheres to the Arrow implementation.&#x20;

For more information, check the documentation at [https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens](https://arrow.readthedocs.io/en/latest/guide.html#supported-tokens).&#x20;

If you need additional help, feel free to open an issue in the repository for support.

## Other Related Options

These options also effect the final file name

### responsetype

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

## metadata

{% content-ref url="setting-metadata-path.md" %}
[setting-metadata-path.md](setting-metadata-path.md)
{% endcontent-ref %}

Metadata is mainly used for&#x20;

* dupe check
* To speed up scanning of profiles

It can also be shared with other programs via the .db files created
