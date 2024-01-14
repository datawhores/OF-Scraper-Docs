# Advanced config options

## threads

The count of threads or workers designated for downloading

```
min=0
max=10
```

0 threads: This is a special setting indicating that you want to use the main program thread for downloading as well\


### Caveats

* It's important to note that if the thread count exceeds 0 but the number of downloads for a model doesn't surpass a minimum per thread, only the main thread will handle the downloading process.
*   Additionally, the maximum number of usable threads is determined by your system, irrespective of the configuration file settings.



    * This is linked to the handling of unused threads on Windows and Linux. However, on Mac, the operating system lacks this specific OS API, so the maximum is established as the total number of threads on the system



## download-sems

Max concurrent number of downloads per thread

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time.\
\


## maxfile-sem

The maximum concurrent number of downloads per thread is defined by 'download-sems.'&#x20;

So, if 'threads' represents the count of workers for downloading, 'download-sems' specifies the number of tasks each worker can handle simultaneously.

## code-execution

The 'code-execution' feature enables code execution during the generation of metadata, path, file\_format, and dir\_format.&#x20;

All available placeholders can be used within these options, and the input for these choices will be transformed into an f-string for processing.\
\
As an example

```
eval("f'{}'".format(config_.get_dirformat(config_.read_config())))
```

Any Python code that produces a string as its output should work just fine in this context.

## custom

Before, 'custom' was transformed into a dictionary using Python's built-in JSON library.&#x20;

While this approach remains an option, OF-Scraper now supports scripting within the 'custom' block, allowing for the inclusion of small scripts directly.\


### How it works

{% hint style="info" %}
**Use exec if you need to save a variable**\
**the keys should be executed in order**
{% endhint %}

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

Each value in dictionary is ran through eval, meaning each value should be a statement that equals some value

You can access the calculated value via

```
custom.get(key)
```

### Example

```
code-execution:true
dir_format:{custom.get(model_username,model_username)}
custom={"mymodel","'replace'.lower()"}
```

It's crucial to note that when working with strings, the inner quotes hold significance because 'eval' interprets what's inside the quotes as code.&#x20;

Therefore, maintaining the inner quotes is vital for accurate interpretation by 'eval'.

### Changing const

You can change most const  values with the custom dict as well

{% content-ref url="changing-const.md" %}
[changing-const.md](changing-const.md)
{% endcontent-ref %}

## dynamic-mode-default

\


* This is utilized to sign a request, essential for its authorization. Without this, the request would lack proper authorization and fail.
* Generally, the options remain mostly identical. However, in rare instances, modifying these options might resolve certain issues with authentication

## cache-mode

{% hint style="info" %}
**You can use** \
**--no-cache**&#x20;

\
**If your having major issues with cache**

**Just make sure to set --after manually**
{% endhint %}

The script uses DiskCache, which has different options like SQLite and JSON.&#x20;

For most folks, SQLite works fine, but if you're on a network drive, its performance might not be great. That's when switching to JSON could be a smart move, according to the author\
\


## backend

\
Both aio and httpx can handle downloads and requests. You'd only need to switch if your system doesn't work smoothly with aio.&#x20;

Historically, this has mostly been an issue for Mac users, and even then, only a small group among them.

## downloadbars

whether to show download progress bars or not

Disabling these can improve performance

## appendlog

If set to False, each run will generate a new log. If set to True, logs will be combined into one file per day.



## auto\_resume

{% hint style="info" %}
replaces partfileclean
{% endhint %}

If you set this to false, the script will  delete .part files, and will not be able to auto resume

## sanitize\_text

If set to true,  text content will be sanitized before to database insertion into database
