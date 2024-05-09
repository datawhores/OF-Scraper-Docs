---
description: >-
  These options allow you to fine-tune the program's behavior for specific
  situations. Use them with caution, as they might override default settings or
  introduce unexpected behavior.
---

# Advanced Program Options

### Caching and API Calls

#### -nc, --no-cache

* **Disables:** Reading from and writing to the program's cache.
* **Effect:** Forces the program to make fresh API calls for data, even if it's available in the cache. This can be useful for ensuring you have the latest information but can be slower than using the cache.
* **Default:** `False` (cache is enabled)

#### -nca, --no-api-cache

* **Effect:** Forces the program to make fresh API calls for data, even if it's cached within the current program session. This is different from `--no-cache` which also disables writing to the cache for future use.
* **Default:** `False` (API cache is enabled for the current session)

***

### Configuration Overrides

#### -k, --key-mode \[argument]

* **Overrides:** The key mode setting specified in the configuration file.
* **Possible values:**
  * `auto`: (default) The program automatically determines the appropriate key mode.
  * (List other available modes if applicable)
* **Use case:** You might need this option if the program's automatic key mode detection is not working as expected.
* **Requires Argument:** You must specify the desired key mode after the option (e.g., `-k manual`).

#### -dr, --dynamic-rules \[argument]

* **Overrides:** The `dynamic-rules` setting in the configuration file.
* **Used for:** Signing API requests.
* **Default:** `false` (dynamic rules are disabled)
* **Note:** Use this option cautiously, as it might affect the security of your API interactions.
* **Requires Argument:** You must specify a value for dynamic rules (e.g., `-dr true`).

***

### Additional Options

#### -up, --update-profile

* **Retrieves:** Up-to-date profile information directly from the API, bypassing the cache.
* **Cache Update:** Profile information is typically cached for about a day. Use this option if you need the absolute latest data.

#### -ds, --download-script \[argument]

* **Executes:** A user-defined script after a model is downloaded.
* **Arguments passed to script:** Username, model ID, media JSON, and post JSON (all based on the original API responses, with additional data for convenience).
* **Note:** This option allows for custom post-download processing but requires creating and managing the script separately.
* **Requires Argument:** You must provide the path to your script after the option (e.g., `-ds /path/to/my_script.sh`).
