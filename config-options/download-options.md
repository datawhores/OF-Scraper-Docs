# Download Options

## backend

\
Both aio and httpx can handle downloads and requests. Normally aio is faster,so switching is only required if your having issues&#x20;

Historically, this has mostly been the case Mac users, and even then, only a small group among them.

## downloadbars

whether to show download progress bars or not

Disabling these can improve performance

## auto\_resume

{% hint style="info" %}
replaces partfileclean
{% endhint %}

If you set this to false, the script will  delete .part files, and will not be able to auto resume
