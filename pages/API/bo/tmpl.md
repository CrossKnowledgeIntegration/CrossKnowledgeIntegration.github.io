---
title: 
keywords: web service, REST, back office
last_updated: February 27, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: TODO.html
---

[< Back to commands list](/rest-bo.html#commands)

#### Description

&nbsp; |&nbsp;
--- | -------------
**URL** | API/ADMIN/v1/REST/XXX
**Method** | XXX
**Header** | API-KEY (ex. 23467C0D36E15C0E1D3B55391C8ED860)

XXX

#### Request

Here are the parameters:

Name | Type | Mandatory | Comment
---- | ---- | --------- | --------
XXX | string | yes | XXX

#### Response

Here is the response:

Name | Type | Comment   | Sample
---- | ---- | --------- | --------
XXX | string | XXX | XXX
_links | array | URI to related object | XXX

##### JSON for verb GET

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "_links": "XXX"
        "value": [XXX]
    }

##### HTTP Codes

Code | Message | Comments
---- | ------- | --------
200 | OK | &nbsp;
401 | Unauthorized | Missing or invalid API-KEY

#### Sample

XXX

##### Request

    GET https://demosite.eu.crossknowledge.com/API/ADMIN/v1/REST/XXX
    API-KEY: 7F067C0D36E15C0E1D3B55391C8ED860

##### Response

    {
        "message": "OK",
        "success": true,
        "totalCount": XX,
        "count": XX,
        "value": [XX],
        "_links": {
            "self": "/API/ADMIN/v1/REST/XX"
        }
    }