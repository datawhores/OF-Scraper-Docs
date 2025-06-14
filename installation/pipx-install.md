# PIPX Install

***

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



***

## Getting UV

{% hint style="info" %}
**Installing UV with one of their scripts is recommend**
{% endhint %}

{% embed url="https://docs.astral.sh/uv/getting-started/installation/" %}

***

## Installing/Upgrading OF-Scraper

{% hint style="info" %}
**Tip: Use the --verbose command to get more details about the install process**
{% endhint %}

### **Stable Release install**

```
uv tool install ofscraper --force
```

### Development Release

#### Pre-release

```
uv tool install --prerelease allow ofscraper --force
```

#### Development

```
uv tool install git+https://github.com/datawhores/OF-Scraper.git --force
```

### Specific version of script

```
uv tool install --prerelease allow ofscraper==version
```

where x is the version you want to install

### Specific version of python

```
Append --python (version number)
```

<pre><code><strong>Example: uv tool install --prerelease allow ofscraper==version --python 3.12
</strong></code></pre>

### Upgrade

Not uninstalling has caused problems for users before

```
uv tool upgrade ofscraper
```

or to upgrade to a prerelease/dev version

```
uv tool install ofscraper --prerelease allow
```
