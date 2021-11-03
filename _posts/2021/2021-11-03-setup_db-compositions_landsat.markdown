---
layout: article
title: compositions_landsat_v090_sql.json
categories: setup_db
excerpt:  Install the tables for defining landsat compositions
tags:: 
    - compositions_landsat
date: 2021-11-03
modified: 2021-11-03
comments: true
share: true
---

# compositions landsat (setup_db)

###  Install the tables for defining landsat compositions

The json command file <span class='file'>compositions_landsat_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat",
        "table": "compdef",
        "command": [
          "compid TEXT",
          "content varchar(32)",
          "layerid varchar(64)",
          "prefix varchar(32)",
          "scalefac real",
          "offsetadd real",
          "measure char(1) NOT NULL",
          "dataunit varchar(32)",
          "title varchar(255)",
          "label varchar(255)",
          "PRIMARY KEY (compid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat",
        "table": "compprod",
        "command": [
          "compid TEXT",
          "system varchar(16) NOT NULL",
          "source TEXT",
          "product varchar(32)",
          "suffix varchar(64)",
          "cellnull real",
          "celltype varchar(8)",
          "masked character(1) DEFAULT 'N'",
          "title varchar(255)",
          "label varchar(255)",
          "frequency varchar(20)",
          "PRIMARY KEY (compid,source,product,suffix)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat",
        "table": "layer",
        "command": [
          "layerid bigserial",
          "compid TEXT",
          "source TEXT",
          "product varchar(32)",
          "suffix varchar(64)",
          "acqdatestr varchar(20)",
          "acqdate date",
          "doy smallint",
          "createdate date DEFAULT CURRENT_DATE",
          "wrspath smallint",
          "wrsrow smallint",
          "wrspr char(8)",
          "PRIMARY KEY (compid, source, product, suffix, wrspath, wrsrow, acqdatestr)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat",
        "table": "mask",
        "command": [
          "source TEXT",
          "product varchar(32)",
          "cellnull smallint",
          "water smallint",
          "cloudshadow smallint",
          "snow smallint",
          "cloud smallint",
          "clear smallint",
          "mask smallint ARRAY[3]",
          "PRIMARY KEY (source,product)"
        ]
      }
    }
  ]
}
```
