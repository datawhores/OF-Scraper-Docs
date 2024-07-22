# Schema

## Schemas

The schema may be extended in future versions, but existing columns will remain for backwards compatibility.

### labels

* **id:** INTEGER NOT NULL PRIMARY KEY
* **label\_id:** INTEGER
* **name:** VARCHAR
* **type:** VARCHAR
* **post\_id:** INTEGER
* **model\_id:** INTEGER
* **UNIQUE (post\_id, label\_id, model\_id)**

### Medias

* **model\_id**: INTEGER
* **hash**: VARCHAR
* **unlocked**: BOOL
* **duration**: VARCHAR
* **posted\_at**: TIMESTAMP
* **created\_at**: TIMESTAMP
* **downloaded**: BOOL
* **linked**: BOOL
* **preview**: INTEGER
* **media\_type**: VARCHAR
* **api\_type**: VARCHAR
* **size**: INTEGER
* **filename**: VARCHAR
* **directory**: VARCHAR
* **link**: VARCHAR
* **post\_id**: INTEGER NOT NULL
* **media\_id**: INTEGER
* **id**: INTEGER NOT NULL PRIMARY KEY
* **UNIQUE (media\_id, model\_id, post\_id)**

### Messages

* **model\_id:** INTEGER
* **user\_id:**  INTEGER
* **created\_at:**  TIMESTAMP
* **archived:**  BOOLEAN
* **paid:**  BOOLEAN
* **price:**  INTEGER
* **text:**  VARCHAR
* **post\_id:**  INTEGER NOT NULL
* **id:**  INTEGER NOT NULL PRIMARY KEY
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

* **model\_id:**  INTEGER
* **created\_at:**  TIMESTAMP
* **archived:**  BOOLEAN
* **paid:**  INTEGER
* **price:**  INTEGER
* **text:**  VARCHAR
* **post\_id:**  INTEGER NOT NULL
* **id:**  INTEGER NOT NULL PRIMARY KEY
* **UNIQUE (post\_id, model\_id)**



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
