---
layout: article
title: modis_tilecoords_v090_sql.json
categories: setup_db
excerpt:  Add table for MDOIS tile coordinates
tags:: 
    - modis_tilecoords
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# modis tilecoords (setup_db)

###  Add table for MDOIS tile coordinates

The json command file <span class='file'>modis_tilecoords_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "modis",
        "table": "tilecoords",
        "command": [
          "hvtile char(6)",
          "htile smallint",
          "vtile smallint",
          "minxsin double precision",
          "minysin double precision",
          "maxxsin double precision",
          "maxysin double precision",
          "west double precision",
          "south double precision",
          "east double precision",
          "north double precision",
          "ullat double precision",
          "ullon double precision",
          "lrlat double precision",
          "lrlon double precision",
          "urlat double precision",
          "urlon double precision",
          "lllat double precision",
          "lllon double precision",
          "PRIMARY KEY (hvtile)"
        ]
      }
    }
  ]
}
```
