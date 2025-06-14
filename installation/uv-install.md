# UV Install

## Installing UV

{% hint style="warning" %}
Important: UV is a standalone binary. You do not need Python installed on your system to install UV. Once UV is installed, it can then manage and install Python versions for you. Installing UV with one of their official installation scripts is recommended for the most straightforward setup.
{% endhint %}

[pre-install-guide](pre-install-guide/ "mention")

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

### Including pyffmpeg (Optional)

pyffmpeg is a Python package that provides ffmpeg capabilities directly within Python by bundling its own ffmpeg binaries. You can accomplish this by appending \[ffmpeg] to the install name when using uv tool install.

example:  `uv tool install ofscraper[ffmpeg] --force`

{% hint style="info" %}
When you install ofscraper using ofscraper\[ffmpeg], pyffmpeg will be automatically installed as a dependency. pyffmpeg then manages its own ffmpeg binary for the script, meaning you generally do not need to separately install ffmpeg or mp4decrypt on your host system or mount them into Docker containers.
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
