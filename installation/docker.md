# Docker

## Volumes

{% hint style="warning" %}
**If manually downloading binaries, you'll need to mount the Linux-based binaries from your host system into the container. Refer to the 'Docker Compose' section for examples.**
{% endhint %}

| Mount Point     | Purpose                                                                                                                         | Typical Default Location                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| **APP\_HOME**   | The **home directory** for your application's user inside the container. This often serves as the base for other default paths. | `/home/<APP_USER>` (e.g., `/home/ofscraper`)          |
| **DATA\_DIR**   | Where the application stores its **persistent data files**, such as databases, downloaded content, or user-generated media.     | `$APP_HOME/data` (e.g., `/home/ofscraper/data`)       |
| **CONFIG\_DIR** | Where the application stores its **configuration files** and settings.                                                          | `$APP_HOME/.config` (e.g., `/home/ofscraper/.config`) |

### CONFIG\_DIR

The `CONFIG_DIR` is where OF-Scrapers configuration files will be stored. It will prioritizes any explicit setting by the user

| Scenario               | `CONFIG_DIR` Environment Variable        | `APP_HOME` Value (Example) | `CONFIG_DIR` Final Path   | Explanation                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------- | -------------------------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Explicitly Set**  | `CONFIG_DIR=/app/onfig/`                 | `/home/ofscraper`          | `/app/config`             | If you explicitly provide the `CONFIG_DIR` environment variable, its value is used directly. This overrides any default behavior.                                                                                               |
| **2. Not Set / Empty** | `CONFIG_DIR` is unset or `CONFIG_DIR=""` | `/home/ofscraper`          | `/home/ofscraper/.config` | <p>If <code>CONFIG_DIR</code> is not provided (or provided as an empty string), it defaults to a hidden <code>.config</code> directory within the determined <code>APP_HOME</code>.   </p><p>or users <br><code>Home</code></p> |



### DATA\_DIR

The `DATA_DIR` is where your application will store its persistent data. Similar to `CONFIG_DIR`, it will respects user overrides.

| Scenario               | `DATA_DIR` Environment Variable      | `APP_HOME` Value (Example) | `DATA_DIR` Final Path  | Explanation                                                                                                                       |
| ---------------------- | ------------------------------------ | -------------------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **1. Explicitly Set**  | `DATA_DIR=/app/data`                 | `/home/ofscraper`          | `/app/data`            | If you explicitly provide the `DATA_DIR` environment variable, its value is used directly, overriding any default.                |
| **2. Not Set / Empty** | `DATA_DIR` is unset or `DATA_DIR=""` | `/home/ofscraper`          | `/home/ofscraper/data` | If `DATA_DIR` is not provided (or provided as an empty string), it defaults to a `data` directory within the determined `APP_HOM` |

### Home Folder

{% hint style="danger" %}
**If you do&#x20;**_**not**_**&#x20;explicitly set the `HOME_FOLDER` environment variable, the script's default behavior is to make the home directory name match the adapted `APP_USER` name. For instance, if `APP_USER` was initially `ofscraper` but gets adapted to an existing user like `nginx` (due to a UID conflict), the `APP_HOME`  folder will dynamically change to `/home/nginx`. This keeps the user's name and home folder consistent within the container's `/etc/passwd` file.**
{% endhint %}

