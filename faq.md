# FAQ

## <mark style="color:blue;">Missing Post</mark>

This typically is because the model has deleted the post.\
Unfortunately OF-Scraper would not be able to scrape this content

## <mark style="color:blue;">Number of users doesn't match account number</mark>

[https://github.com/datawhores/OF-Scraper/issues/224#issuecomment-1757367312](https://github.com/datawhores/OF-Scraper/issues/224#issuecomment-1757367312)\
\
Each time you scroll down the api will request 10 names, but it is often that 10 names will not be returned



### Example

Account: 400 total subs

**Active Accounts**

This number should be more accurate, but seems to update based on a schedule so it may be a few off until things sync up

**Expired and ALL**

The number here can be greatly effected by expired subscriptions

For example a account may state it has 400 subs

However as onlyfans iterate through each offset \[0,10,20,30,40,....390]

Some offsets will not return 10 numbers, reducing the number at the end

###



## <mark style="color:blue;">Lots of tempvideo or tempaudio files</mark>

Make sure your cdm is setup correctly

{% embed url="https://of-scraper.gitbook.io/of-scraper/cdm-options" %}

### <mark style="color:blue;">Something is not working</mark>

run to output to console

```
ofscraper --output debug
```

or to output to your config folder

```
ofscraper --log debug
```

Send logs on discord channel or make a git issue

### <mark style="color:blue;">MP4Decrypt and FFMPEG</mark>

The programs mentioned are required to download content

Both programs are cross-platform

{% embed url="https://ffmpeg.org/download.html" %}

{% embed url="https://www.bento4.com/documentation/mp4decrypt/" %}

#### Binaries

These are the binaries used during auto download

**Windows:** https://github.com/BtbN/FFmpeg-Builds/releases -> ffmpeg-master-latest-win64-gpl.zip

**Linux:** [https://github.com/BtbN/FFmpeg-Builds/releases](https://github.com/BtbN/FFmpeg-Builds/releases) -> shared version

**Mac:**  https://www.bok.net/Bento4/binaries/ -> Bento4-SDK-1-6-0-640.universal-apple-macosx.zip

#### More info

#### what to do after downloading

Just provide OF-Scraper the path to the program in the config file

**Note:** This needs to be the full path

#### Copying path on windows

If windows doesn't have a built in esay way to get the full path

{% embed url="https://pathcopycopy.github.io/" %}

### <mark style="color:blue;">ofscraper not found</mark>

This usually means that your need to update your path

### <mark style="color:blue;">Can this download locked content</mark>

Yes..if unlocked prior

### <mark style="color:blue;">Status Down</mark>

This typically means that your auth information is not correct, or onlyfans signed you out.

### <mark style="color:blue;">404 Issue</mark>

This could mean that the content you are trying to scrape is no longer present. It can also indicate that model has deleted her account, and it is no longer accesible on the platform

### <mark style="color:blue;">Request taking a long time</mark>

If a request fails ofscraper will pause and try again a few times. This can lead to certain runs taking longer at points.

### <mark style="color:blue;">429 issue</mark>

* This comes from making too many requests
* 1000 likes is the max per day

## <mark style="color:blue;">Scrape entire paid page or --scape-paid should I do it</mark>

It really depends on how much content you've purchased.

#### Does the regular scraper get purchased content?

Yes if you selected "purchased" then all purchased content for selected models will be scraped. This is done by using the models username as an input on the purchase page

#### Then why the prompt

Some models have deleted accounts, and getting there purchases requires scanning the entire purchase page. They have no name to use as an input

#### When would you use to use it&#x20;

I would use it once on the first run just to get what is in your library Then I would use it if you haven't scan in a while

#### When would you not use it

&#x20;I do at least one scan a day So I would turn it off for most scans, after the initial scan
