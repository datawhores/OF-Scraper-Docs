# Content Check Mode Args

{% hint style="info" %}
&#x20;cached information is stored for 24 hours
{% endhint %}

## post\_check

Display a generated table of data showcasing model posts. Accept multiple URLs through command-line input or a file.



```
ofscraper post_check [global args] [post_check args]
```

### -u, --url

```
Scan posts via url
```

### -f, --file

```
Scan posts using a file containing URLs separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on posts
```

```
Default: False
```

## msg\_check

Display a generated table displaying data regarding model messages. Accept multiple URLs through command-line input or a file

```
ofscraper msg_check [global args] [msg_check args]
```

### -u, --url

```
Scan messages via url
```

### -f, --file

```
Scan messages using a file containing URLs separated by lines
```

### -fo, --force

```
Force the API to retrieve updated information on messages
```

```
Default: False
```

## paid\_check

Display a generated table featuring information on purchased content from models.&#x20;

Allows multiple usernames to be entered via command-line input or a file

```
ofscraper paid_check [global args] [paid_check args]
```

### -u, --username

```
Scan purchases via username
```

### -f, --file

```
Scan paid content using a file containing usernames separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on paid content
```

```
Default: False
```

## story\_check

Display a generated table of data with information about highlights and stories

Multiple usernames can be passed via command-line or file

```
ofscraper story_check  [global args] [story_check args]
```

### -u, --username

```
Scan stories/highlights via username
```

### -f, --file

```
Scan stories/highlist using a file containing usernames separated by lines.
```

### -fo, --force

```
Force the API to retrieve updated information on stories/highlights
```

```
Default: False
```
