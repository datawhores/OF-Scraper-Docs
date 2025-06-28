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



**Default Values:** All environment variables keys are listed in the `ofscraper/utils/env/values` folder. This folder contains separate folders/files for different types of values

#### Configuration Precedence

When determining the final value for any configuration setting, the program follows a specific order of precedence. Items higher on this list will **override** items lower on the list:

***

1. Explicit `.env` File (`--env-file` option): Values loaded from the `.env` file(s) specified by the `--env-file` option. If this option is provided multiple times on the command line (e.g., `cli --env-file a.env --env-file b.env`), all specified files are loaded in the order they are declared in the command. Values from files loaded later will take precedence over those from files loaded earlier. These values also override any conflicting values from earlier source.
2. Automatic `.env` File (via `load_dotenv`): Values loaded from a default `.env` file. This is typically initiated by a function call within the application's source code (e.g., `load_dotenv()`). The function searches for the file starting in the current working directory, then moves up through parent directories until it is found.
3. System Environment Variables: Values already set in your operating system's environment (e.g., via `export VAR=VALUE` on Linux/macOS, or `set VAR=VALUE` on Windows Command Prompt). These are present before any `.env` files are loaded.
4. Hardcoded Defaults: Default values defined directly within the program's source code. These are used only if a setting is not found via any of the above methods.

