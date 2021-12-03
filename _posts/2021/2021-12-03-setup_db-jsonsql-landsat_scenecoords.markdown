---
layout: article
title: landsat_scenecoords_v090_sql.json
categories: setup_db
excerpt:  Add coordinates for landsat tiles
tags:: 
    - jsonsql/landsat_scenecoords
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/landsat scenecoords (setup_db)

###  Add coordinates for landsat tiles

The json command file <span class='file'>landsat_scenecoords_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": true,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat",
        "table": "scenecoords",
        "command": [
          "wrs smallint",
          "dir char(1)",
          "wrspath smallint",
          "wrsrow smallint",
          "wrspr char(8)",
          "EPSG integer",
          "proj4 TEXT",
          "projection TEXT",
          "datum TEXT",
          "refsize real",
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
          "maxx double precision",
          "maxy double precision",
          "centerx double precision",
          "centery double precision",
          "PRIMARY KEY (wrs,dir,wrspath,wrsrow)"
        ]
      }
    }
  ]
}
```
