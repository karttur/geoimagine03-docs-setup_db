---
layout: article
title: climateindexes_v090_sql.json
categories: setup_db
excerpt:  Adds the schema and table for climate indexes
tags:: 
    - climateindexes
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# climateindexes (setup_db)

###  Adds the schema and table for climate indexes

The json command file <span class='file'>climateindexes_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "climateindex",
        "table": "climindex",
        "command": [
          "index TEXT NOT NULL",
          "acqdate date",
          "acqdatestr char(6)",
          "value real",
          "PRIMARY KEY(index,acqdate)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "climateindex",
        "table": "indexmeta",
        "command": [
          "index TEXT NOT NULL",
          "type TEXT NOT NULL",
          "source TEXT NOT NULL",
          "url TEXT NOT NULL",
          "update date",
          "PRIMARY KEY (index)"
        ]
      }
    }
  ]
}
```
