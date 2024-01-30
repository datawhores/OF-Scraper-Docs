# PIP Install

## Installing Python

**Good resources if you want an easy way to install python or to manage multiple versio**n

{% content-ref url="managing-multiple-python-versions.md" %}
[managing-multiple-python-versions.md](managing-multiple-python-versions.md)
{% endcontent-ref %}

***

**Alternatively you can just follow the pre-install guides**

{% content-ref url="pre-install-guide/" %}
[pre-install-guide](pre-install-guide/)
{% endcontent-ref %}



## Installation

**Recommended python3.11**

{% tabs %}
{% tab title="Window Install" %}
## **Install**

**Stable Install**

```
py -3 -m pip install ofscraper
```

**Development verison**

```
py -3 -m pip install git+https://github.com/datawhores/OF-Scraper.git 
```

or

<pre><code><strong>py -3 -m pip install ofscraper --pre
</strong></code></pre>

**Specific version of script**

```
py -3 -m pip install ofscraper==x
```

where 'x' represents the version you intend to install\


## Upgrade

Not uninstalling has caused problems for users before

```
py -3 -m pip uninstall ofscraper
```

Next, run one of the installation commands listed below

```
py -3 -m pip install ofscraper --upgrade
```

or

```
py -3 -m pip install ofscraper==latest version number
```
{% endtab %}

{% tab title="Linux/Mac Install" %}
## Install

**Stable Install**

```
python3 -m pip install ofscraper
```

**Development version**

```
python3 -m pip install git+https://github.com/datawhores/OF-Scraper.git 
```

or

```
python3 -m pip install ofscraper --pre
```

**Specific version of script**

```
python3 -m pip install ofscraper==x
```

where 'x' represents the version you intend to install

## Upgrade

Not uninstalling has caused problems for users before

```
python3 -m pip uninstall ofscraper
```

Next, run one of the installation commands listed below

```
python3 -m pip install ofscraper --upgrade
```

or

```
python3 -m pip install ofscraper==latest version number
```
{% endtab %}
{% endtabs %}





####
