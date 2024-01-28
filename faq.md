# FAQ/Common Issues

## 1. <mark style="color:blue;">Missing Post</mark>

Certain models delete content, which restricts OF-Scraper from accessing this specific content.

## 2<mark style="color:blue;">.  Number of users doesn't match account number</mark>



{% embed url="https://github.com/datawhores/OF-Scraper/issues/224#issuecomment-1757367312" %}

Every time you scroll down, the API requests 10 names, but frequently, fewer than 10 names are returned

### Example

Account: 400 total subs

**Active Accounts**

This figure is expected to be more accurate, but it seems to update according to a schedule, so it might be slightly off until synchronization occurs.

**Expired and ALL**

The count here can be significantly impacted by expired subscriptions.

For instance, an account may indicate it has 400 subscribers, but as OnlyFans iterates through each offset \[0, 10, 20, 30,...390], some offsets won't return 10 numbers, ultimately reducing the final count.



## 3. <mark style="color:blue;">Missing Models</mark>

Before creating an issue, ensure that you're using the latest version available.



## 4. <mark style="color:blue;">Lots of tempvideo or tempaudio files</mark>

Ensure your CDM (Content Decryption Module) is set up correctly

{% embed url="https://of-scraper.gitbook.io/of-scraper/cdm-options" %}

## 5. <mark style="color:blue;">Something is not working</mark>

Run the command to display the output in the console

```
ofscraper --output debug
```

Alternatively, run the command to output to your configuration folder.

```
ofscraper --log debug
```

Send the logs to a Discord channel or create a GitHub issue

## 6. <mark style="color:blue;">MP4Decrypt and FFMPEG</mark>

The mentioned programs below are necessary for downloading content, and they are compatible across various platforms.

{% embed url="https://ffmpeg.org/download.html" %}

{% embed url="https://www.bento4.com/documentation/mp4decrypt/" %}

#### Binaries

_These are the binaries used specifically during the automatic download process_

**FFmpeg**

***

**Windows:** [https://github.com/BtbN/FFmpeg-Builds/releases](https://github.com/BtbN/FFmpeg-Builds/releases) -> ffmpeg-master-latest-win64-gpl.zip

**Linux:** [https://github.com/BtbN/FFmpeg-Builds/releases](https://github.com/BtbN/FFmpeg-Builds/releases) -> shared version

**Mac:**  [**https://evermeet.cx/ffmpeg/get/zip**](https://evermeet.cx/ffmpeg/get/zip) -> downloads latest snapshot zip

***

**Mp4decrypt**

***

**Window:**  [<mark style="color:blue;">https://www.bok.net/Bento4/binaries</mark> ](https://www.bok.net/Bento4/binaries)-> Bento4-SDK-1-6-0-640.x86\_64-microsoft-win32.zip

**Linux:**  [https://www.bok.net/Bento4/binaries](https://www.bok.net/Bento4/binaries) -> Bento4-SDK-1-6-0-640.x86\_64-unknown-linux.zip

**Mac :** [https://www.bok.net/Bento4/binaries](https://www.bok.net/Bento4/binaries) -> Bento4-SDK-1-6-0-640.universal-apple-macosx.zip

***

#### More info

#### what to do after downloading

Simply provide OF-Scraper with the path to the program in the configuration file

**Note:** Ensure to input the complete path

#### Copying path on windows

You can utilize the tool below if Windows lacks an easy method to acquire the full path.

{% embed url="https://pathcopycopy.github.io/" %}

## 7. <mark style="color:blue;">ofscraper not found</mark>

This generally means that you need to update your PATH

## 8. <mark style="color:blue;">Can this download locked content</mark>

Yes.....if it was unlocked before.

## 9. <mark style="color:blue;">Status Down</mark>

This usually indicates that your authentication information is incorrect, or you've been signed out from OnlyFans

## 10. <mark style="color:blue;">404 Response</mark>

This could imply that the content you're attempting to scrape is no longer available. It might also signal that the model has deleted her account, making it inaccessible on the platform.



## 11. <mark style="color:blue;">Request taking a long time</mark>

If a request fails, OF-Scraper will pause and make several retry attempts. Frequent retries could extend the duration of certain runs.

{% hint style="info" %}
**Version 3.7 has a built in timelimit on requests to prevent them for being stuck forever**\
**However you can change the const value to adjust these values to your need**
{% endhint %}

## 12. <mark style="color:blue;">429 Response</mark>

* This error may stem from excessive requests, particularly when auto-liking/unliking.&#x20;
* The maximum appears to be 1000 per day.



## 13. <mark style="color:blue;">409 Response</mark>

\
You might observe cases where content is unavailable on the OnlyFans site, often indicated by placeholders or non-loading media.&#x20;

VPN users might experience this based on the VPN server they're connected to. Consequently, this also affects the API and OF-Scraper's ability to scrape content.

The most effective solution would be to switch VPN servers or allow some time for the situation to reset.

## 14. <mark style="color:blue;">Scrape entire paid page or --scape-paid should I do it</mark>

The amount of content you've purchased largely determines this

#### Does the regular scraper get purchased content?

Yes, if you've chosen "purchased," all purchased content for the selected models will be scraped. This is accomplished by using the models' usernames as input on the purchase page.

#### Then why the prompt

Certain models may have deleted accounts, making it necessary to scan the entire purchase page to access their purchases. Since they lack a name to use as input, a thorough scan becomes necessary.

#### When would you use to use it&#x20;

Personally, I rarely use this setting. However, if your scans are infrequent, it might be a good idea to turn it on.&#x20;

I'd also recommend using it during your initial scan.



#### When would you not use it

If you're conducting frequent scans, such as one per day, it's alright to turn it off for most scans



## 15. <mark style="color:blue;">FFmpeg  shared library not found Error</mark>

Example: : version \`GLIBCXX\_3.4.29' not found

### Cause

Missing shared libraries

This issue appears to only affect Linux systems

### Fix

Obtain the GPL non-shared release version.

{% embed url="https://github.com/BtbN/FFmpeg-Builds/releases" %}

### Some Info

* [https://superuser.com/questions/1712179/which-version-of-ffmpeg-is-the-latest](https://superuser.com/questions/1712179/which-version-of-ffmpeg-is-the-latest)
* using the version in your Linux Repo may not work



## 15. <mark style="color:blue;">CDM Issues</mark>

{% content-ref url="cdm-options/cdm-issues.md" %}
[cdm-issues.md](cdm-options/cdm-issues.md)
{% endcontent-ref %}





