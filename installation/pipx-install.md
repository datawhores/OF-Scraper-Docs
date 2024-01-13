# PIPX Install

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
