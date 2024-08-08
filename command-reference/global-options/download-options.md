---
description: These options allow you to fine-tune how the program handles downloads.
---

# Download Options

## Download Configuration Overrides

{% hint style="info" %}
**For threads and sems**
{% endhint %}

{% content-ref url="../../getting-started/config-options/performance-options/values-to-pick.md" %}
[values-to-pick.md](../../getting-started/config-options/performance-options/values-to-pick.md)
{% endcontent-ref %}

### -db, --download-bars

* **Overrides:** The `downloadbars` setting in the configuration file
* **Default:** `None`

### -sd, --download-sems \[argument]

* **Overrides:** The `download_sems` setting in the configuration file. This setting controls the number of concurrent download processes.
* **Default:** `None` (uses default value from configuration file)

### -dt, --download-threads \[argument]

* **Overrides:** The `threads_count` setting in the configuration file. This setting controls the number of threads used within each download process.
* **Special case:** Setting the value to zero forces the program to use the main thread for downloading. The main thread is also used if there aren't enough active downloads to fill the configured number of download threads.
* **Default:** `None` (uses default value from configuration file)

### -dl, --download-limit\[argument]

* **Overrides:** The `download_limit` setting in the configuration file.
* **Limits:** the maximum download speed per thread to the specified number of bytes per second
* **Accepts:** Human-readable size values like "10MB"
* **Default:** No default limit (unlimited download speed).

***

## Download Cleanup

## -ar, --no-auto-resume

* **Disables:** Automatic cleanup of partially downloaded files (".part" files) upon program exit. This includes forced exits (e.g., Ctrl+C).
* **Default:** `false` (automatic cleanup is enabled)

***
