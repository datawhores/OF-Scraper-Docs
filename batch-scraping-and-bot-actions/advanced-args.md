# Advanced Args

### --profile

You can combine this with **'--config'**.&#x20;

This option holds precedence over the currently active profile within the configuration file

```
Change location of profile 
```

### --users-first

This adjustment alters the download order to prioritize fetching links for all selected users initially. While this may lead to a longer wait for downloads to commence, it can prove beneficial in specific scenarios.

```
ofscraper --user-first
```

### multiple configs

```
ofscraper --config folder or file
```

The program attempts to intelligently guess the location of your config folder.&#x20;

You can observe the locations it's scanning in the table. The checks will cease upon reaching a successful match (True) or reaching the failback check.







<table><thead><tr><th>Check </th><th width="272">config file if True</th><th>config folder if True</th></tr></thead><tbody><tr><td>--config  is not passed</td><td>$HOME/.config/ofscraper/config.json</td><td>$HOME/.config/ofscraper/</td></tr><tr><td>config_arg is an existing file</td><td>config_arg</td><td>config_arg<br>parentdir</td></tr><tr><td>config arg is an existing dir</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td>config arg has no extension</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td><p>config_arg ends is just  a single file</p><p>i.e</p><p>test.json</p></td><td>$HOME/.config/ofscraper/config_arg</td><td>$HOME/.config/ofscraper</td></tr><tr><td>Failback<br>always true<br>Note:<br>The only option is for config_arg to be something like <br>/home/me/test.json</td><td>config_arg</td><td>config_arg<br>parentdir</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



####

#### Shared information

Two configs within the same folder can share

* Profiles
* log files
* cache
* authorization

#### Duplication check

This relies on your configuration settings. If two configurations share identical metadata settings, duplicates won't exist between those configurations.

### multiple profile auth

Authentication for various accounts is managed via profiles. You can modify the default profile either through the configuration or by using the '--profile' argument.

#### Example

```
ofscraper --profile test
```

```
config file location=/home/test/.config/ofscraper/config.json
```

The profile is consistently located within the parent folder of the configuration file and is always appended with '\_profile'.&#x20;

Hence, in this scenario, the profile would be

```
profile location=/home/test/.config/ofscraper/test_profile
```

### no cache

bypass all cache usage&#x20;

useful for testing

```
ofscraper --no-cache
```
