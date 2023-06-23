# Installation

## Intro

You can install with pip but it is recommend to install with pipx

\
As it will put OF-scraper into its own virtualenv and ensure that the program doesn't get interference from others installed

#### Recommended python3.9 or python3.10

### Windows:

#### stable

```
pipx install ofscraper
```

or

#### development

```
pipx install git+https://github.com/datawhores/OF-Scraper.git 
```

or

#### specific version

```
pip install ofscraper==x
```

where x is the vesion you want to install

### macOS/Linux

```
pip3 install ofscraper
```

or

```
pip3 install git+https://github.com/datawhores/OF-Scraper.git 
```

or

#### specific version

```
pip install ofscraper==x
```

where x is the vesion you want to install

### Upgrade

Not uninstalling has caused user issues in the past

```
pip3 uninstall ofscraper
```

Then run one of the install commands above

```
pip3 install ofscraper --upgrade
```

or

```
pip3 install ofscraper==latest version number
```
