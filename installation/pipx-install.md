# PIPX Install

***

## Installing Python

**Good resources if you want an easy way to install python or want to use manage multiple python version**

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

***

**Alternatively you can just follow the pre-install guides**

{% content-ref url="pre-install-guide.md" %}
[pre-install-guide.md](pre-install-guide.md)
{% endcontent-ref %}

{% hint style="info" %}
**Tip: You can use the --python command to change the default python interpreter used for pipx**
{% endhint %}



***



***

## Installing/Upgrading OF-Scraper

{% hint style="info" %}
**Tip: Use the `--verbose` command to get more details about the install process.**
{% endhint %}

### **Stable Release Install**

To install the latest stable release of OF-Scraper:

```bash
uv tool install ofscraper --force
```

### Development Release

**Pre-release**

To install the latest pre-release version:

```bash
uv tool install --prerelease allow ofscraper --force
```

**Development**

To install the very latest development version directly from the GitHub repository:

```bash
uv tool install git+https://github.com/datawhores/OF-Scraper.git --force
```

### Specific Version of Script

To install a specific stable or pre-release version of the script:

```bash
uv tool install --prerelease allow ofscraper==<version>
```

Replace `<version>` with the exact version number you want to install (e.g., `ofscraper==2.4.3`).

### Specific Version of Python

You can specify the Python version `uv` should use for the tool installation by appending `--python <version_number>` to your command.

```bash
# Example: Install a specific script version with Python 3.12
uv tool install --prerelease allow ofscraper==<version> --python 3.12
```

### Including `pyffmpeg` (Optional)

`pyffmpeg` is a Python package that provides `ffmpeg` capabilities directly within Python, often by bundling its own `ffmpeg` binaries. It is included as an optional dependency group named `ffmpeg` within the `ofscraper` project's `pyproject.toml` (or `project.yaml`).

Installing `ofscraper` with this `ffmpeg` extra can simplify your setup, as you might not need to manually install `ffmpeg` or `mp4decrypt` on your system or mount them into Docker containers.

To install `ofscraper` and include `pyffmpeg` through the `ffmpeg` extra, use the following command:

```bash
uv tool install ofscraper[ffmpeg] --force
```

{% hint style="info" %}
When you install `ofscraper` using `ofscraper[ffmpeg]`, `pyffmpeg` will be automatically installed as a dependency. `pyffmpeg` then manages its own `ffmpeg` binary for the script, meaning you generally **do not** need to separately install `ffmpeg` or `mp4decrypt` on your host system or mount them into Docker containers.
{% endhint %}

### Upgrade

It's recommended to explicitly uninstall `ofscraper` before upgrading to avoid potential conflicts, as not doing so has caused problems for users previously.

To upgrade `ofscraper` to the latest stable release:

```bash
uv tool uninstall ofscraper # Recommended first step
uv tool install ofscraper --force
```

To upgrade `ofscraper` to the latest prerelease or development version:

```bash
uv tool uninstall ofscraper # Recommended first step
uv tool install --prerelease allow ofscraper --force
```
