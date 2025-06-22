# Enable label scan

## **what changed?**

**Version 3.9 introduces a performance optimization to the `--all` command by streamlining label utilization**

* In previous versions, the `--all` command relied on labels primarily to extract data and populate the labels table
* While this functionality remains valuable for specific workflows, it can introduce extend scan times  if you don't require labels in your database
* To address this, Version 3.9 the default is to disable label usage , resulting in a performance improvement for the `--all command`

## adding labels to all

```
ofscraper --posts all,labels
```

## scraping just labels

```
ofscraper --posts labels
```

## shorthands for scraping all posts + labels

<pre><code><strong>ofscraper --posts labels*
</strong></code></pre>

or&#x20;

<pre><code><strong>ofscraper --posts labels+
</strong></code></pre>

## permanently add labels to all

```
override include_labels_all to True
```

{% content-ref url="../../getting-started/advanced-config-options/changing-const.md" %}
[changing-const.md](../../getting-started/advanced-config-options/changing-const.md)
{% endcontent-ref %}
