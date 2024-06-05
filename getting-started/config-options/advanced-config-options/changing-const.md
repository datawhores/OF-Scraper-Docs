# Changing Const Values

***

{% hint style="info" %}
**New in version 3.7**
{% endhint %}

## Where are they

**Default Values:** The default values for constants are read from the `ofscraper/const/values` folder. This folder contains separate files for different types of values

* **Custom Configuration (3.7.1 and above):** Starting from version 3.7.1, you can override default values with custom values by setting the `"custom_values"` key in your configuration file.
* **Environment Variables (3.10 and above):** From version 3.10 onwards, you can also customize values by setting environment variables for the wanted value



## What can be changed

* timeouts for requests
* number of tries for requests
* proxy support
* flags for certain process
* urls used by the program
* and much more



***

## How to customize them

* To change a constant value in the config, you'll need to provide a dictionary for the custom\_values option in advanced\_options where the key is the constant value you want to modify and the value is the new value you'd like to assign to it
* There is no limit to how many variables can be changed

***

## Example

### Syntax is&#x20;

```
Custom_Variable:Value,
Custom_Variable2:Value
```

### In the config

* should be in **advanced\_options**

<pre class="language-markup"><code class="lang-markup">.....
  <a data-footnote-ref href="#user-content-fn-1">"advanced_options"</a>: {
        "code-execution": false,
        "dynamic-mode-default": "deviint",
        "backend": "aio",
        "downloadbars": true,
        "cache-mode": "sqlite",
        "appendlog": false,
        "custom_values": {
            "DISCORD_THREAD_OVERRIDE": false,
            "REMOVE_UNVIEWABLE_METADATA": false,
            "API_DISPLAY": false
        },
        "sanitize_text": false,
        "temp_dir": null,
        "remove_hash_match": false,
        "infinite_loop_action_mode": false,
        "post_download_script": null,
        "disable_auto_after": false,
        "default_user_list": "main",
        "default_black_list": ""
    },
`
</code></pre>

## Limitations

* If you change any **OFSCRAPER\_\*\_LIST value** you will need to provide the new list manually with --user-list or change **default\_user\_list**
* changes in **KEY\_OPTIONS** are not accepted in args
* **configFile** and **configPath** are not changeable

[^1]: 
