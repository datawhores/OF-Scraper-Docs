# PIP Install

pipx is recommended but OF-Scraper can also be installed via pip

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

where x is the vesion you want to install

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

where x is the vesion you want to install

#### Upgrade

Not uninstalling has caused user issues in the past

```
python3 -m pip uninstall ofscraper
```

Then run one of the install commands above

```
python3 -m pip install ofscraper --upgrade
```

or

```
python3 -m pip install ofscraper==latest version number
```
