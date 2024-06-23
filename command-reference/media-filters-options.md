---
description: >-
  These options allow you to filter downloaded media based on various criteria,
  helping you manage storage space and download times.
---

# Media Filters Options

## File Size Filters

### -sx, --size-max \[argument]

* **Filters:** Files exceeding the specified size.
* **Accepts:** Human-readable size values like "10MB", "500GB", etc.
* **Default:** `None` (no maximum size filter)
* **Example:** With `-sx 1GB`, only files 1 gigabyte or smaller will be downloaded.

### -sm, --size-min \[argument]

* **Filters:** Files smaller than the specified size.
* **Accepts:** Human-readable size values like "10MB", "500GB", etc.
* **Default:** `None` (no minimum size filter)
* **Example:** With `-sm 50MB`, only files 50 megabytes or larger will be downloaded.



***

## Media Length Filters (Video Only)

These filters only apply to video files.

### -lx, --length-max \[argument]

* **Filters:** Videos longer than the specified duration.
* **Accepts:** Values that will be interpreted as seconds
* **Default:** `None` (no maximum length filter)
* **Example:** With `-lx 30`, only videos shorter or equal to 30 seconds will be downloaded.

### -lm, --length-min \[argument]

* **Filters:** Videos shorter than the specified duration.
* **Accepts:** Values that will be intepreted as seconds
* **Default:** `None` (no minimum length filter)
* **Example:** With `-lm 5m`, only videos 5 seconds or longer will be downloaded.



***

## Media Quality Filter

### -q, --quality \[argument]

* **Sets:** The minimum acceptable video quality
* **Possible choices:**
  * `source`: Attempts to download the highest available quality (may not always be achievable).
  * `240`: Filters for videos with a resolution of at least 240p.
  * `720`: Filters for videos with a resolution of at least 720p.
* **Default:** `source` (attempts to download highest quality)
* **Note:** The program might download a higher quality version if the specified quality is unavailable



***

## Media ID Filter

### -md,--media-id \[argument]

* **Filters:** filters based on mediaid
* **Default:** None
* **Note:** This will have no effect on search speed, as filtering must be done after all posts are found



