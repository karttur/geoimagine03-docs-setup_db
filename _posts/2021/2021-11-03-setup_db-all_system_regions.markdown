---
layout: article
title: all_system_regions_v090_sql.json
categories: setup_db
excerpt:  Install the region tables for the different systems
tags:: 
    - all_system_regions
date: 2021-11-03
modified: 2021-11-03
comments: true
share: true
---

# all system regions (setup_db)

###  Install the region tables for the different systems

The json command file <span class='file'>all_system_regions_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "sentinel",
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "mgrs char(5)",
          "utm smallint",
          "mgrsid char(3)",
          "PRIMARY KEY (regionid,mgrsid)"
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
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "htile smallint",
          "vtile smallint",
          "PRIMARY KEY (regionid,htile,vtile)"
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
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "wrspath smallint",
          "wrsrow smallint",
          "wrs smallint",
          "dir char(1)",
          "prstr char(8)",
          "PRIMARY KEY (regionid,wrs,dir,wrspath,wrsrow)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2n",
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "xtile smallint",
          "ytile smallint",
          "PRIMARY KEY (regionid,xtile,ytile)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2s",
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "xtile smallint",
          "ytile smallint",
          "PRIMARY KEY (regionid,xtile,ytile)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2t",
        "table": "regions",
        "command": [
          "regionid varchar(64)",
          "regiontype varchar(8)",
          "xtile smallint",
          "ytile smallint",
          "PRIMARY KEY (regionid,xtile,ytile)"
        ]
      }
    }
  ]
}
```
