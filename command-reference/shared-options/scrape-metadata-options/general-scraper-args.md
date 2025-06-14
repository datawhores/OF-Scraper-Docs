---
description: >-
  These options allow you to configure automated actions performed by the
  program and control its background execution
---

# Automation Options

## Background Execution

### -d, --daemon \[argument]

* **Runs:** The program in the background as a daemon process.
* **Argument:** (Optional) Specify the desired interval between program runs (e.g., `-d 3600` for hourly runs).
* **Default behavior:** Without the argument, the program runs once in the foreground.

## Automated Actions

### -a, --action \[argument]

* **Selects:** The automated action to perform on posts.
* **Possible choices:**
  * `like`: Like each post encountered during processing.
  * `unlike`: Unlike each post encountered during processing.
  * `download`: Download media associated with each post encountered during processing.

**Combined actions:** You can combine the `-a` option multiple times to specify multiple actions. For example, `-a like -a download` or `a like,download` would like and download media for each post.

#### **Action Descriptions:**

{% hint style="info" %}
**Like and unlike are limited by rate limiting**
{% endhint %}

* **Like:** Attempts to like each post processed by the program.
* **Unlike:** Attempts to unlike each post processed by the program
* **Download:** Downloads associated media (e.g., images, videos) from each post processed by the program
