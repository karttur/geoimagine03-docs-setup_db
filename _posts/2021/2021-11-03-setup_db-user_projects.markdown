---
layout: article
title: user_projects_v090_sql.json
categories: setup_db
excerpt:  User projects - defines users and user projects
tags:: 
    - user_projects
date: 2021-11-03
modified: 2021-11-03
comments: true
share: true
---

# user projects (setup_db)

###  User projects - defines users and user projects

The json command file <span class='file'>user_projects_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "userprojects",
        "command": [
          "userprojid bigserial",
          "projid TEXT",
          "projname varchar(64) NOT NULL",
          "owner varchar(32) NOT NULL",
          "creator varchar(32) NOT NULL",
          "share smallint DEFAULT 5",
          "title varchar(128)",
          "label varchar(256)",
          "descript TEXT",
          "createdate date DEFAULT CURRENT_DATE",
          "PRIMARY KEY (projid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "projlevels",
        "command": [
          "projlevel TEXT",
          "title varchar(64)",
          "label varchar(128)",
          "PRIMARY KEY (projlevel)"
        ]
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "projlevels",
        "command": {
          "columns": [
            "projlevel","title","label"
          ],
          "values": [
            [
              "'TRANSINDEX'",
              "'Transformed indexing using multiband data'",
              "'Define deterministic model from multiband data using unitary matrix transformation and reference data'"
            ],
            [
              "'STATS'",
              "'Statistical modeling - not implemented'",
              "'Define statistical model from multiband data using unitary matrix transformation and reference data'"
            ],
            [
              "'HYDRO'",
              "'Hydrological model calibration'",
              "'Hydrological model calibration by definition of relation between soil moisture conditions and runoff/evapotranspiration'"
            ],
            [
              "'TCI'",
              "'Topographic conversion/wetness modeling'",
              "'Calibrate function defining soil wetness from topographic conditions and hydrological estimates'"
            ],
            [
              "'ES'",
              "'Expert system rule defintions'",
              "'Calibrate expert rules for mapping local/regional/global conditions'"
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
        "schema": "userlocale",
        "table": "projkeywords",
        "command": [
          "projid TEXT",
          "keyword TEXT",
          "PRIMARY KEY (projid,keyword)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "projancil",
        "command": [
          "projid TEXT",
          "ancilid TEXT",
          "PRIMARY KEY (projid,ancilid)"
        ]
      }
    },
    {
      "processid": "createtable",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "linkprojregion",
        "command": [
          "projid TEXT",
          "regionid varchar(64)",
          "PRIMARY KEY (projid,regionid)"
        ]
      }
    }
  ]
}
```
