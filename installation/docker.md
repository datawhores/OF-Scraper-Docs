# Docker

## Volumes

{% hint style="warning" %}
**If manually downloading binaries, you'll need to mount the Linux-based binaries from your host system into the container. Refer to the 'Docker Compose' section for examples.**
{% endhint %}

This table outlines the essential volume mounts required for OF-Scraper. Replace `anypath` with the desired absolute path on your **host machine**.

| Host Path           | Container Path                      | Use          | Required |
| ------------------- | ----------------------------------- | ------------ | -------- |
| `anypath` (on host) | `/home/ofscraper/.config/ofscraper` | Store config | True     |
| `anypath` (on host) | `/home/ofscraper/data`              | Data storage | False    |

***

## Docker Run

This section provides the basic `docker run` commands to get OF-Scraper started. Remember to replace `/your/host/config/path/` with the actual path on your host machine where you want to store OF-Scraper's configuration, and `/your/host/data/path/` with where you want to store downloaded content. Replace `{args}` with your desired OF-Scraper commands (e.g., `ofscraper --username myonlyfans`)

### Minimal `docker run` Command

This command uses the container's default user and group settings (`ofscraper` user with UID/GID `1000`).

Bas

```
docker run -it --rm --name=ofscraper \
  -v /your/host/config/path/:/home/ofscraper/.config/ofscraper/ \
  -v /your/host/data/path/:/home/ofscraper/data \
  ghcr.io/datawhores/of-scraper:main ofscraper {args}
```

#### Using Optional Environment Variables

For better permission management, especially when dealing with mounted volumes, it is **highly recommended** to set the `USER_ID` and `GROUP_ID` to match your host system's user. You can also customize the `USER_NAME` and `GROUP_NAME`.

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

####

## Environment Variables

The container's entrypoint script uses the following environment variables to dynamically create a user and group inside the container. This is crucial for matching permissions between the container and your host system, especially for files on mounted volumes.

| **Environment Variable** | **Default Value (if not set)** | **Purpose & Effect of Changing the Value**                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------ | ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `USER_NAME`              | `ofscraper`                    | **Purpose:** Defines the **name** of the user created inside the container (e.g., `ofscraper`). This is mainly for logical identification and setting the home directory path (`/home/ofscraper` by default). \&lt;br>**Effect of Change:** If you set `USER_NAME=youruser`, a user named `youruser` will be created in the container, with their home directory at `/home/youruser`. This name is also used when dropping root privileges.                                            |
| `USER_ID`                | `1000`                         | **Purpose:** Sets the **numeric User ID (UID)** for the user created in the container. This is vital for matching file ownership on **mounted volumes** with your host user. \&lt;br>**Effect of Change:** Setting `USER_ID=$(id -u)` (highly recommended) makes the container's user have the _same UID as your host user_. This ensures files created on shared volumes are correctly owned by you on the host. Changing it to a different number might cause permission mismatches. |
| `GROUP_ID`               | `1000`                         | **Purpose:** Sets the **numeric Primary Group ID (GID)** for the group created in the container. This works with `USER_ID` to manage correct **group ownership** for files on **mounted volumes**. \&lt;br>**Effect of Change:** Setting `GROUP_ID=$(id -g)` (highly recommended) makes the container's user part of a group with the _same GID as your host's primary group_. Changing it could lead to permission issues on shared volumes if it doesn't match your host's GID.      |
| `GROUP_NAME`             | Defaults to `USER_NAME`        | **Purpose:** Defines the **name** of the primary group created for the user in the container. \&lt;br>**Effect of Change:** By default, the group will share the same name as `USER_NAME` (e.g., `ofscraper`). If you explicitly set `GROUP_NAME=mygroup`, the user will be added to a group named `mygroup` instead. This is less common unless you have specific group naming conventions.                                                                                           |

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

**All officially released OF-Scraper Docker images already include `ffmpeg` built-in.**

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

{% hint style="warning" %}
Modifying the Dockerfile requires you to clone the OF-Scraper repository and understand its build process. Ensure that any added Python dependencies are compatible with the container's environment and the existing OF-Scraper codebase.
{% endhint %}









## Releases

{% embed url="https://hub.docker.com/r/datawhores/of-scraper" %}
Images on Docker.com
{% endembed %}

{% embed url="https://github.com/datawhores/OF-Scraper/pkgs/container/of-scraper/" %}
Images on ghcr.io
{% endembed %}

## Tags

This table explains the different image tags you can use to pull specific versions or builds of the OF-Scraper Docker image.

| **Syntax**           | **Example**    | **What it is**                       |
| -------------------- | -------------- | ------------------------------------ |
| `latest`             | `latest`       | Get the latest stable release        |
| `branch-commitshort` | `main-9e54ed3` | Container for a specific commit      |
| `branch`             | `main`         | Latest commits for a specific branch |
| `version number`     | `2.4.3`        | Specific stable release              |

####
