# Docker

## Volumes

Note: Binaries are no longer stored in github you will have use one of these mounts to store the binary files autodownloader puts files in /root/.config/ofscraper/bin

| host    | docker                            | use          | required |
| ------- | --------------------------------- | ------------ | -------- |
| anypath | /home/ofscraper/.config/ofscraper | store config | True     |
| anypath | anypath                           | data storage | False    |

### Docker Run

```
docker run  -it --rm --name=ofscraper -v anypath:/home/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main ofscraper {args}
```

#### Older Version

The docker file was changed to  better support permissions on the host, if you using one of the older version you will need to modify your docker run or compose file

**This verison and older will require the modificaiton**\
[#](https://github.com/datawhores/OF-Scraper/commit/b06e9caefe8f3e62fedb399af6719c919ef19d2a)[https://github.com/datawhores/OF-Scraper/commit/b06e9caefe8f3e62fedb399af6719c919ef19d2a](https://github.com/datawhores/OF-Scraper/commit/b06e9caefe8f3e62fedb399af6719c919ef19d2a)\


```
docker run  -it --rm --name=ofscraper -v anypath:/root/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main {args}
```

You can also tell if the command already passed ofscraper in the entrypoint if you see this&#x20;

'ofscraper' (choose from 'post\_check', 'msg\_check', 'paid\_check', 'story\_check', 'manual')

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
