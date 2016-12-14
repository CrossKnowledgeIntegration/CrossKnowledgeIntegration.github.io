---
title: REST back office API
keywords: ...
last_updated: December 14, 2016
tags: 
summary: "blah blan"
sidebar: home_sidebar
permalink: rest_bo.html
folder: API
---

## Usage
The following API is for back office administration and management.

This documentation is also available throught the following link:
http[s]://[instanceUrl].crossknowledge.com/API/ADMIN/doc

### Authentication
To authenticate the call, an API key must be provided in the **HEADER** of the **HTTP** request 
(all verbs). This API key must be provided by your IT consultant.

### Requests format
All calls to the API must follow the structure below:

**http[s]://[instanceUrl].crossknowledge.com/API/ADMIN/v1/REST/[command]**

where:

* **instanceURL**: the URL of your instance (and the protocole, HTTP/HTTPS)
* **command**: any supported commands below

### Responses types
The call request and response are in JSON

### Response structure
All responses are following the JSON structure:
    
    {
        "message": "Some message",
        "success": true|false,
        "totalCount": 1,
        "count": 1,
        "value": {}|[]
    }

where:

* **message**: a message indicating the success or the reason of the failure
* **success**: boolean true or false depending on whether the request has been successfully processed or not
* **count**: an integer indicating the number of results in the current response
* **totalCount**: an integer indicating the total number of results; this number may be different from the count result because of pagination
* **value**: an object or a list of objects containing the data in response to the request

Most of the reponses will contain a propery **_link**. This is a shortcut to linked services

### HTTP response code
If the response is ok, then 200 is returned. if the API-KEY is not provided, or is incorrect, 401 is returned.

Other codes can be returned by specific commands.

## Commands

### /Content:GET
.|.   
------------ | -------------
**URL** | API/ADMIN/v1/REST/Training/{training_guid}/Content/
**Method** | GET
**Header** | API-KEY (ex. 23467C0D36E15C0E1D3B55391C8ED860)

#### Description
This web service returns the learning objects list (pedagogical content) for a given training path.

Please **note** that this service only works so far with "blended", "elearning" and "campus" modalities 

#### Request
Here are the parameters

Name | Type | Mandatory | Comment
---- | ---- | --------- | --------
training_guid | string | yes | The associated training course GUID sent in the URL

#### Response
Name | Type | Comment   | Sample
---- | ---- | --------- | --------
guid | string | GUID of the learning object | 133da3aa-7f95-49e1-83df-27e3986c0fa5
_links | array | URI to related object | /API/ADMIN/v1/REST/Content/2F9B175C-5A14-A709-AB61-3703C7CD5981/

##### JSON for verb GET

    {
        "message": "OK",
        "success": true,
        "totalCount": 1,
        "count": 1,
        "_links": "/API/ADMIN/v1/REST/Training/2F9B175C-5A14-A709-AB61-3703C7CD5981/Content/"
        "value": [
            {
                "guid": "2F9B175C-5A14-A709-AB61-3703C7CD5981",
                "_links": {
                    "self": "/API/ADMIN/v1/REST/Content/2F9B175C-5A14-A709-AB61-3703C7CD5981/"
                }
            },
            {
                "guid": "D076461D-6B29-FD33-9FC2-FFFB9D6AAD4D",
                "_links": {
                    "self": "/API/ADMIN/v1/REST/Content/D076461D-6B29-FD33-9FC2-FFFB9D6AAD4D/"
                }
            }
        ]
    }

##### HTTP Codes

Code | Message | Comments
---- | ------- | --------
200 | OK | &nbsp;
401 | Unauthorized | Missing or invalid API-KEY
204 | no content in the traning | $nbsp;

#### Sample
The sample below retrieves all content (learning objects) for training **1DDD634E-D03B-8AA4-32EC-77EBFE6CC084**

##### Request

    GET https://demosite.eu.crossknowledge.com/API/ADMIN/v1/REST/Training/1DDD634E-D03B-8AA4-32EC-77EBFE6CC084/Content/
    API-KEY: 7F067C0D36E15C0E1D3B55391C8ED860

##### Response

    {
        "message": "OK",
        "success": true,
        "totalCount": 2,
        "count": 2,
        "value": [
            {
                "guid": "5288F68C-8DF9-7CDB-18AE-8CA79A927469",
                "_links": {
                    "self": "/API/ADMIN/v1/REST/Content/5288F68C-8DF9-7CDB-18AE-8CA79A927469/"
                }
            },
            {
                "guid": "0713CFF3-7C40-BA9C-E915-2BF5B884311E",
                "_links": {
                    "self": "/API/ADMIN/v1/REST/Content/0713CFF3-7C40-BA9C-E915-2BF5B884311E/"
                }
            }
        ],
        "_links": {
            "self": "/API/ADMIN/v1/REST/Training/1DDD634E-D03B-8AA4-32EC-77EBFE6CC084/Content/"
        }
    }