---
layout: article
title: modis_scenes_bands_v090_sql.json
categories: setup_db
excerpt:  Add the table for holding all scenes available at the datapool and tables for local MODIS data holdings
tags:: 
    - modis_scenes_bands
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# modis scenes bands (setup_db)

###  Add the table for holding all scenes available at the datapool and tables for local MODIS data holdings

The json command file <span class='file'>modis_scenes_bands_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "datapooltiles",
        "command": [
          "tileid character(26)",
          "tilefilename character varying(128)",
          "source character varying(32)",
          "product varchar(24)",
          "version character(3)",
          "acqdate date",
          "htile smallint",
          "vtile smallint",
          "hvtile char(6)",
          "PRIMARY KEY (tileid,product,version)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "modis",
        "table": "tiles",
        "command": [
          "tileid character(26)",
          "tilefilename character varying(128)",
          "source character varying(32)",
          "product varchar(24)",
          "version character(3)",
          "acqdate date",
          "doy smallint",
          "folder varchar(16) DEFAULT 'original'",
          "downloaded character(1) DEFAULT 'N'",
          "organized character(1) DEFAULT 'N'",
          "exploded character(1) DEFAULT 'N'",
          "redundant character(1) DEFAULT 'N'",
          "deleted character(1) DEFAULT 'N'",
          "maskstatus character(1) DEFAULT 'N'",
          "htile integer",
          "vtile integer",
          "PRIMARY KEY (tileid,product,version)"
        ]
      }
    }
  ]
}
```
