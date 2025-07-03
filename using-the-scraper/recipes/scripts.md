---
description: Example of scripts to change the program behavior
---

# Scripts

{% hint style="danger" %}
All files must end with a .py to be auto-detected  by OF-Scraper as a python file
{% endhint %}

## Naming Scripts

These scripts would be place into the naming\_script section of the config

### rename jpeg to jpg

```
import sys
import json
import pathlib
def main():
    input_json_str = sys.stdin.read()

    # 1. Parse the JSON string into a Python dictionary
    data = json.loads(input_json_str)
    filename=str(pathlib.Path(data["dir"],data["file"]))
    #2  Fix name
    filename=filename.replace("jpeg","jpg").strip()
    #2. Print to stdout for output
    print(filename, file=sys.stdout)
    #3. Print all information data to stderr
    print(filename, file=sys.stderr)
if __name__=="__main__":
    main()


```
