# Pre-Install Guide

## Linux

Python is usually pre-installed on Linux systems

## Windows

### Video

{% embed url="https://bunkrr.su/v/scraper-l3eS0Abl.mkv" %}

### Step 1

Start by opening your terminal program



#### Windows Terminal Program i.e command prompt

{% embed url="https://i.ibb.co/809sCyT/03j4-Skzpd-Viq-NKl1b-WPp-Ql-X-2.webp" %}

### Step 2

Verify if Python is installed on your system

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

You'll see something resembling the image below

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

**Doesn't Work**\
Move to step 3

**Version Too old**

You should get an output between 3.10.12 to the latest version of 3.12. If not, proceed to step 3 to upgrade to an appropriate version

\
**Every Okay**

Move to step 4

### Step 3 \[Optional Maybe]

If 'py -3' doesn't work, you'll need to install Python

{% embed url="https://www.python.org/downloads/" %}

#### When Installing

**Make sure to install PIP**

![](<../.gitbook/assets/image (4).png>)

**Make sure to install py launcher**

![](<../.gitbook/assets/image (4).png>)

**Make sure to add to environmental variables**

### ![](<../.gitbook/assets/image (7).png>)



#### Guide

{% embed url="https://www.digitalocean.com/community/tutorials/install-python-windows-10" %}

#### Done

Return to step 2 and retry the process



### step 4

To confirm that pip is installed, return to the terminal and type

```
py -3 -m pip -V
```

You should see a message similar to

```
pip 23.0.1 from /home/john/.local/lib/python3.10/site-packages/pip (python 3.10)

```

### &#x20;step 5

From now on, all actions related to OF-Scraper will take place in the terminal program. Enter any commands you see within the terminal

## MAC&#x20;

###

### Step 1

Start by opening your terminal program

#### Terminal Program

![](<../.gitbook/assets/image (2) (1).png>)

### Step 2

Macs usually come with a pre-installed Python version, but it might be outdated

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

**Doesn't Work**\
Move to step 3

**Version Too old**

You should get an output between 3.10.12 to the latest version of 3.12. If not, proceed to step 3 to upgrade to an appropriate version\


### Step 3

**Manual**

{% embed url="https://www.lifewire.com/how-to-install-python-on-mac-4781318" %}
install python the manual way\

{% endembed %}

**Auto**



{% embed url="https://arpitrana.medium.com/installing-miniconda-on-mac-osx-ac4557a715f7" %}

{% embed url="https://docs.conda.io/en/latest/miniconda.html" fullWidth="false" %}
a more automatic installer
{% endembed %}

step 4

To confirm that pip is installed, return to the terminal and type

```
python3 -m pip -V
```

You should see a message similar to

```
pip 23.0.1 from /home/john/.local/lib/python3.10/site-packages/pip (python 3.10)

```

### &#x20;step 5

From now on, all actions related to OF-Scraper will take place in the terminal program. Enter any commands you see within the terminal.
