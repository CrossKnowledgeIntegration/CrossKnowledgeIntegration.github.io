---
title: Update info of an administrator
keywords: web service, REST, back office
last_updated: February 27, 2017
tags: 
summary: "Describe the /administrator:put web service"
sidebar: home_sidebar
permalink: rest-bo-administrator-put.html
---

[< Back to commands list](/rest-bo.html#commands)

#### Description

&nbsp; |&nbsp;
--- | -------------
**URL** | API/ADMIN/v1/REST/Administrator/{administrator_login}/
**Method** | PUT
**Header** | API-KEY (ex. 23467C0D36E15C0E1D3B55391C8ED860)

This web service updates an existing administrator with new info

#### Request

Name | Type | Mandatory | Comment
---- | ---- | --------- | --------
administrator_login | string | yes | The administrator login

##### Parameters

Name | Type | Mandatory | Comment
---- | ---- | --------- | --------
entityGuid | string | no | Guid of the entity to attach the administrator to

Sample: 

    {
        "entityGuid": "D0E19488-A8CC-7933-BBE8-0E1E615E7DA9"
    }

#### Response

Name | Type | Comment   | Sample
---- | ---- | --------- | --------
guid | string | Administrator's guid | 7F067C0D36E15C0E1D3B55391C8ED860
login |string | Administrator's login | admin
entityGuid | string | Entity Guid the admnistrator is attached to | D0E19488-A8CC-7933-BBE8-0E1E615E7DA9
_links | array | URI to related object |

##### JSON for verb GET

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "_links": "XXX",
        "value": [
        {
            "guid": "DBC319F9-BF0E-50AA-327E-4A24A2438053",
            "login": "admin",
            "entityGuid": "D0E19488-A8CC-7932-BBE8-0E1E615E8DA9",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Administrator/admin/"
            }
        }]
    }

##### HTTP Codes

Code | Message | Comments
---- | ------- | --------
200 | OK | &nbsp;
401 | Unauthorized | Missing or invalid API-KEY | &nbsp;
400 | Entity does not exist | &nbsp;
400 | Oops, something went wrong | &nbsp;

#### Sample

The sample below updates the administrator **admin** so that he is attached to 
entity **D0E19488-A8CC-7933-BBE8-0E1E615E7DA9**

##### Request

    https://demosite.eu.crossknowledge.com/API/ADMIN/v1/REST/Administrator/admin/
    API-KEY: 7F067C0D36E15C0E1D3B55391C8ED860
    Content-Type: application/json; charset=utf8

    {
        "entityGuid": "D0E19488-A8CC-7944-BBE8-0E1E615E8DA9"
    }  

##### Response

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "value": [
        {
            "guid": "DBC319F9-BF0E-66AA-327E-4A24A2438053",
            "login": "admin",
            "entityGuid": "D0E19488-A8CC-7944-BBE8-0E1E615E8DA9",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Administrator/admin/"
            }
        }],
        "_links": {
            "self": "/API/ADMIN/v1/REST/Administrator/admin/"
        }
    }