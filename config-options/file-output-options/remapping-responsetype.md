# Remapping responsetype

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
