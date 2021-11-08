---
layout: article
title: general_processes_v090_sql.json
categories: setup_db
excerpt:  Install tables for handling paths and processes
tags:: 
    - general_processes
date: 2021-11-07
modified: 2021-11-07
comments: true
share: true
---

# general processes (setup_db)

###  Install tables for handling paths and processes

The json command file <span class='file'>general_processes_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "rootprocesses",
        "command": [
          "rootprocid TEXT",
          "title varchar(128)",
          "label varchar(255)",
          "creator varchar(32)",
          "PRIMARY KEY (rootprocid)"
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
        "table": "subprocesses",
        "command": [
          "rootprocid TEXT",
          "subprocid TEXT",
          "version varchar(16)",
          "minuserstratum integer",
          "title varchar(128)",
          "label varchar(255)",
          "creator varchar(32)",
          "access varchar(8)",
          "createdate date",
          "PRIMARY KEY (subprocid,version)"
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
        "table": "procdiv",
        "command": [
          "subprocid TEXT",
          "division varchar(16)",
          "PRIMARY KEY (subprocid,division)"
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
        "table": "procsys",
        "command": [
          "subprocid TEXT",
          "system varchar(16)",
          "srcsystem varchar(16)",
          "dstsystem varchar(16)",
          "srcdivision varchar(16)",
          "dstdivision varchar(16)",
          "srcepsg integer",
          "dstepsg integer",
          "PRIMARY KEY (subprocid,system,srcsystem,dstsystem,srcdivision,dstdivision)"
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
        "table": "processparams",
        "command": [
          "rootprocid TEXT",
          "subprocid TEXT",
          "version varchar(16)",
          "parent varchar(32)",
          "element varchar(32)",
          "paramid varchar(32)",
          "paramtyp varchar(8)",
          "required BOOL",
          "defaultvalue varchar(32)",
          "hint varchar(255)",
          "bandid varchar(32) DEFAULT 'False'",
          "PRIMARY KEY (subprocid,version,parent,element,paramid,defaultvalue,bandid)"
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
        "table": "processparamsetvalues",
        "command": [
          "rootprocid TEXT",
          "subprocid TEXT",
          "version varchar(16)",
          "parent varchar(32)",
          "element varchar(32)",
          "paramid varchar(32)",
          "value varchar(32)",
          "label varchar(128)",
          "PRIMARY KEY (subprocid,version,parent, element,paramid,value)"
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
        "table": "processparamsetminmax",
        "command": [
          "rootprocid TEXT",
          "subprocid TEXT",
          "version varchar(16)",
          "parent varchar(32)",
          "element varchar(32)",
          "paramid varchar(32)",
          "minval real",
          "maxval real",
          "PRIMARY KEY (subprocid,version,parent,element,paramid)"
        ]
      }
    }
  ]
}
```
