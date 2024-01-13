# PIPX Install

1. **Option 1 pipx**&#x20;

{% embed url="https://pipx.pypa.io/stable/" %}

2. **Option 2 pip**

{% content-ref url="pip-install.md" %}
[pip-install.md](pip-install.md)
{% endcontent-ref %}

***



## Installing Python

{% content-ref url="managing-multiple-python-versions.md" %}
[managing-multiple-python-versions.md](managing-multiple-python-versions.md)
{% endcontent-ref %}

Good resources if you want an easy way to install python or to manage multiple version

## Installing OF-Scraper



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

###

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

d
