---
description: Advanced control of program behavior
---

# Advanced Program Options

***

### -nc, --no-cache

```
Disables read/writing to cache
Along with, forcing consecutive api scans
```

```
Default: False
```

### -nca, --no-api-cache

```
Forces a consecutive api scans
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

### -dr,--dynamic-rules

```
Override the dynamic-rules setting in the configuration file; 
it's utilized for signing requests
```

```
default: false
```

***

### **-up, --update-profile**

```
gets up to date profile info, rather then using cache
Note: Profile cache is saved  for about a day
```

### **-ds, --download-script**

```
runs a script post model download via subprocess
addional args sent include username, model_id, media json ,and post json

Note: jsons are based on the original api responses
additional data will be added for ease of use
```
