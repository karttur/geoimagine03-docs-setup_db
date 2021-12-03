---
layout: article
title: compositions_export_v090_sql.json
categories: setup_db
excerpt:  Install the tables for defining export compositions
tags:: 
    - jsonsql/compositions_export
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/compositions export (setup_db)

###  Install the tables for defining export compositions

The json command file <span class='file'>compositions_export_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "export",
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
        "schema": "export",
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
        "schema": "export",
        "table": "layer",
        "command": [
          "compid TEXT",
          "source TEXT",
          "product varchar(32)",
          "suffix varchar(64)",
          "acqdatestr varchar(20)",
          "acqdate date",
          "doy smallint",
          "createdate date DEFAULT CURRENT_DATE",
          "locusid TEXT",
          "PRIMARY KEY (compid,source,product,suffix,locusid,acqdatestr)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "export",
        "table": "legend",
        "command": [
          "compid TEXT",
          "source TEXT",
          "product varchar(32)",
          "suffix varchar(64)",
          "scalefac real DEFAULT 1",
          "offsetadd real DEFAULT 0",
          "power real DEFAULT 0",
          "mirror0 char(1) DEFAULT 'N'",
          "two51 char(1) DEFAULT 'N'",
          "two52 char(1) DEFAULT 'N'",
          "two53 char(1) DEFAULT 'N'",
          "two54 char(1) DEFAULT 'N'",
          "two55 char(1) DEFAULT 'N'",
          "palmin smallint",
          "palmax smallint",
          "legmin smallint",
          "legmax smallint",
          "PRIMARY KEY (compid,source,product,suffix)"
        ]
      }
    }
  ]
}
```
