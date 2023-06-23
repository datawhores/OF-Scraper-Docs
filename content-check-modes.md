# Content Check Modes

## What is this

<figure><img src=".gitbook/assets/image2.png" alt=""><figcaption></figcaption></figure>

scrapes onlyfans.com and parses the database to display information about content through a generated table

Each individual media is given it own row within the table

The table is searchable/can be filtered

Table includes lots of information including

* price of content
* Will try to show if media is in your library based on media id
* If the media is unlocked
* The post that a media is connected
* Date the media was posted
* text included with the media
* Length of media



It uses cache to speed things up

Cache is created with the normal scraper or when you run one content check mode, and lasts for a day before the program get's new data You can also use --force to retrieve the latest data

## Sorting the table

Click the column labels on the top ![image](https://github.com/datawhores/OF-Scraper/assets/67020411/14ca5b89-c9c1-44bc-936e-db4683f81823)

* First click will be desc
* second click will be asc
* Alternates after

## Filtering the table

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/7aba01b5-e768-43aa-ba98-6d85aca4e37e)

The form on top holds all the filters clicking on submit will filter the form

### Adding filter from table

Click on a cell to heighlight it

enter semicolon: \[ ;] or  apostrophe: \[ ' ]  the table will filter to rows matching that cell value



#### Example

The word videos is heightlighted\


<figure><img src=".gitbook/assets/img1.png" alt=""><figcaption></figcaption></figure>

Once enter semicolon: \[ ;] or  apostrophe: \[ ' ]   is pressed

only cell matching videos will appear

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/11911f08-2e0c-4759-b033-1fcaf40a5e6f)

Additionally the forum will also update

This process stacks until you press reset

### Reset the table

Click the reset button.

Note: the current table information is saved to memory, so new information won't be retrieved until you restart the program

### Table Columns

```
Download Cart = A cart for sending downloads to a queue
```

```
Username = model username
```

```
Downloaded = is the media marked by the db as downloaded
```

```
Unlocked = Whether the post tied to the media is unlocked
```

```
Times Detected = The greater of how many times the media id is in the db 
vs how many times the API returns the same media id from different posts
```

```
Length = This is the length of videos/audio
N/A ==0 for pictures
```

```
Mediatype = type of media
```

```
Post date = Date the post was created/updated
```

```
Post Media Count = Number of media in the original post
```

```
Responsetype = Which API the media was retrieved from
```

```
Price = Where the price of the post the media is tied to
```

```
Post ID = id for the post the media is tied
```

```
Media ID = id for the media
```

```
Text = Text that came with the post
```

### Example filter by all content with the text dog

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/6f03fbe1-2ad9-4296-9b95-7a4cad874e36)

### Additional info about text filter

Searches uses python regex

#### Searching case-senstive

Upper case trigger a case-sensitive search

```
Dog
```

#### Searching for full string match

This will trigger the search to match text that are exactly dog, and not text containing dog within them

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/010b2d9a-a841-4b96-85c2-220a1fbecafc)

## Args

### Post Check Mode

This is for checking posts on the main timeline or paid content via the post url

1. you must add the --url or --file argument
2. You can combine the previous args
3. \--url can be split by comma or passed multiple times
4. \--file can only be passed once, and does not spit string will be interpreted as single url

#### Examples

`ofscraper post_check --url url,url,url`

`ofscraper post_check --url url --url url`

`ofscraper post_check --file file`

`ofscraper post_check --file file --url url`

#### File

Should contain accepted urls line separated

#### Accepted urls

**post page**

```
https://onlyfans.com/1113331313/model
```

**model page**

```
https://onlyfans.com/model
```

**model name**

```
model
```

**model number**

```
11131313
```

### Message Check Mode

To not repeat message check mode is the same as post\_check the only difference is the type of posts accepted

Since there is no way to link to a specific post if cache is expired then all messages must be scrape

#### Examples

Again all the previous examples will work

`ofscraper msg_check --url url,url,url`

#### Accepted urls

**chat page**

```
https://onlyfans.com/my/chats/chat/11131313/
```

**model name**

```
model
```

**model number**

```
11131313
```

### Paid Check Mode

Scrapes paid content via username

1. you must add the --username or --file argument
2. You can combine the previous args
3. \--username can be split by comma or passed multiple times
4. \--file can only be passed once, and does not spit string will be interpreted as single username

#### Examples

```
ofscraper paid_check --username username,username
```

```
ofscraper paid_check --username username --username username
```

```
ofscraper paid_check --file file
```

```
ofscraper paid_check --file file --username username
```

#### File

Should contain usernames line separated

#### Accepted username

**model name**

```
model
```

**model number**

```
11131313
```

### story check mode

Scrapes story/highlights via username Note: stories are temporary

1. you must add the --username or --file argument
2. You can combine the previous args
3. \--username can be split by comma or passed multiple times
4. \--file can only be passed once, and does not spit string will be interpreted as single username

#### Examples

`ofscraper story_check --username username,username`

`ofscraper story_check --username username --username username`

`ofscraper story_check --file file`

`ofscraper story_check --file file --username username`

#### File

Should contain usernames line separated

### Getting latest content

For each of these modes information for each model is cached for 24 hours. add the --force argument to any of the modes to retrieve the latest content

```
ofscraper msg_check --url url --force
```
