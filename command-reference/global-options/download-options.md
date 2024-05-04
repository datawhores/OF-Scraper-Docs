---
description: Options for managing downloads
---

# Download Options

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

{% hint style="warning" %}
**This replaces** \
**part-cleanup**
{% endhint %}

```
cleanup part files on program exit

This includes forced exit
```

```
default: false
```
