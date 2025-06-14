# Table Management

## Sorting the table

Click the column labels on the top ![image](https://github.com/datawhores/OF-Scraper/assets/67020411/14ca5b89-c9c1-44bc-936e-db4683f81823)

* First click will be desc
* second click will be asc
* Alternates after



***

## Filtering of the table

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* Toggle the form with Ctrl+S
* The filter form  contains fields for all the columns in the table.
* Clicking 'Filter' applies form values to filter the table.

### Adding value  from table

* Click on a cell to heighlight it
* enter semicolon: \[ ;] or  apostrophe: \[ ' ]&#x20;
* &#x20;the matching field in the filter form, will use the value from the cell
* To apply click 'Filter'

#### Example

The table a cell with the word 'videos' is highlighted in the mediatype column\


<figure><img src="../../.gitbook/assets/img1.png" alt=""><figcaption></figcaption></figure>

&#x20;Pressing semicolon (`;`) or apostrophe (\`) confirms your choice and updates the filter form

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Clicking "Filter" applies the changes, showing only videos in the table.



![image](https://github.com/datawhores/OF-Scraper/assets/67020411/11911f08-2e0c-4759-b033-1fcaf40a5e6f)

###

### Reset the table

Click on the reset button. Keep in mind, the program saves the current table information in memory, so it won't fetch new data until you restart it

###

### Example filter by all content with the text dog

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/6f03fbe1-2ad9-4296-9b95-7a4cad874e36)

###

### Additional info about text filter

Searches uses python regex

#### Searching case-senstive

Upper case trigger a case-sensitive search

```
Dog
```

#### Searching for full string match

This will prompt the search to specifically match text that is exactly "dog," rather than text that contains "dog" within it

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/010b2d9a-a841-4b96-85c2-220a1fbecafc)