| Scenario     | `HOME_FOLDER` Environment Variable Status | `APP_USER` Adaptation (e.g., from `ofscraper` to `nginx`) | Resulting `APP_HOME` Directory Path in Container (`/etc/passwd`) | Explanation                                                                                                                                                                                                                                   |
| ------------ | ----------------------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Default**  | **Not set** (or empty string)             | **Yes**, `APP_USER` changes                               | `/home/nginx` (dynamically matches new `APP_USER`)               | When `HOME_FOLDER` isn't specified, the home directory name **automatically updates** to match the new `APP_USER` name if the user account has to adapt to an existing UID on the host. This keeps the user name and home folder consistent.  |
|              | **Not set** (or empty string)             | **No**, `APP_USER` remains `ofscraper`                    | `/home/ofscraper`                                                | If no `HOME_FOLDER` is set and `APP_USER` doesn't need to change, the home directory defaults to `/home/ofscraper`.                                                                                                                           |
| **Explicit** | **Set** (e.g., `mydata`)                  | **Yes**, `APP_USER` changes                               | `/home/mydata` (remains as explicitly set)                       | If you explicitly define `HOME_FOLDER`, the home directory path **stays fixed** at `/home/mydata`. It will not change, even if `APP_USER` adapts to a different name due to UID/GID conflicts. This provides a stable, predictable home path. |
|              | **Set** (e.g., `mydata`)                  | **No**, `APP_USER` remains `ofscraper`                    | `/home/mydata`                                                   | The explicitly set `HOME_FOLDER` always takes precedence, so the home directory will be `/home/mydata`.                                                                                                                                       |









***

## Environment Variables

The container is managed by a entrypoint script that automatically creates a non-root user to run the application.&#x20;

You can control the user, group, paths, and script behavior using the environment variables below.

### User and Group Identity

These variables control the identity of the user that runs the application inside the container.

For the best experience with mounted volumes, it is **highly recommended** to set `UID` and `GID` to match your host system's user (e.g., `-e UID=$(id -u) -e GID=$(id -g)`).

| **Environment Variable** | **Default Value (if not set)** | **Purpose & Effect of Changing the Value**                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------ | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `UID`                    | `1000`                         | Sets the **numeric User ID (UID)** for the application user, which is critical for matching file ownership on mounted volumes. Setting `UID=$(id -u)` makes the container user have the _same UID as your host user_, ensuring files it creates are correctly owned by you on the host. if the UID already exists with a different username in the container, it will adapt and use that existing user.     |
| `GID`                    | `1000`                         | Sets the **numeric Group ID (GID)** for the application user's primary group, which works with `UID` to manage correct group ownership. Setting `GID=$(id -g)` ensures file permissions align with your host's primary group. Similar to `UID`, the script will adapt if this GID already belongs to an existing group.                                                                                     |
| `USERNAME`               | `ofscraper`                    | Defines the **name** of the user to be created or managed inside the container. If you set `USERNAME=youruser`, the script will attempt to create or modify a user named `youruser` with the specified `UID`. This name is mainly for logical identification. If the `UID` you provide is already taken by a different user, the script will use that existing user's name instead and print a log message. |
| `GROUPNAME`              | The value of `USERNAME`        | Defines the **name** of the primary group for the application user. By default, the group name will match the username (e.g., `ofscraper`). You can set this explicitly if you have specific group naming conventions. Like `USERNAME`, this is secondary to `GID`.                                                                                                                                         |

### Path and Directory Management

These variables allow you to control where the application stores its files. This is useful for mounting specific host directories.

| **Environment Variable** | **Default Value (if not set)** | **Purpose & Effect of Changing the Value**                                                                                                                                                                                                                                                            |
| ------------------------ | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `HOME_FOLDER`            | The value of `USERNAME`        | Sets the **folder name** for the user's home directory inside the container's `/home/` directory. If you set `USERNAME=john` and leave this unset, the home directory will be `/home/john`. If you set `HOME_FOLDER=my_app`, the home directory becomes `/home/my_app`, regardless of the `USERNAME`. |
| `DATA_DIR`               | `$APP_HOME/data`               | Overrides the path for the application's data directory. By default, data is stored in a `data` folder inside the user's home directory (e.g., `/home/ofscraper/data`). You can set this to any absolute path, such as `/data`, if you prefer to mount a volume directly to `/data`.                  |
| `CONFIG_DIR`             | `$APP_HOME/.config`            | Overrides the path for the application's configuration directory. By default, configuration is stored in a hidden `.config` folder inside the user's home directory (e.g., `/home/ofscraper/.config`). You can set this to an absolute path like `/config` to mount a volume there instead.           |

