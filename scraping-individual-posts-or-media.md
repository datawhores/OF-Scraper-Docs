# Scraping Individual Posts or Media



***

## Scraping content from timeline post

**1. click '...' and then copy link to post**

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/84a87986-36ef-4d75-a9d9-10d7b572419a)

```
ofscraper manual --url copied_link
```

Alternatively

```
ofscraper manual --url postid
```



***

## Scraping content from purchase page

**1. Click '...' and copy link to message**

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/74cebb3f-c0e4-4cbb-b2f7-18b52e2a98a6)

```
ofscraper manual --url copied_link
```



***

## Advanced

\
To grasp this better, checking out the **`get_info`** function in **`manual.py`** is the ideal way as it accepts a wider range of URLs.



***

## Scraping Individual Media

**1. Run a content scraper mode**

{% content-ref url="content-check-modes.md" %}
[content-check-modes.md](content-check-modes.md)
{% endcontent-ref %}

**2. Use the mouse to toggle the checkmark of the row you want to download**\
_Note you can also toggle with  ";" or "',"_&#x20;

Only unlocked media will have a checkmark

* media marked for download will have 'added' in them

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/48e3badd-5502-480b-aeaa-04d58c769dd1)

**3. Click Send to OF-Scraper**

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/9727c122-73ea-4043-850a-4d4fe0ffbf33)

Downloads progress will be updated in console

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/9d0748b2-c036-4b7f-91c0-499b78a808e1)

**4. Finished Downloads will have the words download in them**

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/7ae553c7-94d1-4a03-a44f-83fd056b80f9)

You can redownload by using ";" or "'" to untoggle and then retoggle with the added value

| Status      | Meaning                                                     |
| ----------- | ----------------------------------------------------------- |
| added       | content is ready to be added to queue                       |
| downloading | content is added to queue, and will be downloaded           |
| downloaded  | content was downloaded and all post process were successful |
| failed      | content was not downloaded and or post process failed       |

### Good things to know

* Downloads won't start off immediately because the program is designed to check the queue for new downloads every 10 seconds.
* Since there isn't a progress bar, enabling debug mode could be helpful in this situation.
* By clicking on the table, you can instantly add more downloads. Any entry marked as "downloading" will be inaccessible for modification
* Sorting and filtering functionalities should also be operational
