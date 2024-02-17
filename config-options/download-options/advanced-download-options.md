---
description: Options that have an effect on the download experience
---

# Advanced Download Options

## backend

\
Both aio and httpx can handle downloads and requests. Normally aio is faster,so switching is only required if your having issues&#x20;

Historically, this has mostly been the case Mac users, and even then, only a small group among them

***

## downloadbars

whether to show download progress bars or not

Disabling these can improve performance

***

## temp\_dir

{% hint style="info" %}
**If not set the the final download directory is used to hold temp files**
{% endhint %}

This overrides the temporary directory used during download
