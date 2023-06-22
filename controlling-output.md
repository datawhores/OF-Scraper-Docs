---
description: various options for output
---

# Controlling Output

## Output Streams

### Discord

outputs to discord channel

#### LEVELS

* OFF
* STATS
* LOW
* NORMAL
* DEBUG

### Output

output to the console

#### LEVELS

* PROMPT
* LOW
* NORMAL
* DEBUG

### Log

output to logfile within the config folder

* OFF
* LOW
* NORMAL
* DEBUG

## Output LEVEL

With the release of 1.9 you now have more control over the level of output

**OFF**

```
This can be used to turn discord or log file logging off

These outputs are disabled by default
```

**PROMPT**

```
prompts and some output to the console is required to run the program in certain cases.
This sets the console output to strictly what is required. Passing a scraping action and usernames should disable most if not all output
```

**LOW**

```
Turns off all progress bars 
Shows barebones information about the status of the program as it is running
Also shows avatars
Available for all output destinations
```

**STATS**

```

Slight modification to LOW no avatars will be shown

```

**NORMAL**

```
This is the default level of output to the console
Progress bars will be shown in console, along with all general status messages

Available for all output destinations
discord and log file will receive all general status messages, but not progress bars

```

**DEBUG**

```
Adds debugger messages and tracebacks to 'Normal'
Available for all output destinations

```
