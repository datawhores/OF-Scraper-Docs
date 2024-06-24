# Mediatype overwrites

Overwrites allow you to overwrite certain settings based on the 4 mediatypes

```
text
videos
audios
images
```

The following can be changed

<pre><code>- system_free_min
- auto-resume
- file_size_min
- file_size_limit
- temp_dir
- responsetype
- remove_hash_match
- dir_format
- file_format
- textlength
<strong>- date
</strong>- space_replacer
- text_type_default
- truncation_default
- hash
</code></pre>

## Example

```
{"overwrites":
{"photos":{fileformat:"file format specific to photos"}
{"audios":"",
{"text":""
}
```

## Notes

* arguments will always have precedence of overwrites
* If using an argument you can  use --mediatype to target the argument to a specific mediatype such as video
