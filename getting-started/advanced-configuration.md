# Advanced Configuration



Environment variables are a way for advanced users to have more control over certain aspects of the program



**Default Values:** All environment variables keys are listed in the `ofscraper/utils/of_env/values` folder. This folder contains separate folders/files for different types of value

#### Configuration Precedence

When determining the final value for any configuration setting, the program follows a specific order of precedence. Items higher on this list will **override** items lower on the list:

***

1. Explicit `.env` File (`--env-file` option): Values loaded from the `.env` file(s) specified by the `--env-file` option. If this option is provided multiple times on the command line (e.g., `cli --env-file a.env --env-file b.env`), all specified files are loaded in the order they are declared in the command. Values from files loaded later will take precedence over those from files loaded earlier. These values also override any conflicting values from earlier source.
2. Automatic `.env` File (via `load_dotenv`): Values loaded from a default `.env` file. This is typically initiated by a function call within the application's source code (e.g., `load_dotenv()`). The function searches for the file starting in the current working directory, then moves up through parent directories until it is found.
3. System Environment Variables: Values already set in your operating system's environment (e.g., via `export VAR=VALUE` on Linux/macOS, or `set VAR=VALUE` on Windows Command Prompt). These are present before any `.env` files are loaded.
4. Hardcoded Defaults: Default values defined directly within the program's source code. These are used only if a setting is not found via any of the above methods.
