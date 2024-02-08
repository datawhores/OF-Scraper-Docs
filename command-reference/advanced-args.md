# Advanced Args

### -uf, --users-first

```
Prioritize downloading posts by scraping all users at once instead of one at a time
```

```
Default: False
```

### -nc, --no-cache

```
meant for disabling cache when scraping posts
```

```
Default: False
```

### -k, --key-mode

```
Override the key mode in the configuration file
```

```
default: auto
```

### -db, --download-bars&#x20;

```
Override the download-bars setting in the configuration file
```

```
default: None
```

### -sd, --download-sems

```
Override the download-sems setting in the configuration file
```

```
default: None
```

### -sd, --download-threads

```
Override the download-threads setting in the configuration file

Setting the value to zero will force the use of the main thread for downloading. 
The main thread is also utilized if downloads cannot fill the download-sems.
```

```
default: None
```

### -ar,--no-auto-resume

{% hint style="info" %}
This replaces \
part-cleanup
{% endhint %}

```
cleanup part files on program exit

This includes forced exit
```

```
default: false
```

### -dr,--dynamic-rules

```
Override the dynamic-rules setting in the configuration file; 
it's utilized for signing requests
```

```
default: false
```

### -md, --metadata

{% hint style="info" %}
**progress bar  shows  all downloads as skipped**
{% endhint %}

{% hint style="info" %}
**No change to download field for media entries in database**
{% endhint %}

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Does not change download status
```

### -mc, --metadata-complete

{% hint style="info" %}
**progress bar shows all download mediatypes**
{% endhint %}

{% hint style="info" %}
**Marks all media entries in database as downloaded by setting the "download" field to True**
{% endhint %}

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Additionally marks each media as downloaded
```

### -mu, --metadata-update

{% hint style="info" %}
**progress bar marks downloads without files as skipped**

**progress bar marks downloads with files as based on mediatype**
{% endhint %}

{% hint style="info" %}
**Media entries in the database will have their "download" field flagged as False upon verification that the corresponding files are missing**
{% endhint %}

```

This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database

Marks every download based on presence on file system
```

### **-fi, --force-individual**

```
When --username arg is provided searches each username as a seperate request
```

### **-fl, --force-list**

```
When --username arg is provided searches entire list based on the currently enabled 
config settings for userlist or --user-list arg
```

### **-up, --update-profile**

```
gets up to date profile info, rather then using cache
Note: Profile cache is saved  for about a day
```
