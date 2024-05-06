---
description: Options for controlling which media is downloaded
---

# Media Filters Options

### -sx,--size-max



```
Filter files larger than the specified size. 
This filter accepts human-readable strings like "10GB"

```

```
Default: None
```

### -sm,--size-min

```
Filter files smaller than the specified size. 
This filter accepts human-readable strings like "10GB"

```

```
Default: None
```



***

### -lx,--length-max



```
Filters files with duration greater than provided value
Does not effect non-video files
```

```
Default: None
```

### -lm,--length-min

```
Filters files with duration less than provided value
Does not effect non-video files
```

```
Default: None
```



***

### -q,--quality

```
The --quality flag determines the minimum acceptable quality, 
with the actual choice falling back to the 
lowest available option within --quality to "source"

```

```
Possible Choices: source,240,720
```

```
Default: source
```

