# Advanced config options

##



## threads

Number of threads or workers to use for downloading

```
min=0
max=10
```

0 threads: This is a special setting indicating that you want to use the main program thread for downloading as well\


### Caveats

\
One thing to note, is that even with a thread number greater then 0\
If the number of downloads for a model is not higher then download sems , then only the main thread will be used for downloading

Second the max number of usable threads will be set based on your system regardless of what is in the config file\
\
This is tied to the unused threads on windows and linux

On Mac the OS does not provide this as part of the os api, thus the max is set to the total number of threads on the system







## download-sems

Max concurrent number of downloads per thread

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time.\
\


## maxfile-sem

Max concurrent files per thread

wraps around download function to control the total number of files be processed at once

\
Zero means no limit

Changing this setting should only be required in very unique cases\




## code-execution

code-execution This allows for the execution of code when generating metadata path, file\_format, and dir\_format

all placeholders are available as placeholders the input for these options will be converted to an f- string\
\
As an example

```
eval("f'{}'".format(config_.get_dirformat(config_.read_config())))
```

Any python code that returns a string should be acceptable

## custom

Previously custom was converted into a dictionary with the built in json libary in python

While  this is still possible

OF-Scraper now offers the ability to write small scripts within the custom block



````
```python
            if not isinstance(custom,dict)==True:
                try:return eval(custom)
                except:return custom
            for key,val in custom.items():
                try:custom[key]=eval(val)
                except:continue
```
````

\
This allows for accessing the customized value by using



```
custom.get(key)
```

During filename creation



For example&#x20;

```
code-execution:true
dir_format:{custom.get(model_username,model_username)}
custom={"mymodel","'replace'.lower()"}
```

Something importnat to see is that when dealing with strings\
The inner quotes are important since eval processes&#x20;

what is inside the quotes as code



## dynamic Rules

Used for signing request

Without this request would fail to authorized



There is mostly no difference between the options.

On rare occasions  changing these may fix issues



\


## cache-mode

The script using diskcache -> [https://grantjenks.com/docs/diskcache/tutorial.html#caveats](https://grantjenks.com/docs/diskcache/tutorial.html#caveats)\
\
sqlite is fine for most users\
However certain users may want to look into the json backend\
\
For example the author notes that sqlite performance may be limited on network drives.

So switching to json is a good option&#x20;



backend\



Both aio and httpx are able to process downloads, and requests

Switching is only required if your the small percentage of users who system does not perform well with aio. Historically this has been mac users, and a subset of that



## partfileclean

WIthout this the script will try to auto resume .part files

Consequently  if left off, then you may see your folder filled with .part files if many downloads fail.

## downloadbars

Whether or not to display download bars

Turning these off can have a postive effect on performance
