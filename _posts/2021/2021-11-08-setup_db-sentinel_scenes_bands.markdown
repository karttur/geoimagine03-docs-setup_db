---
layout: article
title: sentinel_scenes_bands_v090_sql.json
categories: setup_db
excerpt:  Add tables for sentinel scenes, granules bands
tags:: 
    - sentinel_scenes_bands
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# sentinel scenes bands (setup_db)

###  Add tables for sentinel scenes, granules bands

The json command file <span class='file'>sentinel_scenes_bands_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "granules",
        "command": [
          "granuleid TEXT",
          "orbitid varchar(4)",
          "acqdate date",
          "acqtime time",
          "sunazimuth real",
          "sunelevation real",
          "doy smallint",
          "source varchar(32)",
          "product varchar(32)",
          "folder varchar(16)",
          "filetype varchar(8) DEFAULT 'zip'",
          "filename TEXT",
          "downloaded char(1) DEFAULT 'N'",
          "organized char(1) DEFAULT 'N'",
          "exploded char(1) DEFAULT 'N'",
          "deleted char(1) DEFAULT 'N'",
          "declouded char(1) DEFAULT 'N'",
          "maskstatus char(1) DEFAULT 'N'",
          "metacheck char(1) DEFAULT 'N'",
          "tgnote varchar(32) DEFAULT 'None'",
          "PRIMARY KEY (granuleid)"
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
        "table": "granuletiles",
        "command": [
          "granuleid TEXT",
          "mgrs char(5)",
          "overlap real",
          "PRIMARY KEY (granuleid,mgrs)"
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
        "table": "tiles",
        "command": [
          "tileid TEXT",
          "utm char(2)",
          "mgrs char(5)",
          "mgrsid char(3)",
          "orbitid varchar(4)",
          "acqdate date",
          "acqtime time",
          "sunazimuth real",
          "sunelevation real",
          "doy smallint",
          "source varchar(32)",
          "product varchar(32)",
          "folder varchar(16)",
          "filetype varchar(8) DEFAULT 'zip'",
          "filename TEXT",
          "downloaded char(1) DEFAULT 'N'",
          "organized char(1) DEFAULT 'N'",
          "exploded char(1) DEFAULT 'N'",
          "deleted char(1) DEFAULT 'N'",
          "declouded char(1) DEFAULT 'N'",
          "maskstatus char(1) DEFAULT 'N'",
          "metacheck char(1) DEFAULT 'N'",
          "tgnote varchar(32) DEFAULT 'None'",
          "PRIMARY KEY (tileid)"
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
        "table": "tilemeta",
        "command": [
          "tileid TEXT",
          "uuid TEXT",
          "product varchar(16)",
          "proclevel varchar(16)",
          "orbitnr smallint",
          "orbitdir char(1)",
          "cloudcover real DEFAULT -99.0",
          "sensopmode varchar(32)",
          "s2datatakeid varchar(128)",
          "procbase varchar(16)",
          "polmode varchar(16)",
          "platformid varchar(16)",
          "platformname varchar(16)",
          "instrument varchar(16)",
          "PRIMARY KEY (tileid)"
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
        "table": "granulemeta",
        "command": [
          "granuleid TEXT",
          "uuid TEXT",
          "product varchar(16)",
          "proclevel varchar(16)",
          "orbitnr smallint",
          "orbitdir char(1)",
          "cloudcover real DEFAULT -99.0",
          "sensopmode varchar(32)",
          "s2datatakeid varchar(128)",
          "procbase varchar(16)",
          "polmode varchar(16)",
          "platformid varchar(16)",
          "platformname varchar(16)",
          "instrument varchar(16)",
          "PRIMARY KEY (granuleid)"
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
        "table": "metatranslate",
        "command": [
          "src varchar(64)",
          "dst varchar(64)",
          "tab varchar(16)",
          "typ varchar(16)",
          "PRIMARY KEY (src,dst,tab)"
        ]
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "sentinel",
        "table": "metatranslate",
        "command": {
          "columns": [
            "src",
            "dst",
            "tab",
            "typ"
          ],
          "values": [
            [
              "'identifier'",
              "'tileid'",
              "'metatiles'",
              "'string'"
            ],
            [
              "'uuid'",
              "'uuid'",
              "'meta'",
              "'string'"
            ],
            [
              "'relativeorbitnumber'",
              "'orbitnr'",
              "'meta'",
              "'integer'"
            ],
            [
              "'orbitdirection'",
              "'orbitdir'",
              "'meta'",
              "'trunc1'"
            ],
            [
              "'cloudcoverpercentage'",
              "'cloudcover'",
              "'meta'",
              "'real'"
            ],
            [
              "'sensoroperationalmode'",
              "'sensopmode'",
              "'meta'",
              "'string'"
            ],
            [
              "'s2datatakeid'",
              "'s2datatakeid'",
              "'meta'",
              "'string'"
            ],
            [
              "'processingbaseline'",
              "'procbase'",
              "'meta'",
              "'string'"
            ],
            [
              "'processinglevel'",
              "'proclevel'",
              "'meta'",
              "'string'"
            ],
            [
              "'producttype'",
              "'product'",
              "'metatiles'",
              "'string'"
            ],
            [
              "'platformidentifier'",
              "'platformid'",
              "'meta'",
              "'string'"
            ],
            [
              "'platformname'",
              "'platformname'",
              "'meta'",
              "'string'"
            ],
            [
              "'instrumentshortname'",
              "'instrument'",
              "'meta'",
              "'string'"
            ],
            [
              "'polarisationmode'",
              "'polmode'",
              "'meta'",
              "'string'"
            ]
          ]
        }
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "sentinel",
        "table": "vectorsearches",
        "command": [
          "vectorfile TEXT",
          "searchid TEXT",
          "startdate date",
          "enddate date",
          "platformname varchar(16)",
          "product varchar(16)",
          "cloudcover real",
          "PRIMARY KEY (vectorfile, searchid, startdate, enddate, platformname, product)"
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
        "table": "bands",
        "command": [
          "tileid TEXT",
          "source varchar(32)",
          "product varchar(32)",
          "folder char varying(32)",
          "band char varying(32)",
          "prefix char varying(32)",
          "suffix char varying(32)",
          "masked char (1) DEFAULT 'N'",
          "defaultext char varying(8)",
          "filecat char (1) DEFAULT 'B'",
          "cellnull integer",
          "celltype char varying(8)",
          "dataunit char varying(32)",
          "proddate date",
          "status char varying(16) DEFAULT 'unknown'",
          "PRIMARY KEY (tileid,band,product)"
        ]
      }
    }
  ]
}
```
