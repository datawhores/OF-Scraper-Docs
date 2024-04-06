# Enable label scan

## **what changed?**

**Version 3.9 introduces a performance optimization to the `--all` command by streamlining label utilization**

* In previous versions, the `--all` command relied on labels primarily to extract data and populate the labels table
* While this functionality remains valuable for specific workflows, it can introduce extend scan times  if you don't require labels in your database
* To address this, Version 3.9 the default is to disable label usage , resulting in a performance improvement for the `--all command`

## add labels to the arg

```
ofscraper --posts all,labels
```

or&#x20;

```
ofscraper --posts labels
```

## permanently add labels to all

```
override include_labels_all to True
```

