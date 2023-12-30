# Install

No Install Run

The OF-Scraper repository contains comprehensive binaries enabling you to run OF-Scraper without requiring additional installations on your computer.

The zip file operates straight away, but with the .exe, it needs to unpack into a temporary folder, which might cause the script to start a bit slower.



**Warning**

Windows binaries, in particular, can have distinct issues due to their use of spawning versus forking processes. If you encounter problems with the script, they might be resolved by opting for a proper installation.

{% embed url="https://github.com/datawhores/OF-Scraper/releases" %}

{% content-ref url="release-info.md" %}
[release-info.md](release-info.md)
{% endcontent-ref %}

## Before Starting

The guide assumes you have your terminal program open and have already installed Python. If you're unsure about this, follow this guide

{% content-ref url="pre-install-guide.md" %}
[pre-install-guide.md](pre-install-guide.md)
{% endcontent-ref %}

##

## Intro

While you can install it using pip, it's recommended to use pipx. This method places OF-scraper&#x20;

into its own virtual environment, ensuring the program operates without interference from other installations.

{% embed url="https://pipx.pypa.io/stable/" %}

***

<details>

<summary>Still want to install with pip</summary>

[https://of-scraper.gitbook.io/of-scraper/installation/pip-install](https://of-scraper.gitbook.io/of-scraper/installation/pip-install)

</details>



***

Otherwise, If you prefer to proceed using pipx, you can follow along with the guide

## Preparing Pipx

#### Setting Python Version

\
pipx utilizes your default Python version. If you need to ensure a specific Python version, consider using \
one of the following

1. **pyenv**

{% embed url="https://github.com/pyenv/pyenv" %}

#### Install python with pyenv

{% embed url="https://realpython.com/lessons/pyenv-install-python/" %}

***

2. **miniconda**

{% embed url="https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html" %}



**Install python with miniconda**

{% embed url="https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-python.html" %}



## Install

### Video

Watch this video for a quick overview of the install and run process

{% embed url="https://bunkrr.su/v/scraper-l3eS0Abl.mkv" %}



### Windows:

####

#### stable

```
pipx install ofscraper
```

#### development

```
pipx install git+https://github.com/datawhores/OF-Scraper.git 
```

#### specific version

```
pipx install ofscraper==version --force
```

where x is the version you want to install

#### Specific version of python

```
Append --python $(where {python version})
```

```
Example: pipx install ofscraper --python $(where python3.11)
```

### macOS/Linux

```
pipx install ofscraper
```

#### development



```
pipx install git+https://github.com/datawhores/OF-Scraper.git 
```

#### specific version

```
pipx install ofscraper==x --force
```

where x is the version you want to install

#### Specific version of python



```
Append --python $(which {python version})
```

```
Example: pipx install ofscraper --python $(which python3.11)
```

### Upgrade

Not uninstalling has caused problems for users before

```
 pipx upgrade ofscraper
```

or

```
pipx install ofscraper==x --force
```
