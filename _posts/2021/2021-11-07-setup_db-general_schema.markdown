---
layout: article
title: general_schema_v090_sql.json
categories: setup_db
excerpt:  Install the default database schemas
tags:: 
    - general_schema
date: 2021-11-07
modified: 2021-11-07
comments: true
share: true
---

# general schema (setup_db)

###  Install the default database schemas

The json command file <span class='file'>general_schema_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ancillary"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "system"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "landsat"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "sentinel"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "modis"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "specimen"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "topography"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "layout"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "export"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "soilmoisture"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "smap"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "modispolar"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2n"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2s"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2t"
      }
    },
    {
      "processid": "createschema",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "climateindex"
      }
    }
  ]
}
```
