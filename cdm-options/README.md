# CDM Setup

To handle encrypted content, you'll require a CDM (Content Decryption Module). Indicators for this are the utilization of 'tempvideo' and 'tempaudio'.\\

### Manual

This method is recommended due to its reliability and independence from potential issues like loss of third-party access or service shutdowns.

#### Setup

* Follow this guide:

{% embed url="https://forum.videohelp.com/threads/408031-Dumping-Your-own-L3-CDM-with-Android-Studio/page26#post2766668" %}
Guide
{% endembed %}

*   In the end you should have two files\
    \- private key file

    -client id file
* Save the files to a location that is easily accessible

#### Changing via config manually

change key-mode-default

```
key-mode-default:manual
```

change client-id and private-key

Ensure you utilize the complete file path

```json
private-key:...??privatekey.pem
```

```json
client-id:...??client_id.bin
```

#### Changing via the prompt menu

* go to edit advance config settings menu in the prompt menu

<details>

<summary>prompt menu</summary>

[https://of-scraper.gitbook.io/of-scraper/using-prompts](https://of-scraper.gitbook.io/of-scraper/using-prompts)

</details>

* Switch to manual key-mode when prompted
* When asked for the private-key, provide the complete path
* When requested for the client-id, provide the complete path

### CDRM

\
This is the initial automated option provided by

{% embed url="https://cdrm-project.com" %}

If you're unable to access the site, it's likely down, and you'll need to choose an alternative.

#### Changing via config manually

change key-mode-default

```
key-mode-default:cdrm
```

you could also pass --key-mode arg

```
--key-mode cdrm
```

#### Changing via the prompt menu

* Navigate to the "Edit Config Settings" section
* Navigate to the "Edit Advanced Options" section
* When prompted to choose the key-mode, opt for "cdrm".
