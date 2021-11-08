---
layout: article
title: general_GDALtypes_v090_sql.json
categories: setup_db
excerpt:  Install and fill the tables that define the different cell types and file types that the system can handle
tags:: 
    - general_GDALtypes
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# general GDALtypes (setup_db)

###  Install and fill the tables that define the different cell types and file types that the system can handle

The json command file <span class='file'>general_GDALtypes_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

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
        "table": "celltypes",
        "command": [
          "gdal varchar(8)",
          "arr char(1)",
          "np varchar(8)",
          "usgs varchar(8)",
          "PRIMARY KEY (gdal)"
        ]
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "celltypes",
        "command": {
          "columns": [
            "gdal",
            "arr",
            "np",
            "usgs"
          ],
          "values": [
            [
              "'Byte'",
              "'B'",
              "'uint8'",
              "'UINT8'"
            ],
            [
              "'Int16'",
              "'h'",
              "'int16'",
              "'INT16'"
            ],
            [
              "'UInt16'",
              "'H'",
              "'uint16'",
              "'UINT16'"
            ],
            [
              "'Int32'",
              "'l'",
              "'int32'",
              "'INT32'"
            ],
            [
              "'UInt32'",
              "'L'",
              "'uint32'",
              "'UINT32'"
            ],
            [
              "'Float32'",
              "'f'",
              "'float32'",
              "'FLOAT32'"
            ],
            [
              "'Float64'",
              "'d'",
              "'float64'",
              "'FLOAT64'"
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
        "schema": "process",
        "table": "gdalformat",
        "command": [
          "hdr varchar(8)",
		    	"dat varchar(8)",
		    	"gdaldriver varchar(8)",
		    	"PRIMARY KEY (hdr,dat,gdaldriver)"
        ]
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "process",
        "table": "gdalformat",
        "command": {
          "columns": [
            "hdr", "dat", "gdaldriver"
          ],
          "values": [
            [
              "'.tif'",
              "'*'",
              "'GTiff'"
            ],
            [
              "'.ers'",
              "'*'",
              "'ERS'"
            ],
            [
              "'tif'",
              "'*'",
              "'GTiff'"
            ],
            [
              "'ers'",
              "'*'",
              "'ERS'"
            ],
            [
              "'csv'",
              "'*'",
              "'none'"
            ],
            [
              "'xml'",
              "'*'",
              "'none'"
            ],
            [
              "'txt'",
              "'*'",
              "'none'"
            ],
            [
              "'.csv'",
              "'*'",
              "'none'"
            ],
            [
              "'.xml'",
              "'*'",
              "'none'"
            ],
            [
              "'.txt'",
              "'*'",
              "'none'"
            ],
            [
              "'.hdf'",
              "'*'",
              "'HDF4'"
            ],
            [
              "'hdf'",
              "'*'",
              "'HDF4'"
            ],
            [
              "'HDF'",
              "'*'",
              "'HDF4'"
            ],
            [
              "'.HDF'",
              "'*'",
              "'HDF4'"
            ],
            [
              "'lis'",
              "'*'",
              "'GENBIN'"
            ],
            [
              "'.lis'",
              "'*'",
              "'GENBIN'"
            ],
            [
              "'1x1'",
              "'*'",
              "'GENBIN'"
            ],
            [
              "'.1x1'",
              "'*'",
              "'GENBIN'"
            ],
            [
              "'hdr'",
              "'bil'",
              "'bil'"
            ],
            [
              "'.hdr'",
              "'.bil'",
              "'bil'"
            ],
            [
              "'shp'",
              "'*'",
              "'shp'"
            ],
            [
              "'.shp'",
              "'.*'",
              "'shp'"
            ],
            [
              "'adf'",
              "'*'",
              "'AIG'"
            ],
            [
              "'.adf'",
              "'.*'",
              "'AIG'"
            ],
            [
              "'zip'",
              "'*'",
              "'none'"
            ],
            [
              "'.zip'",
              "'.*'",
              "'none'"
            ],
            [
              "'adf'",
              "'*'",
              "'AIG'"
            ],
            [
              "'.adf'",
              "'.*'",
              "'AIG'"
            ],
            [
              "'e00'",
              "'*'",
              "'E00GRID'"
            ],
            [
              "'.e00'",
              "'.*'",
              "'E00GRID'"
            ],
            [
              "'tar.gz'",
              "'*'",
              "'none'"
            ],
            [
              "'.tar.gz'",
              "'.*'",
              "'none'"
            ],
            [
              "'sql'",
              "'*'",
              "'none'"
            ],
            [
              "'.sql'",
              "'.*'",
              "'none'"
            ],
            [
              "'pos'",
              "'csv'",
              "'none'"
            ],
            [
              "'.pos'",
              "'.csv'",
              "'none'"
            ],
            [
              "'asc'",
              "'aai'",
              "'AAIGrid'"
            ],
            [
              "'.asc'",
              "'.aai'",
              "'AAIGrid'"
            ],
            [
              "'.zip'",
              "'.zip'",
              "'none'"
            ],
            [
              "'.tar.bz2'",
              "'.tar.bz2'",
              "'none'"
            ]
          ]
        }
      }
    }
  ]
}
```
