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

Below are a table of the checks.





<table><thead><tr><th>Check </th><th width="272">config file if True</th><th>config folder if True</th></tr></thead><tbody><tr><td>config arg is not passed</td><td>$HOME/.config/ofscraper/config.json</td><td>$HOME/.config/ofscraper/</td></tr><tr><td>config_arg is an existing file</td><td>config_arg</td><td>config_arg<br>parent</td></tr><tr><td>config_arg  parent is an existing folder, and is not root</td><td>config_arg </td><td>config_arg  parent</td></tr><tr><td><p>config_arg ends in json</p><p>i.e</p><p>test.json</p></td><td>$HOME/.config/ofscraper/config_arg</td><td>$HOME/.config/ofscraper</td></tr><tr><td>Failback<br>always true</td><td>config_arg/config.json</td><td>config_arg</td></tr></tbody></table>



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
