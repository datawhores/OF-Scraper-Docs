# Advanced Args

###



##

###

### Advanced

Advanced Args

#### -uf, --users-first

```
Prioritize downloading posts by scraping all users at once instead of one at a time
```

```
Default: False
```

#### -nc, --no-cache

```
disable cache
```

```
Default: False
```

#### -k, --key-mode

```
Override the key mode in the configuration file
```

```
default: auto
```

#### -db, --download-bars&#x20;

```
Override the download-bars setting in the configuration file
```

```
default: None
```

#### -sd, --download-sems

```
Override the download-sems setting in the configuration file
```

```
default: None
```

#### -sd, --download-threads

```
Override the download-threads setting in the configuration file

Setting the value to zero will force the use of the main thread for downloading. 
The main thread is also utilized if downloads cannot fill the download-sems.
```

```
default: None
```

#### -pc,--part-cleanup

```

Override the tempfile clean setting in the configuration
file, eliminating the ability to resume downloads.
```

```
default: false
```

#### -dr,--dynamic-rules

```
Override the dynamic-rules setting in the configuration file; 
it's utilized for signing requests
```

```
default: false
```

### -md, --metadata

```
This feature skips the downloading of files to the disk, 
primarily designed for adding metadata to the database.
```
