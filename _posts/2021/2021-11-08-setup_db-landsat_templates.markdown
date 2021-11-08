---
layout: article
title: landsat_templates_v090_sql.json
categories: setup_db
excerpt:  Install landsat template table
tags:: 
    - landsat_templates
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# landsat templates (setup_db)

###  Install landsat template table

The json command file <span class='file'>landsat_templates_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "templatescenes",
        "command": [
          "source varchar(8)",
          "product varchar(8)",
          "subtype character(1)",
          "filecat character(1)",
          "proccat varchar(16)",
          "collcat char(2)",
          "collnr smallint",
          "scenenameform varchar(255)",
          "basenameform varchar(255)",
          "scenecompstr varchar(255)",
          "basecompstr varchar(255)",
          "archive varchar(16)",
          "PRIMARY KEY (source,product,collcat,collnr,proccat)"
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
        "table": "templatelayers",
        "command": [
          "source varchar(8)",
          "product varchar(8)",
          "subtype character(1)",
          "filecat character(1)",
          "proccat varchar(16)",
          "dataunit varchar(32)",
          "collcat char(2)",
          "collnr smallint",
          "bandnr smallint",
          "bandcat varchar(16)",
          "band varchar(32)  NOT NULL",
          "prefix varchar(32)  NOT NULL",
          "suffix varchar(32)  NOT NULL",
          "folder varchar(32) NOT NULL",
          "scalefac real",
          "offsetadd  real",
          "measure char(1)",
          "pattern varchar(128) NOT NULL",
          "hdfgrid varchar(32)",
          "celltype varchar(8)",
          "cellnull smallint",
          "fileext varchar(8)",
          "required character(1)",
          "PRIMARY KEY (source, product, collcat, collnr, proccat, band)"
        ]
      }
    }
  ]
}
```
