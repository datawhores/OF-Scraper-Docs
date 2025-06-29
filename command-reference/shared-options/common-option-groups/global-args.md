---
description: These options allow you to configure various aspects of the program's behavior
---

# Program Options

## General Options

### -v, --version

* **Displays:** The program's version number and then exits.
* **Example output:** `2.4.5+main.8f998cd` (This might vary depending on the actual version).

### -cg, --config \[argument]&#x20;

* **Controls:** The location of the configuration folder or file.
* **Default behavior:** The program uses the default configuration location
* **Example:** With `-cg /custom/config/path`, the program will look for configuration files in the `/custom/config/path` directory

{% content-ref url="../../../using-the-scraper/batch-scraping-and-bot-actions/advanced-args.md" %}
[advanced-args.md](../../../using-the-scraper/batch-scraping-and-bot-actions/advanced-args.md)
{% endcontent-ref %}

### -r, --profile \[argument] (optional)

* **Specifies:** The name of the profile directory, which stores authentication information&#x20;

&#x20;     This is store in the config location

* **Default behavior:** The program uses the default profile 'main'
* **Example:** With `-r test`, the program will use a profile named test

### --env-file \[path]

* **Specifies:** The path to an external `.env` file from which to load environment variables.
* **Effect:** Variables defined in this file are loaded into the program's environment. Values from this file will **override** system environment variables that might be set. These values are then utilized by various configuration settings that are designed to read from environment variables.
* **Default behavior:** If this option is not provided, the program automatically searches for a `.env` file in the current working directory and its parent directories.
* **Example:** With `--env-file /home/user/my_app/prod.env`, the program will load environment variables from the specified `prod.env` file.

{% content-ref url="../../../getting-started/advanced-configuration.md" %}
[advanced-configuration.md](../../../getting-started/advanced-configuration.md)
{% endcontent-ref %}
