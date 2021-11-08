---
layout: article
title: MODISpolar_v090_sql.json
categories: setup_db
excerpt:  Add tables for MODIS polar datasets
tags:: 
    - MODISpolar
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# MODISpolar (setup_db)

###  Add tables for MODIS polar datasets

The json command file <span class='file'>MODISpolar_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "MODISpolar",
        "table": "daacholdings",
        "command": [
          "daacid character(26)",
          "version smallint",
          "metaurl varchar(64)",
          "serverurl varchar(64)",
          "serverpath varchar(64)",
          "startdate date",
          "enddate date",
          "resolkm smallint",
          "temporal varchar(16)",
          "label TEXT",
          "tgcomment varchar(255)",
          "PRIMARY KEY (daacid,version)"
        ]
      }
    },

    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "modispolar",
        "table": "daacdata",
        "command": [
          "daacid varchar(64)",
          "version character(3)",
          "filename character varying(128)",
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
    }
  ]
}
```
