# Advanced config options

##



## threads

Number of threads or workers to use for downloading

```
min=0
max=10
```

0 threads: This is a special setting indicating that you want to use the main program thread for downloading as well\
\
Another thing to note, is that even with a thread number greater then 0\
If the number of downloads for a model is not high enough, then the main thread will be used for downloading



## download-sems

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time.\
\


## maxfile-sem

wraps around download function to control the total number of files be processed at once

Zero means no limit.&#x20;

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

