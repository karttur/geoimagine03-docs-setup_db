---
layout: article
title: general_grant_karttur_v090_sql.json
categories: setup_db
excerpt:  Add db users for handling connections to postgres db
tags:: 
    - jsonsql/general_grant_karttur
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/general grant karttur (setup_db)

###  Add db users for handling connections to postgres db

The json command file <span class='file'>general_grant_karttur_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "grant",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "user": "karttur",
        "command": [
          "GRANT USAGE ON SCHEMA process TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA process TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA process TO karttur;",
          "GRANT USAGE ON SCHEMA system TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA system TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA system TO karttur;",
          "GRANT USAGE ON SCHEMA regions TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA regions TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA regions TO karttur;",
          "GRANT USAGE ON SCHEMA userlocale TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA userlocale TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA userlocale TO karttur;",
          "GRANT USAGE ON SCHEMA ancillary TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA ancillary TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA ancillary TO karttur;",
          "GRANT USAGE ON SCHEMA landsat TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA landsat TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA landsat TO karttur;",
          "GRANT USAGE ON SCHEMA modis TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA modis TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA modis TO karttur;",
          "GRANT USAGE ON SCHEMA sentinel TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA sentinel TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA sentinel TO karttur;",
          "GRANT USAGE ON SCHEMA smap TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA smap TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA smap TO karttur;",
          "GRANT USAGE ON SCHEMA layout TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA layout TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA layout TO karttur;",
          "GRANT USAGE ON SCHEMA climateindex TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA climateindex TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA climateindex TO karttur;",
          "GRANT USAGE ON SCHEMA soilmoisture TO karttur;",
          "GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA soilmoisture TO karttur;",
          "GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA soilmoisture TO karttur;"
        ]
      }
    }
  ]
}
```
