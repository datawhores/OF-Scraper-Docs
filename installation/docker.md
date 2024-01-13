# Docker

## Volumes



{% hint style="info" %}
**Binaries for mp4decrypt and ffmpeg are no longer stored in GitHub. You'll need to utilize one of the mounts for storing binaries.**
{% endhint %}

{% hint style="info" %}
**If you opt for the auto download feature when installing mp4decrypt or ffmpeg, the binaries will be stored in /root/.config/ofscraper/bin within the Docker image**
{% endhint %}



| host    | docker                            | use          | required |
| ------- | --------------------------------- | ------------ | -------- |
| anypath | /home/ofscraper/.config/ofscraper | store config | True     |
| anypath | anypath                           | data storage | False    |

## Docker Run

```
docker run  -it --rm --name=ofscraper -v anypath:/home/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main ofscraper {args}
```

## Docker Compose

{% hint style="info" %}
**make sure to install ffmpeg and mp4decrypt to your local system and add to the volumes in the compose file.**
{% endhint %}

```
version: "3"
services:
    of-scraper:
        stdin_open: true
        tty: true
        container_name: ofscraper
        volumes:
            - /usr/bin/ffmpeg:/usr/bin/ffmpeg
            - /usr/local/bin/mp4decrypt:/usr/local/bin/mp4decrypt
            - ./config/:/home/ofscraper/.config/
        image: ghcr.io/datawhores/of-scraper:main
        command: ofscraper
```

To run the scraper manually use: `docker exec ofscraper ofscraper {args}`



## Images

{% embed url="https://hub.docker.com/r/datawhores/of-scraper" %}
Images on Docker.com
{% endembed %}

{% embed url="https://github.com/datawhores/OF-Scraper/pkgs/container/of-scraper/" %}
Images on ghcr.io
{% endembed %}

| Syntax             | Example      | What it is                           |
| ------------------ | ------------ | ------------------------------------ |
| latest             | latest       | get the latest stable release        |
| branch-commitshort | main-9e54ed3 | container for specific commit        |
| branch             | main         | latest commits for a specific branch |
| version number     | 2.4.3        | specific stable release              |

### Older Versions

\
The Docker file was updated to enhance host permissions support. If you're using an older version, you'll need to adjust your Docker run or compose file.

For versions equal to or older than this commit: [https://github.com/datawhores/OF-Scraper/commit/b06e9caefe8f3e62fedb399af6719c919ef19d2a](https://github.com/datawhores/OF-Scraper/commit/b06e9caefe8f3e62fedb399af6719c919ef19d2a)\\

```
docker run  -it --rm --name=ofscraper -v anypath:/root/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main {args}
```

> You can determine if the command has already passed 'ofscraper' in the entrypoint by checking for this sequence: 'ofscraper' (options include: 'post\_check', 'msg\_check', 'paid\_check', 'story\_check', 'manual').
