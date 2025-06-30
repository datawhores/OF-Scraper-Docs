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

***

## env\_files

list of files imported to set custom enviroment variables for the script
