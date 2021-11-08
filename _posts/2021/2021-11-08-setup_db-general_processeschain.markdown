---
layout: article
title: general_processeschain_v090_sql.json
categories: setup_db
excerpt:  Install the automated processing chains tables
tags:: 
    - general_processeschain
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# general processeschain (setup_db)

###  Install the automated processing chains tables

The json command file <span class='file'>general_processeschain_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "prcesschain",
        "command": [
          "chainid TEXT",
          "title TEXT",
          "label TEXT",
          "creator varchar(32)",
          "owner varchar(32)",
          "sharing varchar(8)",
          "createdate date",
          "PRIMARY KEY (chainid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "chainprocess",
        "command": [
          "chainid TEXT",
          "chainstep smallint",
          "subprocid TEXT",
          "version varchar(16)",
          "PRIMARY KEY (chainid,chainstep,subprocid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "chaincompin",
        "command": [
          "chainid TEXT",
          "chainstep smallint",
          "compid varchar(16)",
          "suffix varchar(64)",
          "PRIMARY KEY (chainid,chainstep,compid,suffix)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "chainparams",
        "command": [
          "chainid TEXT",
          "chainstep smallint",
          "parameter varchar(32)",
          "value varchar(64)",
          "PRIMARY KEY (chainid,chainstep,parameter,value)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "chaincompout",
        "command": [
          "chainid TEXT",
          "chainstep smallint",
          "compid varchar(16)",
          "suffix varchar(64)",
          "cellnull integer",
          "celltype varchar(8)",
          "scalefac real",
          "offsetadd integer",
          "dataunit varchar(32)",
          "measure char(1)",
          "PRIMARY KEY (chainid,chainstep,compid,suffix)"
        ]
      }
    }
  ]
}
```
