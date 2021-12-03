---
layout: article
title: ease_tilecoords_v090_sql.json
categories: setup_db
excerpt:  Table for EASEGRID 2 tile coordinates
tags:: 
    - jsonsql/ease_tilecoords
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/ease tilecoords (setup_db)

###  Table for EASEGRID 2 tile coordinates

The json command file <span class='file'>ease_tilecoords_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2t",
        "table": "tilecoords",
        "command": [
          "xytile char(6)",
          "xtile smallint",
          "ytile smallint",
          "minx double precision",
          "miny double precision",
          "maxx double precision",
          "maxy double precision",
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
          "PRIMARY KEY (xytile)"
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
        "table": "tilecoords",
        "command": [
          "xytile char(6)",
          "xtile smallint",
          "ytile smallint",
          "minx double precision",
          "miny double precision",
          "maxx double precision",
          "maxy double precision",
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
          "PRIMARY KEY (xytile)"
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
        "table": "tilecoords",
        "command": [
          "xytile char(6)",
          "xtile smallint",
          "ytile smallint",
          "minx double precision",
          "miny double precision",
          "maxx double precision",
          "maxy double precision",
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
          "PRIMARY KEY (xytile)"
        ]
      }
    }
  ]
}
```
