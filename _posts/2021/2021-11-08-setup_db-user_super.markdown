---
layout: article
title: user_super_v090_sql.json
categories: setup_db
excerpt:  Add superusers of the system,
tags:: 
    - user_super
date: 2021-11-08
modified: 2021-11-08
comments: true
share: true
---

# user super (setup_db)

###  Add superusers of the system,

The json command file <span class='file'>user_super_v090_sql.json</span> is part of karttur's GeoImagine project <span class='project'>setup_db</span>. Calling the json file will execute the following commands of the GeoImagine Framework.

```
{
  "process": [
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "users",
        "command": {
          "columns": [
            "userid",
            "userpswd",
            "stratum",
            "usercat"
          ],
          "values": [
            [
              "'inGenkangiSSa'",
              "'jfeo-P9hy4-Oinv-'",
              "10",
              "'super'"
            ],
            [
              "'anvaendarefixaren'",
              "'kjuuY8-O8--oiTu6-Zf'",
              "9",
              "'userfix'"
            ],
            [
              "'karttur'",
              "'weg-iK8-tng-w9k'",
              "10",
              "'super'"
            ]
          ]
        }
      }
    },
    {
      "processid": "tableupdate",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "users",
        "command": {
          "where": "userid = 'inGenkangiSSa'",
          "columns": [
            "usercat",
            "stratum"
          ],
          "values": [
            "'super'",
            "10"
          ]
        }
      }
    },
    {
      "processid": "tableupdate",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "users",
        "command": {
          "where": "userid = 'anvaendarefixaren'",
          "columns": [
            "usercat",
            "stratum"
          ],
          "values": [
            "'userfix'",
            "9"
          ]
        }
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "regions",
        "table": "tracts",
        "command": {
          "columns": [
            "parentid",
            "tractid",
            "tractname",
            "creator",
            "owner",
            "share"
          ],
          "values": [
            [
              "'global'",
              "'karttur'",
              "'Global'",
              "'karttur'",
              "'karttur'",
              "0"
            ],
            [
              "'global'",
              "'globalsuper'",
              "'Global'",
              "'inGenkangiSSa'",
              "'inGenkangiSSa'",
              "0"
            ],
            [
              "'global'",
              "'globalusers'",
              "'Global'",
              "'anvaendarefixaren'",
              "'anvaendarefixaren'",
              "0"
            ]
          ]
        }
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "userprojects",
        "command": {
          "columns": [
            "projid",
            "projname",
            "owner",
            "creator",
            "share",
            "title",
            "label"
          ],
          "values": [
            [
              "'nooneCanGuess'",
              "'nooneCanGuess'",
              "'inGenkangiSSa'",
              "'inGenkangiSSa'",
              "0",
              "'superuser'",
              "'superuser access'"
            ],
            [
              "'userfixer'",
              "'userfixer'",
              "'anvaendarefixaren'",
              "'anvaendarefixaren'",
              "0",
              "'useradministrator'",
              "'useradministrator access'"
            ],
            [
              "'karttur'",
              "'karttur'",
              "'karttur'",
              "'karttur'",
              "0",
              "'karttur super user'",
              "'karttur super user access'"
            ]
          ]
        }
      }
    },
    {
      "processid": "tableinsert",
      "overwrite": false,
      "delete": false,
      "parameters": {
        "db": "karttur",
        "schema": "userlocale",
        "table": "linkprojregion",
        "command": {
          "columns": [
            "projid",
            "regionid"
          ],
          "values": [
            [
              "'karttur'",
              "'karttur'"
            ],
            [
              "'globalsuper'",
              "'nooneCanGuess'"
            ],
            [
              "'globalusers'",
              "'userfixer'"
            ]
          ]
        }
      }
    }
  ]
}
```
