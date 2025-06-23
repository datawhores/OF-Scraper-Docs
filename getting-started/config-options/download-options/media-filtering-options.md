---
description: Settings control which media is downloaded
---

# Media Filtering Options

## filter

Determines the type of content you wish to download.

```
Options are Images,Audios,Videos case insensitive
```



## file\_size\_limit

Controls the maximum allowable file size for downloads

* ignored if 0 or None
* provided value should be in bytes or human readable string like '10MB'

## file\_size\_min

Controls the minimum allowable file size for downloads

* ignored if 0 or None
* provided value should be in bytes or human readable string like '10MB'



## length\_max

Limits processed items to media as long or  longer then the given length

in seconds

* ignored if 0
* only used to filter videos

## length\_min

Limits processed items to media as short or  shorter then the given length

in seconds

* ignored if 0
* only used to filter videos

## block\_ads

remove posts with based on built in AD regex

```
r"(#(?:ad|ads|AD|advertising|sponsored|promotion)|trial|discount|exclusive\s+offer|giveaway|limited\s+time|\Buser\s+promo|shoutout|endorsement)"

```

## max\_post\_count

The maximum  number of items to process
