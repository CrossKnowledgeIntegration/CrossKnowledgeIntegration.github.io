---
title: REST back office API
keywords: ...
last_updated: December 14, 2016
tags: 
summary: "blah blan"
sidebar: home_sidebar
permalink: rest-bo.html
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

* [/content:get](/rest-bo-content-get.html)
* [/administrator/autoconnectionurl:get](rest-bo-administrator.html)
