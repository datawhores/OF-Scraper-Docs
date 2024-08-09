---
description: >-
  These options allow you to fine-tune the program's behavior for specific
  situations. Use them with caution, as they might override default settings or
  introduce unexpected behavior.
---

# Advanced Program Options

## Caching and API Calls

### -nc, --no-cache

* **Disables:** Reading from and writing to the program's cache.
* **Effect:** Disables all uses of cache including\
  For example cache is used to store keys and file sizes\
  \
  Also forces the program to make fresh sequential API calls for data, even if it's available in the cache. This can be useful for ensuring you have the latest information but can be slower than using the cache
* **Default:** `False` (cache is enabled)

### -nca, --no-api-cache

* **Effect:** Forces the program to make sequential  API calls for data, even if it's cached within the current program session. This is different from `--no-cache` which is for all uses of the cache library beyond just OF API request
* **Default:** `False` (API cache is enabled for the current session)

***

## Configuration Overrides

### -k, --key-mode \[argument]

* **Overrides:** The key mode setting specified in the configuration file.
* **Possible values:**
  * cdrm
  * cdrm2
  * keydb
  * manual
* **Requires Argument:** You must specify the desired key mode after the option (e.g., `-k manual`).

### -dr, --dynamic-rules \[argument]

* **Overrides:** The `dynamic-rules` setting in the configuration file.
* **Used for:** Signing API requests.
* **Default:** `false` (dynamic rules are disabled)
* **Possible values:**
  * sneaky
  * digital
  * deviint
* **Requires Argument:** You must specify a value for dynamic rules (e.g., `-dr sneaky`)
* **Note:** Possible values may change based on removal of sources, frequency of updates of sources

***

## Additional Options

### -up, --update-profile

* **Retrieves:** Up-to-date profile information directly from the API, bypassing the cache.
* **Cache Update:** Profile information is typically cached for about a day. Use this option if you need the absolute latest data.

### -ds, --download-script \[argument]

*   **Executes:** A user-defined script after each model is processed

    * runs after each model is downloaded in the main scraper
    * runs after each model's metadata is processed in metadata mode
    * runs after each model is processed in manual mode
    * runs for each unique model, after the current cart is downloaded in check mode


* **Arguments passed to script:**  all based on the original API responses, with additional data for convenience\
  \
  in the form of a json file
  * <pre><code><strong>username:username
    </strong></code></pre>
  * ```
    model_id:model_id
    ```
  * ```
    media:media dictionary from api, with final_path added
    ```
  * ```
    posts:posts dictionary from api
    ```
  * ```
    userdata:a dictionary from users api
    ```









* **Note:** This option allows for custom post-download processing but requires creating and managing the script separately.
* **Requires Argument:** You must provide the path to your script after the option \
  (e.g., `-ds /path/to/my_script.sh`)



### -ps, --post-script \[argument]

* **Executes:** A user-defined script once the script finishes an action&#x20;
  * once all models are downloaded or liked in scrape mode
  * once all the post from manual mode are completed
  * After the current cart downloads are processed in check mode, and after the download-script is processed for each user
  * after all metadata for  all users is processed in metadata mode&#x20;
*   **Arguments passed to script:** a single json with the following



    * <pre><code><strong>users:A dictionary of user dictionaries retrieved from the user API
      </strong></code></pre>
    * ```
      dir_format:string from  config
      ```
    * ```
      file_format:string from  config
      ```
    * ```
      metadata":string from  config
      ```


* **Note:** This option allows for custom post-script processing but requires creating and managing the script separately.
* **Requires Argument:** You must provide the path to your script after the option \
  (e.g., `-ps /path/to/my_script.sh`)
