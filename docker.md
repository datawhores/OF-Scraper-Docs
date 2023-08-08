# Docker

## Volumes

Note: Binaries are no longer stored in github you will have use one of these mounts to store the binary files autodownloader puts files in /root/.config/ofscraper/bin

| host    | docker                            | use            | required |
| ------- | --------------------------------- | -------------- | -------- |
| anypath | /home/ofscraper/.config/ofscraper | store config   | True     |
| anypath | anypath                           | binary storage | False    |

Docker Run

```
docker run  -it --rm --name=ofscraper -v anypath:/root/ofscraper/.config/ ghcr.io/datawhores/of-scraper:main {args}
```

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
