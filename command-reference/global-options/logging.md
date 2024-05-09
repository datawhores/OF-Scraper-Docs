---
description: >-
  These options allow you to control the level of detail and location for
  program logs.
---

# Logging Options

##

## Log Levels

### -l, --log \[argument]

* **Possible choices:**
  * `OFF`: Disables log output to the log file.
  * `STATS`: Logs only high-level statistics and errors.
  * `LOW`: Logs basic program flow and non-critical errors.
  * `NORMAL` (default): Logs most program activity and errors.
  * `DEBUG`: Logs all program activity and detailed debugging information.
* **Sets:** The verbosity level for the program's log file.

### -dc, --discord \[argument]

* **Possible choices:**
  * `OFF`: Disables log output to Discord.
  * `STATS`: Logs only high-level statistics and errors to Discord.
  * `LOW`: Logs basic program flow and non-critical errors to Discord.
  * `NORMAL`: Logs most program activity and errors to Discord.
  * `DEBUG`: Logs all program activity and detailed debugging information to Discord.
* **Sets:** The verbosity level for logs sent to the Discord channel (if configured).

### -p, --output \[argument]

* **Possible choices:**
  * `PROMPT`: Logs only critical information displayed on the program prompt.
  * `STATS`: Logs only high-level statistics and errors to the console.
  * `LOW`: Logs basic program flow and non-critical errors to the console.
  * `NORMAL` (default): Logs most program activity and errors to the console.
  * `DEBUG`: Logs all program activity and detailed debugging information to the console.
* **Sets:** The verbosity level for log messages displayed in the console window.
