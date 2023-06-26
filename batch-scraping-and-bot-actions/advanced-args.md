# Advanced Args

###

### --profile

This can be **combined** with --config

This option has preference over the profile  the currently active config would have provided

```
Change location of profile 
```

### --users-first

Changes the order of downloading to retrieve links for all selected users first This means waiting longer for downloads to start, but this can be useful in certain situations

```
ofscraper --user-first
```

### multiple configs

```
ofscraper --config folder or file
```

The program will try to make a good guess of where you want the config folder

You can see what the program is looking for in the table\
The checks will stop once True or the failback check is reached







<table><thead><tr><th>Check </th><th width="272">config file if True</th><th>config folder if True</th></tr></thead><tbody><tr><td>--config  is not passed</td><td>$HOME/.config/ofscraper/config.json</td><td>$HOME/.config/ofscraper/</td></tr><tr><td>config_arg is an existing file</td><td>config_arg</td><td>config_arg<br>parentdir</td></tr><tr><td>config arg is an existing dir</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td>config arg has no extension</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td><p>config_arg ends is just  a single file</p><p>i.e</p><p>test.json</p></td><td>$HOME/.config/ofscraper/config_arg</td><td>$HOME/.config/ofscraper</td></tr><tr><td>Failback<br>always true<br>Note:<br>The only option is for config_arg to be something like <br>/home/me/test.json</td><td>config_arg</td><td>config_arg<br>parentdir</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



####

#### Shared information

Two configs within the same folder can share

* Profiles
* log files
* cache
* authorization

#### Duplication check

This is based on your config setting

\
If two configs have the same settings for metadata, then you will not have duplicates among those configs

### multiple profile

Authentication for different accounts is done through profiles

The default profile can be changed through the config or by passing the --profile argument

#### Example

```
ofscraper --profile test
```

```
config file location=/home/test/.config/ofscraper/config.json
```

profile is always place within the config file locations parent folder, and is always appending with \_profile

Therefore the profile here would be&#x20;

```
profile location=/home/test/.config/ofscraper/test_profile
```

### no cache

skips cache when retrieving post

Mostly for testing

```
ofscraper --no-cache
```
