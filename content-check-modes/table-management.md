# Table Management

## Sorting the table

Click the column labels on the top ![image](https://github.com/datawhores/OF-Scraper/assets/67020411/14ca5b89-c9c1-44bc-936e-db4683f81823)

* First click will be desc
* second click will be asc
* Alternates after



***

## Filtering the table

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/7aba01b5-e768-43aa-ba98-6d85aca4e37e)

The form above contains all the filters. Clicking 'Submit' will apply the selected filters to the form

### Adding filter from table

Click on a cell to heighlight it

enter semicolon: \[ ;] or  apostrophe: \[ ' ]  the table will filter to rows matching that cell value



#### Example

The word 'videos' is highlighted\


<figure><img src="../.gitbook/assets/img1.png" alt=""><figcaption></figcaption></figure>

Once enter semicolon: \[ ;] or  apostrophe: \[ ' ]   is pressed

only cell matching videos will appear

![image](https://github.com/datawhores/OF-Scraper/assets/67020411/11911f08-2e0c-4759-b033-1fcaf40a5e6f)

Furthermore, the forum will also refresh. This cycle continues until you press the reset button.

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
