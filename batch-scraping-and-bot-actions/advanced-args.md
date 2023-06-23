# Advanced Args



### au, --auth

This can be combined with --config

This option has preference over the auth path --config would have provided

```
Change location of auth file
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

Below are a table of the check\
If a check is false then then the next check is done\
\
There is a failback check if all other checks fail





<table><thead><tr><th>Check </th><th width="272">config file if True</th><th>config folder if True</th></tr></thead><tbody><tr><td>--config  is not passed</td><td>$HOME/.config/ofscraper/config.json</td><td>$HOME/.config/ofscraper/</td></tr><tr><td>config_arg is an existing file</td><td>config_arg</td><td>config_arg<br>parent</td></tr><tr><td>config arg is an existing dir</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td>config arg has no extension</td><td>config_arg/config.json</td><td>config_arg</td></tr><tr><td><p>config_arg ends is just  a single file</p><p>i.e</p><p>test.json</p></td><td>$HOME/.config/ofscraper/config_arg</td><td>$HOME/.config/ofscraper</td></tr><tr><td>Failback<br>always true<br>Note:<br>The only option is for config_arg to be something like <br>/home/me/test.json</td><td>config_arg</td><td>config_arg</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



####

#### Shared information

Two configs within the same folder can share

* Profiles
* log files
* cache
* authorization

### no cache

skips cache when retrieving post

```
ofscraper --no-cache
```