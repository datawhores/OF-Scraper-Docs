# PIP Install

{% hint style="info" %}
**pipx is the preferred method, although you can also install OF-Scraper using pip**
{% endhint %}

## Installation

**Recommended python3.9 or python3.10**

#### Windows:

**stable**

```
py -3 -m pip install ofscraper
```

or

**development**

```
py -3 -m pip install git+https://github.com/datawhores/OF-Scraper.git 
```

or

**specific version**

```
py -3 -m pip install ofscraper==x
```

where 'x' represents the version you intend to install

#### macOS/Linux

```
python3 -m pip install ofscraper
```

or

```
python3 -m pip install git+https://github.com/datawhores/OF-Scraper.git 
```

or

**specific version**

```
python3 -m pip install ofscraper==x
```

where 'x' represents the version you intend to install

#### Upgrade

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
