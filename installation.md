# Installation

## Intro

You can install with pip but it is recommend to install with pipx

\
As it will put OF-scraper into its own virtualenv and ensure that the program doesn't get interference from others installed\
\
[https://pypa.github.io/pipx/](https://pypa.github.io/pipx/)

#### Recommended python3.9 or python3.10

### Windows:

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
pipx install ofscraper==version
```

where x is the version you want to install

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

### Upgrade

Not uninstalling has caused user issues in the past

```
 pipx upgrade ofscraper
```

or

```
pipx install ofscraper==x --force
```

