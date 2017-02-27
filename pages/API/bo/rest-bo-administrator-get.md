---
title: Generate back office SSO link
keywords: web service, REST, back office
last_updated: February 27, 2017
tags: 
summary: "Describe the /administrator/autoconnectionurl:get web service"
sidebar: home_sidebar
permalink: rest-bo-administrator-get.html
---

[< Back to commands list](/rest-bo.html#commands)

#### Description

&nbsp; |&nbsp;
--- | -------------
**URL** | API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}
**Method** | GET
**Header** | API-KEY (ex. 23467C0D36E15C0E1D3B55391C8ED860)

This web service will create a SSO URL in order to log-in an administrator to the back office. To generate the SSO link, the CKLS check 
if the back office user exists and if he is enabled. 

It does not check user rights and restrictions. 

For example, if a right is missing, the call will successed but the user will not be redirected.

#### Request

Name | Type | Mandatory | Comment
---- | ---- | --------- | --------
administrator_login | string | yes | Login of an existing and enabled administrator (value is not case sensitive)
context_type | string | No (yes if a context_guid is given) | Type of object to redirect: default (default value), training, session, registration or learner
context_guid | string |  No (yes if a context_guid is given) | Guid of object to redirect

#### Response

Name | Type | Comment   | Sample
---- | ---- | --------- | --------
value | string | SSO Url | https://demosite.eu.crossknowledge.com/administration/authentication/admin/6E66DFF6-843A-5F69-036C-1F82FF2D0358

##### JSON for verb GET

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "value": "https://demosite.eu.crossknowledge.com/administration/authentication/admin/6E66DFF6-843A-5F69-036C-1F82FF2D0358"
    }

##### HTTP Codes

Code | Message | Comments
---- | ------- | --------
200 | OK | &nbsp;
401 | Unauthorized | Missing or invalid API-KEY

#### Sample

The sample below retrieves a SSO URL for the administrator **admin** on the training settings page **2481120b-69fd-4fae-a056-738c5a85570c**

##### Request

    GET https://demosite.eu.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl/training/2481120b-69fd-4fae-a056-738c5a85570c
    API-KEY: 7F067C0D36E15C0E1D3B55391C8ED860

##### Response

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "value": "https://demosite.eu.crossknowledge.com/administration/authentication/admin/6E66DFF6-843A-5F69-036C-1F82FF2D0358"
        }
    }