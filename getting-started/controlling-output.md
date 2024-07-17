---
description: various options for output
---

# Controlling Output/Logs

***

## Log Streams

### Discord

{% hint style="info" %}
**Discord logs will solely contain the log message, whereas other logs will include additional details like function calls and line numbers.**
{% endhint %}

{% hint style="info" %}
**You can turn the const value 'DISCORD\_ASYNC' to true to spend up discord logs**\
**This could result in logs not being in order**
{% endhint %}

{% hint style="info" %}
**For optimal performance with Discord, it's recommended to use the Normal or below logging level. Levels like Debug generate a significant amount of data, requiring numerous requests to process and log**
{% endhint %}

The output goes to the Discord channel

#### LEVELS

_In ascending output order_

* OFF
* LOW
* NORMAL
* DEBUG
* TRACE

***

### Output

**output to the console**

{% hint style="info" %}
**For clear console output, it is recommended to set the logging level to Normal or below to avoid excessive messages**
{% endhint %}

#### LEVELS

_In ascending output order_

* PROMPT
* LOW
* NORMAL
* DEBUG
* TRACE

***

### Log

**output to logfile within the config folder**

_In ascending output order_

* OFF
* LOW
* NORMAL
* DEBUG
* TRACE

Deprecated

* STAT

***

## Log levels details

With the 1.9 release, you gain increased control over the output level.

**OFF**

```

This feature allows you to deactivate Discord or log file logging. 
By default, these outputs are turned off.
```

**PROMPT**

```

The program needs prompts and specific console output for certain operations. 
It configures console output to only show necessary information. 
Providing a scraping action and usernames should largely disable most,
 if not all, additional output.
```

**LOW**

```

It disables all progress bars and displays essential program status while running. 
It also includes avatars and applies to all output destinations.
```

**STATS**

{% hint style="info" %}
**Removed in 3.5**
{% endhint %}

```

Slight modification to LOW no avatars will be shown

```

**NORMAL**.

```
The default console output level, progress bars
 and general status messages are displayed. 
 All output destinations, including Discord and log files, 
 receive general status messages but exclude progress bars.
```

**DEBUG**

```
It includes debugger messages and tracebacks within the 
'Normal' output level. 
This applies to all output destinations.

```

**TRACE**

```

This mode provides the most detailed and extensive 
information compared to all other modes.
```