### Script Behavior Flags

These variables act as on/off switches to control specific actions within the entrypoint script.

| **Environment Variable** | **Default Value (if not set)** | **Purpose & Effect of Changing the Value**                                                                                                                                                                                                                                                              |
| ------------------------ | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `KEEP_PERM`              | `false`                        | Prevents the script from changing ownership of the home, data, and config directories. If you set `KEEP_PERM=true`, the script will **not** run `chown` on your mounted directories. This is useful for advanced setups like rootless Docker or when you are managing permissions manually on the host. |
| `SKIP_FFMPEG`            | `false`                        | Controls the installation of the `pyffmpeg` Python package. If you set `SKIP_FFMPEG=true`, the script will not attempt to install the `pyffmpeg` package. This can be used to speed up container startup if you do not need its functionality or if the installation is causing issues.                 |

***

## Docker Run

This section provides the basic `docker run` commands to get OF-Scraper started. Remember to replace `/your/host/config/path/` with the actual path on your host machine where you want to store OF-Scraper's configuration, and `/your/host/data/path/` with where you want to store downloaded content. Replace `{args}` with your desired OF-Scraper commands (e.g., `ofscraper --username myonlyfans`)

### Minimal `docker run` Command

This command uses the container's default user and group settings (`ofscraper` user with UID/GID `1000`).

```
docker run -it --rm --name=ofscraper \
  -v /your/host/config/path/:/home/ofscraper/.config/ofscraper/ \
  -v /your/host/data/path/:/home/ofscraper/data \
  ghcr.io/datawhores/of-scraper:main ofscraper {args}
```

#### Using Optional Environment Variables

To pass these optional variables, add them to your `docker run` command using the `-e` flag:

Bash

```
docker run -it --rm --name=ofscraper \
  -v /your/host/config/path/:/home/ofscraper/.config/ofscraper/ \
  -v /your/host/data/path/:/home/ofscraper/data \
  -e USER_NAME=youruser \
  -e USER_ID=$(id -u) \
  -e GROUP_ID=$(id -g) \
  -e GROUP_NAME=yourgroup \ # Optional: Only if you want a custom group name different from USER_NAME
  ghcr.io/datawhores/of-scraper:main ofscraper {args}
```

***

## Docker Compose

For more complex setups or for defining your service persistently, use Docker Compose. Remember to install `ffmpeg` and `mp4decrypt` on your local system if you choose to mount them from the host.

```
version: "3.8" # Recommended to use a recent version for new features
services:
  of-scraper:
    stdin_open: true # Keeps STDIN open for interactive processes
    tty: true # Allocates a pseudo-TTY for a terminal-like interface
    container_name: ofscraper
    
    environment: # Optional environment variables
      # These are recommended for correct file permissions on mounted volumes.
      # Default UID/GID is 1000:1000 if not specified via environment variables in your shell.
      # - USER_NAME=ofscraper   # Defaults to 'ofscraper' in the entrypoint script
      # - USER_ID=${USER_ID}   # Host user's UID (e.g., set via 'export USER_ID=$(id -u)' on host)
      # - GROUP_ID=${GROUP_ID} # Host user's GID (e.g., set via 'export GROUP_ID=$(id -g)' on host)
      # - GROUP_NAME=mygroup # Optional: If you want a custom group name different from USER_NAME
    volumes:
      # Mount your configuration directory (replace ./config/ with your host path)
      - ./config/:/home/ofscraper/.config/ofscraper/
      # Mount your data storage directory (replace ./data/ with your host path)
      - ./data/:/home/ofscraper/data/
      # Optional: Mount pre-installed binaries from host (adjust paths as needed)
      # - /usr/bin/ffmpeg:/usr/bin/ffmpeg

    image: ghcr.io/datawhores/of-scraper:main 
    # --- COMMAND OPTIONS ---
    # Choose one of the following 'command' configurations based on your use case.
    # Uncomment the desired option and ensure others are commented out.

    # Option 1: For interactive use (recommended if you frequently run commands manually)
    # This keeps the container running indefinitely in the background.
    command: ["/bin/bash", "-c", "sleep infinity"]
    # To bring the container up: `docker compose up -d`
    # Then, to run commands inside it: `docker compose exec -it ofscraper ofscraper {args}`
    # Example: `docker compose exec -it ofscraper ofscraper --username myuser`

    # Option 2: To run the scraper automatically with specific arguments when the container starts
    # Uncomment the line below and comment out Option 1 above.
    # command: "ofscraper --username ALL --posts all"

    # Optional: Configure restart policy.
    # restart: "unless-stopped" # Ensures the container restarts automatically unless explicitly stopped.
```

