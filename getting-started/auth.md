---
description: Setting up authorization
---

# Auth

***

## Example

{% hint style="info" %}
**values are randomized, but should be somewhat similar in style to the example**
{% endhint %}

An example of what an auth file should typically look like

```
{
    "auth": {
        "user_agent": "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36",
        "x-bc": "fncx03r1ygvh26ezq4pe830l49xtj1a146e1x2av",
        "auth_id": "400000",
        "sess": "5pb18tyng144dqyzevbgfddnrz",
        "auth_uid_": "400000"
    }
}
```



***

## Auto methods

You have various options for fetching authentication info. If possible, I'd suggest going for the cookie helper option—it demands the least effort once it's set up.

### M-rcus Cookie Helper

Please follow the instructions provided here to install it in your browser

{% embed url="https://github.com/M-rcus/OnlyFans-Cookie-Helper" %}

![image](https://user-images.githubusercontent.com/67020411/230731183-26a43e62-4385-4fd9-aee8-f75a7c2d33cb.png)

With the helper, all you need to do is copy and paste the output from the program.



### Browser Extraction

This method is probably the second simplest. However, not all information can be automatically extracted.&#x20;

You'll still need to manually locate and provide the x-bc header and the User-Agent as demonstrated below.

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/request\_headers.png)

For more details, check out the manual section below.

You won't need to worry about extracting any cookie information with this choice



***

## Manual methods

{% hint style="info" %}
**You can also manually edit auth information in script**
{% endhint %}

With this option, you'll need to manually input all the required information

```json
{
    "auth": {
        "sess": "",
        "auth_id": "",
        "auth_uniq_": "",
        "user_agent": "",
        "x-bc": ""
    }
}
```

It's not too terrible. I'll walk you through how to get this info in the next parts.

#### Step One: Creating the 'auth.json' File

You first need to run the program in order for the `auth.json` file to be created. To run it, simply type `ofscraper` in your terminal and hit enter. Because you don't have an `auth.json` file, the program will create one for you and then ask you to enter some information. Now we need to get that information.

#### Step Two: Getting Your Auth Info

_**If you've already used DIGITALCRIMINAL's OnlyFans script, you can simply copy and paste the auth information from there to here.**_

Go to your [notification area](https://onlyfans.com/my/notifications) on OnlyFans. Once you're there, open your browser's developer tools. If you don't know how to do that, consult the following chart:

| Operating System |      Keys     |
| :--------------: | :-----------: |
|       macOS      | cmd + opt + I |
|      Windows     |  ctrl+shift+I |
|       Linux      |  ctrl+shift+I |

### **1. Getting a valid requests**



Once you have your browser's developer tools open, your screen should look like the following:

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/browser\_tools\_open.png)

Click on the `Network` tab at the top of the browser tools:

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/network\_tab.png)

Then click on `XHR` sub-tab inside of the `Network` tab:

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/xhr\_tab.png)

Once you're inside of the `XHR` sub-tab, refresh the page while you have your browser's developer tools open. After the page reloads, you should see a section titled `init` appear:



![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/init.png)

When you click on `init`, you should see a large sidebar appear. Make sure you're in the `Headers` section:

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/headers.png)

Skip to step 2 if you have found init successfully\
otherwise read the next section

***

{% hint style="info" %}
**If init does not appear use any entry with the domain onlyfans.com**
{% endhint %}

#### **Examples**

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>onlyfans.com</p></figcaption></figure>



You may need to right click the header field to enable the domain column

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

***

### 2. Getting data from requests

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/init.png)



After that, scroll down until you see a subsection called `Request Headers`. You should then see three important fields inside of the `Request Headers` subsection: `Cookie`, `User-Agent`, and `x-bc`

![](https://raw.githubusercontent.com/taux1c/onlyfans-scraper/main/media/request\_headers.png)

Inside of the `Cookie` field, you will see a couple of important bits:

* `sess=`
* `auth_id=`
* `auth_uid_=`

_Your_ `auth_uid_` _will only appear **if you have 2FA (two-factor authentication) enabled**. Also, keep in mind that your_ `auth_uid_` _will have numbers after the final underscore and before the equal sign (that's your auth\_id)._

You need everything _**after**_ the equal sign and everything _**before**_ the semi-colon for all of those bits.

Once you've copied the value for your `sess` cookie, go back to the program, paste it in, and hit enter. Now go back to your browser, copy the `auth_id` value, and paste it into the program and hit enter. Then go back to your browser, copy the `auth_uid_` value, and paste it into the program and hit enter (**leave this blank if you don't use 2FA!!!**).

Once you do that, the program will ask for your user agent. You should be able to find your user agent in a field called `User-Agent` below the `Cookie` field. Copy it and paste it into the program and hit enter.

After it asks for your user agent, it will ask for your `x-bc` token. You should also be able to find this in the `Request Headers` section.

You're all set and you can now use `ofscraper`.
