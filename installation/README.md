# Install

## No Install Run

We have complete binaries in the OF-Scraper repo

These will allow you to run OF-Scraper without having to install anything additional on your computer



The main difference between the zip and the exe, is that the exe has to unpack to a temporary folder. In theory this might slow down the startup time of the script.&#x20;



**Warning**

The windows binaries especially are prone to unique issues, because of there use of spawn vs forking of processes. If your facing issues with the script, then it may be fixed by investing into a proper install.

{% embed url="https://github.com/datawhores/OF-Scraper/releases" %}

{% embed url="https://of-scraper.gitbook.io/of-scraper/installation/release-info" %}

### Before Starting

The guide assumes&#x20;

1. You have your terminal program open&#x20;
2. You have already installed python&#x20;

If your not sure about this follow this guide

{% embed url="https://of-scraper.gitbook.io/of-scraper/installation/pre-install-guide" %}

##

## Intro

You can install with pip but it is recommend to install with pipx

\
As it will put OF-scraper into its own virtualenv and ensure that the program doesn't get interference from others installed\


{% embed url="https://pypa.github.io/pipx/" %}

#### CLI

This is a CLI program so commands must be entered from your terminal program

### Still want to install with pip

{% embed url="https://of-scraper.gitbook.io/of-scraper/installation/pip-install" %}

## Install

### Video

{% embed url="https://bunkrr.su/v/scraper-l3eS0Abl.mkv" %}

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