***

### Interactive Use

If you've set up your `docker-compose.yml` for interactive use (by using `command: ["/bin/bash", "-c", "sleep infinity"]` or similar), you'll start the container in the background and then execute commands inside it.

To run the scraper manually (after bringing the service up with `docker compose up -d` to start it in detached mode), use:

Bash

```
docker compose exec -it ofscraper ofscraper {args}
```

Replace `{args}` with your desired OF-Scraper commands, for example: `docker compose exec -it ofscraper ofscraper --username myuser --posts all`.

***

## Building Custom Images

{% hint style="info" %}
**All officially released OF-Scraper Docker images already include `ffmpeg` built-in.**
{% endhint %}

This section is **only relevant if you are building the OF-Scraper Docker image locally from source**, for instance, to include specific Python dependencies or to customize the build process. You can use `docker buildx` for this.

### Using `INSTALL_FFMPEG` Build Argument

The OF-Scraper `Dockerfile` includes an `ARG` (build argument) named `INSTALL_FFMPEG`. When set to `true` during a local build, this argument triggers the installation of the `pyffmpeg` Python package, which in turn includes and manages its own `ffmpeg` binary within the container.

To build an image locally where `pyffmpeg` (and thus `ffmpeg`) is included, you would pass `INSTALL_FFMPEG=true` to your `docker buildx` command:

```
# Optional: Create a builder instance for multi-platform builds (recommended for cross-platform compatibility)
# docker buildx create --name mybuilder --use

# Navigate to the directory containing your Dockerfile (e.g., your cloned OF-Scraper repository)
# cd /path/to/OF-Scraper/repository

# Build the image, specifying the build-arg
docker buildx build --platform linux/amd64,linux/arm64 \
  --build-arg INSTALL_FFMPEG=true \
  -t my-ofscraper-image:latest \
```

{% hint style="info" %}
**Benefit of built-in FFmpeg:** If your image was built with `INSTALL_FFMPEG=true` (or if you're using an official released image that already includes FFmpeg), the image is self-contained. This means you generally **do not need to install `ffmpeg` on your host system or mount it into your Docker container**
{% endhint %}



***

## Releases

{% embed url="https://hub.docker.com/r/datawhores/of-scraper" %}
Images on Docker.com
{% endembed %}

{% embed url="https://github.com/datawhores/OF-Scraper/pkgs/container/of-scraper/" %}
Images on ghcr.io
{% endembed %}

***

## Tags

This table explains the different image tags you can use to pull specific versions or builds of the OF-Scraper Docker image.

| **Syntax**           | **Example**    | **What it is**                        |
| -------------------- | -------------- | ------------------------------------- |
| `latest`             | `latest`       | Get the latest commit from any branch |
| `stable`             | `stable`       | the latest stable release             |
| `dev`                | `dev`          | the latest development release        |
| `branch-commitshort` | `main-9e54ed3` | Container for a specific commit       |
| `branch`             | `main`         | Latest commits for a specific branch  |
| `version number`     | `2.4.3`        | Specific stable release               |

