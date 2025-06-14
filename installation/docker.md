# Docker

***

## Volumes

{% hint style="info" %}
**If you opt for the auto download feature when installing mp4decrypt or ffmpeg, the binaries will be stored in /root/.config/ofscraper/bin within the Docker image**
{% endhint %}

{% hint style="info" %}
**If manually downloading binaries please mount the linux based binaries**
{% endhint %}

{% content-ref url="../getting-started/config-options/binaries-options.md" %}
[binaries-options.md](../getting-started/config-options/binaries-options.md)
{% endcontent-ref %}

| host    | docker                            | use          | required |
| ------- | --------------------------------- | ------------ | -------- |
| anypath | /home/ofscraper/.config/ofscraper | store config | True     |
| anypath | anypath                           | data storage | False    |



***

## Docker Run

```
docker run  -it --rm --name=ofscraper -v anypath:/home/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main ofscraper {args}
```



***

## Docker Compose

```
version: "3"
services:
    of-scraper:
        stdin_open: true
        tty: true
        container_name: ofscraper
        volumes:
            - ./config/:/home/ofscraper/.config/
        
        image: ghcr.io/datawhores/of-scraper:main
        command: ofscraper
```



{% hint style="warning" %}
_**Changed**_**&#x20;in version 3.13**
{% endhint %}

You got it! Here's that table formatted in pure Markdown, ready for your documentation.

***

### Docker Container Environment Variables: Configurable User and Group Settings

This table explains the environment variables you can use to customize user and group settings inside your Docker container. These variables work with the container's entrypoint script to dynamically create a user and group that aligns with your host system's permissions.

| **Environment Variable** | **Default Value (if not set)** | **Purpose & Effect of Changing the Value**                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------ | ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `USER_NAME`              | `ofscraper`                    | **Purpose:** Defines the **name** of the user created inside the container (e.g., `ofscraper`). This is mainly for logical identification and setting the home directory path (`/home/ofscraper` by default). \&lt;br>**Effect of Change:** If you set `USER_NAME=youruser`, a user named `youruser` will be created in the container, with their home directory at `/home/youruser`. This name is also used when dropping root privileges.                                            |
| `USER_ID`                | `1000`                         | **Purpose:** Sets the **numeric User ID (UID)** for the user created in the container. This is vital for matching file ownership on **mounted volumes** with your host user. \&lt;br>**Effect of Change:** Setting `USER_ID=$(id -u)` (highly recommended) makes the container's user have the _same UID as your host user_. This ensures files created on shared volumes are correctly owned by you on the host. Changing it to a different number might cause permission mismatches. |
| `GROUP_ID`               | `1000`                         | **Purpose:** Sets the **numeric Primary Group ID (GID)** for the group created in the container. This works with `USER_ID` to manage correct **group ownership** for files on **mounted volumes**. \&lt;br>**Effect of Change:** Setting `GROUP_ID=$(id -g)` (highly recommended) makes the container's user part of a group with the _same GID as your host's primary group_. Changing it could lead to permission issues on shared volumes if it doesn't match your host's GID.      |
| `GROUP_NAME`             | Defaults to `USER_NAME`        | **Purpose:** Defines the **name** of the primary group created for the user in the container. \&lt;br>**Effect of Change:** By default, the group will share the same name as `USER_NAME` (e.g., `ofscraper`). If you explicitly set `GROUP_NAME=mygroup`, the user will be added to a group named `mygroup` instead. This is less common unless you have specific group naming conventions.                                                                                           |

***

***

## Images

{% embed url="https://hub.docker.com/r/datawhores/of-scraper" %}
Images on Docker.com
{% endembed %}

