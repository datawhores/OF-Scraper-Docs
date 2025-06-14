---
description: >-
  These options allow you to download media from specific URLs or post IDs
  without relying on user lists or other automated selection methods.
---

# Manual Mode Options

## Syntax

```
ofscraper manual [options]
```

### example

```
ofscraper manual --url test
```

## General Options

{% content-ref url="shared-options/common-option-groups/" %}
[common-option-groups](shared-options/common-option-groups/)
{% endcontent-ref %}

## Text

### **-tn, --text** \[argument]

* Specify to  download text with any media tied to that text

### **-tp, --text-only** \[argument]

* Specify to  download only text, skipping any media

## Download Sources

### **-f, --file \[argument]:**&#x20;

Download media from a file containing URLs or post IDs, separated by line breaks.

### **u, --url \[argument]:**

Download media directly from one or more URLs provided as arguments (separate URLs with spaces).

***

**Combining Options:** You can use both `-f` and `-u` in a single command. The program will prioritize URLs from the file first, followed by any URLs specified with `-u`.
