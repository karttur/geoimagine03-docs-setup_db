---
layout: article
title: system_regions_v090_sql.json
categories: setup_db
excerpt:  Install tables that hold system default regions and categories
tags:: 
    - jsonsql/system_regions
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/system regions (setup_db)

###  Install tables that hold system default regions and categories

The json command file <span class='file'>system_regions_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "regioncats",
        "command": [
          "stratum smallint",
          "regioncat varchar(32)",
          "parentcat varchar(32)",
          "title varchar(128)",
          "label varchar(255)",
          "PRIMARY KEY (regioncat,stratum)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "defregions",
        "command": [
          "regioncat varchar(32) NOT NULL",
          "regionid varchar(64)",
          "regionname varchar(64)",
          "parentid varchar(32) NOT NULL",
          "title TEXT",
          "label TEXT",
          "PRIMARY KEY (regioncat,regionid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "regions",
        "command": [
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
          "PRIMARY KEY (regionid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "regionswrs",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
          "wrs char(1)",
          "dir char(1) DEFAULT 'D'",
          "wrspath smallint",
          "wrsrow smallint",
          "PRIMARY KEY (regionid,wrs,wrspath,wrsrow,dir)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "regionsmodis",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
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
        "schema": "system",
        "table": "regionssentinel",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
          "utmzone integer",
          "mgrsid varchar(3)",
          "PRIMARY KEY (regionid,utmzone,mgrsid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system",
        "table": "regionsease2n",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
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
        "schema": "system",
        "table": "regionsease2s",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
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
        "schema": "system",
        "table": "regionsease2t",
        "command": [
          "regionid varchar(64)",
          "regiontype char(1)",
          "xtile smallint",
          "ytile smallint",
          "PRIMARY KEY (regionid,xtile,ytile)"
        ]
      }
    }
  ]
}
```
