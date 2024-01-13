---
description: Getting OF-Scraper onto you system
---

# Install

##

## Before Starting

The guide assumes you have your terminal program open and have already installed Python. If you're unsure about this, follow this guide

{% content-ref url="pre-install-guide.md" %}
[pre-install-guide.md](pre-install-guide.md)
{% endcontent-ref %}



## Getting Package Manager



{% hint style="info" %}
**Pipx is recommend puts binaries in there own virtualenv, leading to less issues**
{% endhint %}

1. **Option 1 pipx**&#x20;

{% embed url="https://pipx.pypa.io/stable/" %}

2. **Options 2 pip**

{% content-ref url="pip-install.md" %}
[pip-install.md](pip-install.md)
{% endcontent-ref %}

***



## Managing Multiple Python Versions

{% hint style="info" %}
**Both of these optional tools allow for managing multiple versions of python**
{% endhint %}

#### 1. pyenv

{% embed url="https://github.com/pyenv/pyenv" %}
Getting pyenv
{% endembed %}

{% embed url="https://realpython.com/lessons/pyenv-install-python/" %}
Installing Python via pyenv
{% endembed %}

***

2. **miniconda**

{% embed url="https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html" %}
Getting Miniconda
{% endembed %}

{% embed url="https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-python.html" %}
Installing Python via miniconda
{% endembed %}



## Install



{% tabs %}
{% tab title="Windows Install" %}
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
{% endtab %}

{% tab title="Linux/Mac Install" %}


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
{% endtab %}
{% endtabs %}

### Video

Watch this video for a quick overview of the install and run process

{% embed url="https://bunkrr.su/v/scraper-l3eS0Abl.mkv" %}

## Binary Releases

{% hint style="info" %}
**Check out the binaries below if you want to run without installing**
{% endhint %}

{% hint style="info" %}
**However, pip/pipx are the recommended as they will have better performance**\
**and provide easier path to updates**
{% endhint %}

{% embed url="https://github.com/datawhores/OF-Scraper/releases" %}

{% content-ref url="release-info.md" %}
[release-info.md](release-info.md)
{% endcontent-ref %}
