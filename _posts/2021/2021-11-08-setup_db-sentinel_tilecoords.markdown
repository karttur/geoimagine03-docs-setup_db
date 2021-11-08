---
layout: article
title: sentinel_tilecoords_v090_sql.json
categories: setup_db
excerpt:  Add the coordinates for sentinel tiles
tags:: 
    - sentinel_tilecoords
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# sentinel tilecoords (setup_db)

###  Add the coordinates for sentinel tiles

The json command file <span class='file'>sentinel_tilecoords_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "tilecoords",
        "command": [
          "mgrs char(5)",
          "EPSG integer",
          "proj4 TEXT",
          "projection TEXT",
          "datum TEXT",
          "utmzone integer",
          "mgrsid varchar(3)",
          "refsize real",
          "reflins integer",
          "refcols integer",
          "ullat double precision",
          "ullon double precision",
          "urlat double precision",
          "urlon double precision",
          "lllat double precision",
          "lllon double precision",
          "lrlat double precision",
          "lrlon double precision",
          "centerlat double precision",
          "centerlon double precision",
          "west double precision",
          "east double precision",
          "north  double precision",
          "south double precision",
          "minx double precision",
          "miny double precision",
          "maxx  double precision",
          "maxy  double precision",
          "centerx double precision",
          "centery double precision",
          "PRIMARY KEY (mgrs)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "sentinel",
        "table": "mgrscoords",
        "command": [
          "mgrs char(5)",
          "west double precision",
          "east double precision",
          "north  double precision",
          "south double precision",
          "minx double precision",
          "miny double precision",
          "maxx  double precision",
          "maxy  double precision",
          "sentinel char(1)",
          "PRIMARY KEY (mgrs)"
        ]
      }
    }
  ]
}
```
