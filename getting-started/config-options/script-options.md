# Script Options

{% content-ref url="../../using-the-scraper/recipes/scripts.md" %}
[scripts.md](../../using-the-scraper/recipes/scripts.md)
{% endcontent-ref %}

## Post Action Script (`post_download_script`)

A script that runs after an action for a user has completed. This script can be configured via the `--after-action-script` command-line argument or the `after_action_script` setting in the program's configuration.

### **Trigger Conditions**

* Runs after each model is downloaded in the main scraper
  * Including in daemon-mode
* Runs after each model like/unlike process is finished
  * Including in daemon-mode
* Runs after each model's metadata is processed in metadata mode.
* Runs after each model is processed in manual mode
* Runs for each unique model, after the current cart is downloaded in check mode
* Runs for each model after scrape paid is process,
  * Note: modeldeleted or models without a active account would be ran together as one unit

### **Data Sent**

As a JSON dictionary, typically via standard input (stdin).

* `username`: username (string)
* `action` : action ran (string)
* `model_id`: model\_id (integer).
* `media`: media dictionary from API, with `final_path` added, and whether they were downloaded or not
* `posts`: posts dictionary from API.
* `userdata`: a dictionary from the users API.

***

## Post Script (`post_script`)

A script that runs after all actions for all users have completed. This script can be configured via the `--post-script` command-line argument or the `post_script` setting in the program's configuration.

### **Trigger Conditions**

* Once all models are downloaded or liked in scrape mode
* After each cycle in daemon mode
* Once all the posts from manual mode are completed
* After the current cart downloads are processed in check mode, and after the download\_action\_script is processed for each user.
* After all metadata for all users is processed in metadata mode.

### **Data Sent**

As a JSON dictionary, typically via standard input (stdin).

* `like_processed`: A list of users who have successfully completed the 'like' action.
* `like_unprocessed`: A list of users who are queued for the 'like' action but were not  processed.
* `unlike_processed`: A list of users who have successfully completed the 'unlike' action.
* `unlike_unprocessed`: A list of users who are queued for the 'unlike' action but were not processed.
* `download_processed`: A list of users whose content has been successfully downloaded.
* `download_unprocessed`: A list of users whose content is queued for download but were not processed.
* `scrape_paid_processed`: A list of users who were successfully processed during the 'scrape\_paid' action
* `scrape_paid_unprocessed`: A list of users who are queued for the 'scrape\_paid' scrape action but but were not processed.

***

## Naming Script (`naming_script`)

A script that dynamically generates the final filename or full path for a downloaded media item. This script can be configured via the `--naming-script` command-line argument or the `naming_script` setting in the program's configuration.

### **Trigger Conditions**

* For each individual media item, this script runs while its temporary filename is being generated.
* It is executed again after the temporary file has been downloaded, and before the file is renamed to its final destination.
* **As a special case, the script also runs before generating filenames for text files when using the `--text` or `--text-only` option.**

### **Data Sent**

As a JSON dictionary, typically via standard input (stdin)

* `media`: A dictionary representing the media item
* `post`: The dictionary representing the post associated with the media item.
* `dir`: The calculated directory path (string).
* `file`: The calculated filename (string).
* `dir_format`: The current directory format string (string from config).
* `file_format`: The current file format string (string from config).
* `metadata`: The current metadata format setting (string from config).
* `username`: The model's username (string).
* `model_id`: The model's ID (integer).
* `post_id`: The ID of the post associated with the media (integer).
* `media_id`: The ID of the media item (integer).
* `media_type`: The type of media
* `value`: The value associated with the media
* `date`: The formatted date related to the media/post (string)
* `response_type`: The response type of the media (string).
* `label`: A string representing associated labels
* `download_type`: The type of download

### **Expected Output**

The script is expected to print the desired the **full desired path** to standard output (stdout). The scraper will then use this output to rename or move the downloaded file

***

## After Download Script (`download_skip_script`)

A script that runs after a download has completed. This script can be configured via the `--after-download-script` command-line argument or the `after_download_script` setting in the program's configuration.

### **Trigger Conditions**

* It executes after a download has successfully been downloaded

### **Data Sent**

a single string

* The final filepath of the download

***

## Download Skip Script (`download_skip_script`)

A script that determines whether to skip or continue a download. This script can be configured via the `--download-skip-script` command-line argument or the `download_skip_script` setting in the program's configuration.

### **Trigger Conditions**

* It executes before the download process begins for each individual media item.

### **Data Sent**

As a JSON dictionary, typically via standard input (stdin).

* `username`: The model's username (string).
* `model_id`: The model's ID (integer).
* `post_id`: The ID of the post associated with the media (integer).
* `media_id`: The ID of the media item (integer).
* `media`: dictionary representing the media item to be downloaded.
* `post`: A dictionary representing the post associated with the media item.
* `total_size`: The total size of the download in bytes (integer).

### **Expected Output**

The script is expected to return a string via standard output (stdout).

* If the returned string is `"False"` (case-insensitive) or an empty string, the download will be **skipped**.
* Any other non-empty string returned will allow the download to **proceed**.







