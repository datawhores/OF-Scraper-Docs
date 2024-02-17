# Changing Const Value

{% hint style="info" %}
**New in version 3.7**
{% endhint %}

## Where are they

* Const values are in the ofscraper/const folder&#x20;
* We try to organize them by usage



***

## How to customize them

* To change a constant value in the config, you'll need to provide a dictionary for the custom\_values option in advanced\_options where the key is the constant value you want to modify and the value is the new value you'd like to assign to it

***

## Limitations

* If you change any **OFSCRAPER\_\*\_LIST value** you will need to provide the new list manually with --user-list or change **default\_user\_list**
* changes in **KEY\_OPTIONS** are not accepted in args
* **configFile** and **configPath** are not changable
