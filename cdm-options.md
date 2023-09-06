# CDM options

You'll need to use a cdm to process encrypted content \
This is marked by the use of tempvideo and tempaudio\


### Manual

This is the recommended method as it is the most reliable and wont be  effected by lost of third party access or shutdown of services.&#x20;

#### Setup

* Follow this guide: [https://forum.videohelp.com/threads/408031-Dumping-Your-own-L3-CDM-with-Android-Studio?s=f22ce643aaaca3496c59a76a2a78c567](https://forum.videohelp.com/threads/408031-Dumping-Your-own-L3-CDM-with-Android-Studio?s=f22ce643aaaca3496c59a76a2a78c567)
*   In the end you should have two files\
    \- private key file

    \-client id file
* Save the files to a easily accessed location

#### Changing via config manually

change key-mode-default&#x20;

```
key-mode-default:manual
```

change client-id

Make sure to use the full path

```json
private-key:...??privatekey.pem
```

change private-key&#x20;

Make sure to use the full path

```json
client-id:...??client_id.bin
```

#### Changing via the prompt menu

* go to edit advance config settings menu
* When prompted for key-mode change to manual
* When prompted for private-key provide the full path&#x20;
* When prompted for client-id provide the full path

### CDRM

This is the first automatic option

provided by [https://cdrm-project.com/](https://cdrm-project.com/)\
If you can not access the site most likely the site is down, and you must select a alternative

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

* go to edit advance config settings
* when prompting for key-mode select cdrm



### CDRM2

This is the second automatic option

provided by [http://172.106.17.134:8080/](http://172.106.17.134:8080/)\
If you can not access the site most likely the site is down, and you must select a alternative

Setup

#### Changing via config manually

change key-mode-default&#x20;

```
key-mode-default:cdrm2
```

you could also pass the keymode arg

```
--key-mode-cdrm2
```

#### Changing via the prompt menu

* go to edit advance config settings
* when prompting for key-mode select cdrm2



### KEYDB

This is the third automatic option

provided by [https://keysdb.net/login?next=/](https://keysdb.net/login?next=/)\
If you can not access the site most likely the site is down, and you must select a alternative

#### Setup

* You must retrieve an api key from the website
* Authenticate with a discord account
* copy api key from [https://keysdb.net/me](https://keysdb.net/me)
* api key is alpha-numeric around 64 characters



#### Changing via config manually

change  keymode

```
key-mode-default:keydb
```

additionally change the keydb\_api

```
keydb_api:api from site
```

or pass the key-mode arg\
You must also have the keydb\_api setup in the config for this option

```
--key-mode keydb
```

#### Changing via the prompt menu

1. go to edit advance config settings
2. when prompting for key-mode select keydb
3. When prompted enter your keydb api key\
