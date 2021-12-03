---
layout: article
title: EASE2S_template_v090_sql.json
categories: setup_db
excerpt:  Table for templates EASE GRID south
tags:: 
    - jsonsql/EASE2S_template
date: 2021-12-03
modified: 2021-12-03
comments: true
share: true
---

# jsonsql/EASE2S template (setup_db)

###  Table for templates EASE GRID south

The json command file <span class='file'>EASE2S_template_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "createtable",
      "overwrite": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2s",
        "table": "template",
        "command": [
          "hdffolder varchar(255)",
          "hdfgrid varchar(255)",
          "version varchar(8)",
          "fileext varchar(8)",
          "timestep varchar(16)",
          "title varchar(128)",
          "label varchar(255)",
          "region varchar (32)",
          "epsg bigint",
          "retrieve character(1)",
          "source varchar(32)",
          "product varchar(32)",
          "content varchar(32)",
          "layerid varchar(64)",
          "prefix varchar(32)",
          "suffix varchar(64)",
          "compid TEXT",
          "masked character(1) DEFAULT 'N'",
          "measure char(1)",
          "dataunit varchar(32)",
          "scalefac real",
          "offsetadd real",
          "cellnull bigint",
          "celltype varchar(8)",
          "PRIMARY KEY (source,product,layerid)"
        ]
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "parameters": {
        "db": "karttur",
        "schema": "ease2s",
        "table": "template",
        "command": {
          "columns": [
            "hdffolder",
            "hdfgrid",
            "version",
            "fileext",
            "timestep",
            "title",
            "label",
            "region",
            "epsg",
            "retrieve",
            "source",
            "product",
            "content",
            "layerid",
            "prefix",
            "suffix",
            "compid",
            "masked",
            "measure",
            "dataunit",
            "scalefac",
            "offsetadd",
            "cellnull",
            "celltype"
          ],
          "values": [
            [
              "'MOD_Grid_Seaice_4km_South'",
              "'Sea_Ice_by_Reflectance_SP'",
              "'006'",
              "'tif'",
              "'1D'",
              "'Sea Ice by Reflectance SP'",
              "'Sea Ice by Reflectance SP'",
              "'global'",
              "'6932'",
              "'Y'",
              "'modis'",
              "'MOD29E1D'",
              "'seaice'",
              "'seaice'",
              "'seaice'",
              "'006'",
              "'seaice_seaice'",
              "'N'",
              "'N'",
              "'class'",
              "'1'",
              "'0'",
              "'-1'",
              "'BYTE'"
            ],
            [
              "'MOD_Grid_Seaice_4km_South'",
              "'Ice_Surface_Temperature_SP'",
              "'006'",
              "'tif'",
              "'1D'",
              "'Ice Surface Temperature SP'",
              "'Ice Surface Temperature SP'",
              "'global'",
              "'6932'",
              "'Y'",
              "'modis'",
              "'MOD29E1D'",
              "'seaice'",
              "'icetemp'",
              "'icetemp'",
              "'006'",
              "'seaice_icetemp'",
              "'N'",
              "'R'",
              "'Kelvin'",
              "'1'",
              "'0'",
              "'-1'",
              "'UINT16'"
            ]
          ]
        }
      }
    }
  ]
}
```
