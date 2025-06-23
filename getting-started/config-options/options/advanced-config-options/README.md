# Advanced config options



***

## dynamic-mode-default

* This is utilized to sign a request, essential for its authorization. Without this, the request would lack proper authorization and fail.
* Generally, the options remain mostly identical. However, in rare instances, modifying these options might resolve certain issues with authentication



***

## cache-mode

{% hint style="info" %}
**You can use** \
**--no-cache**&#x20;

**or** \
**--no-cache-api**

\
**If your having major issues with cache**
{% endhint %}

{% hint style="info" %}
**Options**\
**JSON**\
**SQLITE**\
**None (to disable)**
{% endhint %}

The script uses DiskCache, which has different options like SQLite and JSON.&#x20;

For most folks, SQLite works fine, but if you're on a network drive, its performance might not be great. That's when switching to JSON could be a smart move, according to the author

{% embed url="https://grantjenks.com/docs/diskcache/tutorial.html#caveats" %}

***

## rotate\_logs

If set to True, each run will generate a new log. If set to False, each logs will be combined into one file per day.

## sanitize\_text

If set to true,  text content will be sanitized before to database insertion into database

## downloadbars

whether to show download progress bars or not

Disabling these can improve performance



***

## temp\_dir

{% hint style="info" %}
**If not set the the final download directory is used to hold temp files**
{% endhint %}

This overrides the temporary directory used during download\


## infinite\_loop\_action\_mode

{% hint style="info" %}
**You can disable the prompt for continuing the script with any arguments by setting the const value**\
\
**CONTINUE\_BOOL = False**
{% endhint %}

Sets the script to run in a infinite loop even when \
\--action is used



## logs\_expire\_time

&#x20;Determines the maximum age for log files in days. When log rotation is enabled, any log file older than this configured value will be automatically deleted from the system. For this feature to be active, the value must be set to a positive number greater than zero, and rotate\_logs must be enabled



***

## ssl\_validation:

Disable validation of ssl certificates

***

## enable\_auto\_after

* dynamically sets after if enabled
  1. after is set to zero for the first run following that --after was used previously and has been removed in a future run
  2. dynamically sets after based on db status
* if disabled after is is set based on --after only
  1. if --after is None, then after will be set as 0

***

## remove\_hash\_match

{% hint style="info" %}
**Set value to None to disable calculating hash, False will calculate but not remove files**
{% endhint %}

{% hint style="info" %}
**hashes are 128 bit and matched with file sizes to ensure uniqueness**
{% endhint %}



If at least two files with identical hashes exist on the system, remove duplicate files identified by those hashes, keeping only one copy on the file system



***

{% hint style="info" %}
**ofscraper.main or main are the default built in key words for a list combining active and expired list**
{% endhint %}

{% hint style="info" %}
**ofscraper.active or active are  the default built in key words for active list**
{% endhint %}

{% hint style="info" %}
**ofscraper.expired or expired are the default built in key words for expired list**
{% endhint %}

## default\_user\_list

{% hint style="info" %}
**If blank then ofscraper.main is used as setting**
{% endhint %}

The default user list used during username scan

## default\_black\_list

{% hint style="info" %}
**If  blank then the black list option is disabled**
{% endhint %}

The default black list used during username scan



## custom\_values

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

Therefore, maintaining the inner quotes is vital for accurate interpretation by 'eval'

### Changing const

You can change most const  values with the custom dict as well

## code-execution

```
The 'code-execution' feature enables code execution during the 
generation of metadata, path, file_format, and dir_format.
```

\
All available placeholders can be used within these options, and the input for these choices will be transformed into an f-string for processing.\


As an example

```
eval("f'{}'".format(config_.get_dirformat(config_.read_config())))
```

in this example any Python code that produces a string as its output should work
