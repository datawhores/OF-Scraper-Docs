# Script Options

### post\_download\_script

A script that runs after  an action for a user has completed

* runs after each model is downloaded in the main scraper
* runs after each model's metadata is processed in metadata mode
* runs after each model is processed in manual mode
* runs for each unique model, after the current cart is downloaded in check mode

### post\_script

A script that runs after all actions for all users have completed

* once all models are downloaded or liked in scrape mode
* once all the post from manual mode are completed
* After the current cart downloads are processed in check mode, and after the download-script is processed for each user
* after all metadata for  all users is processed in metadata mode&#x20;
