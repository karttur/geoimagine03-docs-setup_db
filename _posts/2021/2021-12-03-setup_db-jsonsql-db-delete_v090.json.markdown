---
layout: article
title: db-delete_v090.json
categories: setup_db
excerpt:  Delete the complete database
tags:: 
    - jsonsql/db-delete_v090.json
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/db delete v090.json (setup_db)

###  Delete the complete database

The json command file <span class='file'>db-delete_v090.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "userproject": {
    "userid": "karttur",
    "projectid": "karttur",
    "tractid": "karttur",
    "siteid": "*",
    "plotid": "*",
    "system": "system"
  },
  "period": {
    "timestep": "static"
  },
  "process": [
    {
      "processid": "DeleteDatabase",
      "overwrite": true,
      "version": "0.9",
      "verbose": 2,
      "dstpath": {
        "volume": ".",
        "hdr": "shp",
        "dat": "shp"
      }
    }
  ]
}
```
