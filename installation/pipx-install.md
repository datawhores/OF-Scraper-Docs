# PIPX Install

## Installing Python

**Good resources if you want an easy way to install python or want to use manage multiple python version**

{% content-ref url="managing-multiple-python-versions.md" %}
[managing-multiple-python-versions.md](managing-multiple-python-versions.md)
{% endcontent-ref %}

***

**Alternatively you can just follow the pre-install guides**

{% content-ref url="pre-install-guide/" %}
[pre-install-guide](pre-install-guide/)
{% endcontent-ref %}

{% hint style="info" %}
**Tip: You can use the --python command to change the default python interpreter used for pipx**
{% endhint %}

## Getting PIPX

{% hint style="info" %}
**Installing PIPX with PIP is recommended** \
**This way you can control which python it is install with**
{% endhint %}

{% embed url="https://github.com/pypa/pipx" %}

## Installing OF-Scraper

{% hint style="info" %}
**Tip: Use the --verbose command to get more details about the install process**
{% endhint %}

{% tabs %}
{% tab title="Windows Install" %}
## **Install**

**Stable install**

```
pipx install ofscraper
```

#### development

```
pipx install git+https://github.com/datawhores/OF-Scraper.git 
```

#### Specific version of script

```
pipx install ofscraper==version --force
```

where x is the version you want to install

#### Specific version of python

```
Append --python $(where {python version}
```

```
Example: pipx install ofscraper --python $(where python3.11)
```

## Upgrade

Not uninstalling has caused problems for users before

```
 pipx upgrade ofscraper
```

or

```
pipx install ofscraper==x --force
```

```
Append --python $(where {python version}
```
{% endtab %}

{% tab title="Linux/Mac Install" %}
**Stable Install**

```
pipx install ofscraper
```

#### Development version

```
pipx install git+https://github.com/datawhores/OF-Scraper.git 
```

#### Specific version of script

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

#### Upgrading

Not uninstalling has caused problems for users before

```
 pipx upgrade ofscraper
```

or

```
pipx install ofscraper==x --force
```

```
Append --python $(where {python version}
```
{% endtab %}
{% endtabs %}

###
