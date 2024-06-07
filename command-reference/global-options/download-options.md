---
description: These options allow you to fine-tune how the program handles downloads.
---

# Download Options

## Download Configuration Overrides

### -db, --download-bars

* **Overrides:** The `download-bars` setting in the configuration file
* **Default:** `None`

### -sd, --download-sems \[argument]

* **Overrides:** The `download-sems` setting in the configuration file. This setting controls the number of concurrent download processes.
* **Default:** `None` (uses default value from configuration file)

### -dt, --download-threads \[argument]

* **Overrides:** The `download-threads` setting in the configuration file. This setting controls the number of threads used within each download process.
* **Special case:** Setting the value to zero forces the program to use the main thread for downloading. The main thread is also used if there aren't enough active downloads to fill the configured number of download threads.
* **Default:** `None` (uses default value from configuration file)

***

## Download Cleanup

## -ar, --no-auto-resume

* **Disables:** Automatic cleanup of partially downloaded files (".part" files) upon program exit. This includes forced exits (e.g., Ctrl+C).
* **Default:** `false` (automatic cleanup is enabled)

***
