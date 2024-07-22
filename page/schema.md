# Schema

## Schemas

The schema may be extended in future versions, but existing columns will remain for backwards compatibility.

### labels

* id INTEGER NOT NULL PRIMARY KEY
* label\_id INTEGER
* name VARCHAR
* type VARCHAR
* post\_id INTEGER
* model\_id INTEGER
* UNIQUE (post\_id, label\_id, model\_id)

### Medias

* id INTEGER NOT NULL PRIMARY KEY
* media\_id INTEGER
* post\_id INTEGER NOT NULL
* link VARCHAR
* directory VARCHAR
* filename VARCHAR
* size INTEGER
* api\_type VARCHAR
* media\_type VARCHAR
* preview INTEGER
* linked BOOL
* downloaded BOOL
* created\_at TIMESTAMP
* posted\_at TIMESTAMP
* duration VARCHAR
* unlocked BOOL
* hash VARCHAR
* model\_id INTEGER
* **UNIQUE (media\_id, model\_id, post\_id)**

### Messages

* id INTEGER NOT NULL PRIMARY KEY
* post\_id INTEGER NOT NULL
* text VARCHAR
* price INTEGER
* paid  BOOLEAN
* archived BOOLEAN
* created\_at TIMESTAMP
* `user_id INTEGER` (May be null)
* `model_id INTEGER` (May be null)
* **UNIQUE (post\_id, model\_id)**

### Models

* **id:** INTEGER NOT NULL PRIMARY KEY
* **model\_id:** INTEGER NOT NULL&#x20;
* **UNIQUE model\_id**



### **Posts**

* **model\_id:** INTEGER
* **created\_at** :TIMESTAMP
* **opened:** BOOLEAN
* **stream:** BOOLEAN
* **pinned:** BOOLEAN
* **archived:** BOOLEAN
* **paid:** INTEGER
* **price:** INTEGER
* **text:** VARCHAR
* **post\_id:** INTEGER NOT NULL
* **id:** INTEGER NOT NULL PRIMARY KEY
* **UNIQUE** (**post\_id**, **model\_id**)

### Stories

* `id INTEGER NOT NULL PRIMARY KEY`
* `post_id INTEGER NOT NULL`
* `text VARCHAR`
* `price INTEGER`
* `paid INTEGER`
* `archived BOOLEAN`
* `created_at TIMESTAMP`
* `model_id INTEGER`
* `UNIQUE (post_id, model_id)`



### &#x20;Products

* **id**: INTEGER NOT NULL PRIMARY KEY&#x20;
* **post\_id**: INTEGER NOT NULL&#x20;
* **model\_id**: INTEGER&#x20;
* **title**: VARCHAR&#x20;
* **created\_at**: TIMESTAMP&#x20;
* **archived**: BOOLEAN&#x20;
* **paid**: INTEGER&#x20;
* **price**: INTEGER
* **text**: VARCHAR&#x20;
* **UNIQUE (post\_id, model\_id)**



### Others

* **`id`**: INTEGER, NOT NULL, PRIMARY KEY
* **`post_id`**: INTEGER, NOT NULL
* **`text`:** VARCHAR
* **`price`:** INTEGER
* **`paid`:** INTEGER
* **`archived`:** BOOLEAN
* **`created_at`:** TIMESTAMP
* **`model_id`:** INTEGER
* **UNIQUE (post\_id, model)**
