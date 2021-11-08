---
layout: article
title: regions_v090_sql.json
categories: setup_db
excerpt:  Install tables that hold regions
tags:: 
    - regions
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# regions (setup_db)

###  Install tables that hold regions

The json command file <span class='file'>regions_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions",
        "table": "regions",
        "command": [
          "system varchar(16)",
          "regioncat varchar(32)",
          "regionid varchar(64)",
          "regiontype char(1)",
          "epsg smallint",
          "ullat double precision",
          "ullon double precision",
          "urlat double precision",
          "urlon double precision",
          "lrlat double precision",
          "lrlon double precision",
          "lllat double precision",
          "lllon double precision",
          "minx double precision",
          "miny double precision",
          "maxx double precision",
          "maxy double precision",
          "PRIMARY KEY (system, regionid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions",
        "table": "defregions",
        "command": [
          "system varchar(16)",
          "regioncat varchar(32) NOT NULL",
          "regionid varchar(64)",
          "regionname varchar(64)",
          "parentid varchar(32) NOT NULL",
          "title TEXT",
          "label TEXT",
          "PRIMARY KEY (system,regioncat,regionid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions",
        "table": "tracts",
        "command": [
          "system varchar(16)",
          "parentid TEXT NOT NULL",
          "tractid TEXT",
          "tractname varchar(64)",
          "regiontype char(1)",
          "creator varchar(32)",
          "owner varchar(32)",
          "title varchar(64)",
          "label varchar(128)",
          "share smallint DEFAULT 5",
          "createdate date DEFAULT CURRENT_DATE",
          "PRIMARY KEY (system,tractid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions",
        "table": "sites",
        "command": [
          "system varchar(16)",
          "siteid TEXT",
          "sitename varchar(64)",
          "owner varchar(32)",
          "tractid TEXT",
          "title TEXT",
          "label TEXT",
          "share smallint DEFAULT 5",
          "createdate date DEFAULT CURRENT_DATE",
          "PRIMARY KEY (system,siteid,tractid,owner)"
        ]
      }
    }
  ]
}
```
