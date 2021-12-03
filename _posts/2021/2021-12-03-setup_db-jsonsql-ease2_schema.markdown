---
layout: article
title: ease2_schema_v090_sql.json
categories: setup_db
excerpt:  Install schema for EASEGRID 2
tags:: 
    - jsonsql/ease2_schema
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/ease2 schema (setup_db)

###  Install schema for EASEGRID 2

The json command file <span class='file'>ease2_schema_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
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
    }
  ]
}
```
