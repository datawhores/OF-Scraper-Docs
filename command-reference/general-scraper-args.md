# General Scraper Args

***

### -u, --username

```
Choose the usernames to process, separated by commas (e.g., name, name2). 
Use ALL (case-sensitive) to include all users.
```



### -eu, --excluded-username

```
Specify the usernames to exclude (e.g., name, name2). 
This takes precedence over the '--username' option.
```



### -d, --daemon

```
Execute the script in the background
Set the value for the time between runs
```



### -g, --original

```
Do not truncate lengthy paths
```

```
Default: False
```



### -c, --letter-count

```
intrepret config ‘textlength’ as max length by letter
```

```
Default: False
```



### -a, --action

```
Possible choices: like, unlike,download
```

<pre><code><strong>Download media from a post
</strong>and/or 
<strong>Execute a like or unlike action on each post
</strong></code></pre>
