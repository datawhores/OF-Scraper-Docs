---
description: >-
  These options allow you to customize how the program generates filenames for
  downloaded content
---

# Filename Modification Options

## Filename Modification Parameters

### -g, --original

* **Disables:** Truncation of long file paths.
* **Default:** `None` (paths are truncated by default)
* **Use case:** You might want to use this option if you need to preserve the entire original file path for organizational purposes.

### -tt, --text-type \[argument]

* **Sets:** The type of unit used to determine the maximum length of the filename text placeholder
* **Possible choices:**
  * `word`: (default) Splits the filename text placeholder into words and considers word count for truncation.
  * `letter`: Considers the total number of characters in the filename text placeholder for truncation.
* **Example:** With `-tt letter` and `-tl 10`, text placeholder would be truncated to a maximum of 10 characters

### -sr, --space-replacer \[argument] (optional)

* **Replaces:** Spaces in the filename text with the specified character.
* **Default:** `None` (spaces are left as spaces)
* **Use case:** This can be helpful for creating filenames compatible with certain file systems or applications that disallow spaces.
* **Example:** With `-sr _`, spaces would be replaced with underscores (e.g., "This File.txt" becomes "This\_File.txt").

### -tl, --textlength \[argument]

* **Sets:** The maximum length of the filename text placeholder
* **Default:** `None` (no limit on text length)
* **Effect:** Truncates text placeholders that exceed the specified length.
* **Use case:** This is useful for ensuring filenames adhere to character limitations imposed by some file systems, as text placeholders can easily go over OS limits

**Note:**

* These options work together to modify the final filename.
* If truncation occurs, it will be based on the chosen `-tt` type (word or letter) ,the provided `-tl` length, and the current OS
