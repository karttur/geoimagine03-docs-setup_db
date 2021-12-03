---
layout: article
title: modis_daacdata_v090_sql.json
categories: setup_db
excerpt:  Add tables for tiles both online datapool and locally downloaded and processed
tags:: 
    - jsonsql/modis_daacdata
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/modis daacdata (setup_db)

###  Add tables for tiles both online datapool and locally downloaded and processed

The json command file <span class='file'>modis_daacdata_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": true,
      "parameters": {
        "db": "karttur",
        "schema": "modis",
        "table": "daacdata",
        "command": [
          "daacid varchar(64)",
          "version character(3)",
          "tileid character(26)",
          "filename character varying(128)",
          "xtile smallint",
          "ytile smallint",
          "xytile char(6)",
          "acqdate date",
          "doy smallint",
          "downloaded character(1) DEFAULT 'N'",
          "organized character(1) DEFAULT 'N'",
          "exploded character(1) DEFAULT 'N'",
          "redundant character(1) DEFAULT 'N'",
          "deleted character(1) DEFAULT 'N'",
          "maskstatus character(1) DEFAULT 'Y'",
          "PRIMARY KEY (filename)"
        ]
      }
    },
    {
      "processid": "createtable",
      "delete": true,
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
          "xtile integer",
          "ytile integer",
          "PRIMARY KEY (tileid,product,version)"
        ]
      }
    }
  ]
}
```
