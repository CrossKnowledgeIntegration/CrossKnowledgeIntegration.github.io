---
title: Administration API Web-services.
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: 18/09, 2017
tags: 
summary: "This API allows to get and set data from external data sources within the CrossKnowledge Learning Suite database for administration purpose."
sidebar: home_sidebar
permalink: api_web_services_list_and_details_admins.html
folder: API web-services List and Details
---

<script>

	$("#toc").hide();

</script>
<style>
table.code_messages td:first-child {
    width: 493px;
    /* font-weight: bold; */
}

.method{
    display: inline;
    padding: 16.2px 15px 14px;
	margin-left: -16px;
	}
.panel-title{

	color: #000;
	font-weight: normal;
	}
div.glossary {
    padding: 10px 5px;
}
div.panel-footer {
	text-align: right;
	}

.panel{
	    width: 900px;
	}
.hljs-string{
    color: #99ffa1;
}
.hljs-built_in{
	color: #ff8d8d;
	}
.hljs-number{	
	color: #ffe564;
	}

</style>
{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;[Learn more about CrossKnowledge Database Objects](/glossary.html)." type="info" %}


<!--GET API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}-->
<div id="offline_administrator_login_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service will creates a SSO URL in order to sign-in an administrator to the back office. To generate the SSO link, the CKLS check only that the user exists and he is enabled. It does not check user rights and restrictions.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}</i></p>

<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a secured single sign-on access url to the CrossKnowledge Learning Suite administration portal.(Back-office)</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">administrator_login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The login of the administrator.</td>
<td markdown="span">richard.roe</td>

</tr>
<tr>
<td markdown="span">context_type</td>
<td markdown="span">string</td>

<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>

<td markdown="span">Database object landing page where to redirect the administrator. <br/>Mandatory if a <b>context_guid</b> is given.
</td>
<td markdown="span" >
One of the following :
default (default value | training | session | registration | learner
</td>

</tr>
<tr>
<td markdown="span">context_guid</td>
<td markdown="span">string</td>

<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>

<td markdown="span">GUID of database object related to the landing page where to redirect the administrator. <br/>Mandatory if a <b>context_type</b> is given.
</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">

GET /API/ADMIN/v1/REST/Admin/richard.roe/AutoConnectionUrl HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXXXX-YYYYYY-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>


<p style="font-size: 15px"><strong>Response: </strong></p>
<p>Returned data: </p>

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">string</td>
<td markdown="span">A string containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>

<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": "https://yourdomain.crossknowledge.com/administration/authentication/admin/..."
}
</code>
</pre>

<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#administrator" class="btn btn-default navbar-btn cursorNorm" role="button">Administrator</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	  <a href="glossary.html#learning_objects" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	<a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_administrator_login_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--PUT API/ADMIN/v1/REST/Administrator/{administrator_login}/-->
<div id="offline_administrator_update_put" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Administrator/{administrator_login}/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service updates the entity of the administrator in the database.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong><i> API/ADMIN/v1/REST/Administrator/{administrator_login}/
</i></p>

<p style="font-size: 15px"><strong>Method : </strong><span class="label label-warning">PUT</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p markdown="span" >This web-service returns a JSON object after the administrator has been successfully updated.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The entity GUID to assign the administrator to.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
PUT /API/ADMIN/v1/REST/Administrator/richard.roe/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

entityGuid=XXXXX-289D-2D56-24DE-AC7140E412AA
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">the administrator GUID</td>
</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span">the administrator login</td>
</tr>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span">the entity GUID of the administrator</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">list of endpoints related to the administrator object</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">current web-service endpoint</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXXXX-11E0-9006-0026B9FD1E70",
            "login": "richard.roe",
            "entityGuid": "XXXXXXX-2D56-24DE-AC7140E412AA",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Administrator/richard.roe/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Administrator/richard.roe/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No administrator found with provided login"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Entity does not exist"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Oops, something went wrong"</td>
<td markdown="span">**403**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>

	  <a href="glossary.html#entity" class="btn btn-default navbar-btn cursorNorm" role="button">Entity</a>
	<a href="glossary.html#administrator" class="btn btn-default navbar-btn cursorNorm" role="button">Administrator</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_administrator_update_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Training/{training_guid}/Content/-->
<div id="offline_training_contents_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Content/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service allows to get the learning objects associated to a given training course.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/Content/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p> This web-service returns a json response with a list of learning objects (content) for the given training.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">training_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training course GUID.</td>
<td></td>
</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Training/XXXXXXX-7A8C-CA0D-B1A5E38F073D/Content/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXXXX-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p> Returned data:</p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the learning object.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">array</td>
<td markdown="span">Array of the web-service endpoints associated of the learning object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service call out endpoint of the learning object.
</td>
</tr>
</tbody>
</table>
<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-6B4F-1AC6-A461-3919BAE58A2C",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Content/XXXX-6B4F-1AC6-A461-3919BAE58A2C/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/Content/"
    }
}
</code>
</pre>



<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>

<tr>
<td markdown="span">"No message: no content in the training"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	<a href="glossary.html#learningObject" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object (content)</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_learning_objects_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Content/{content_guid}/-->
<div id="offline_learning_object_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Content/{content_guid}/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to read the metadatas of a given learning object.</p>
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Content/{content_guid}/
</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the translated metadatas for a given learning object (content).</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">content_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object (content) GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Content/XXXX-6B4F-1AC6-A461-3919BAE58A2C/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>
<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">the content GUID</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">the content type.</td>
</tr>
<tr>
<td markdown="span">subtype</td>
<td markdown="span">string</td>
<td markdown="span">the content subtype.</td>
</tr>
<tr>
<td markdown="span">publisher</td>
<td markdown="span">string</td>
<td markdown="span">the content publisher.</td>
</tr>
<tr>
<td markdown="span">trackingPropagation</td>
<td markdown="span">boolean</td>
<td markdown="span">define is the tracking propagation is enabled on this content.</td>
</tr>
<tr>
<td markdown="span">points</td>
<td markdown="span">integer</td>
<td markdown="span">number of points on the content.</td>
</tr>
<tr>
<td markdown="span">contentVersions</td>
<td markdown="span">object</td>
<td markdown="span">list of localized versions of the content. Each key represents the language code of the content with the learning object metadatas as a value.</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The learning Object GUID.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The learning object title.
</td>
</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span">The learning object code.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">object</td>
<td markdown="span">Thumbnail URI of the learning object.
</td>
</tr>
<tr>
<td markdown="span">version</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object version number.
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object duration (min.).
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The learning publication status.
</td>
</tr>
<tr>
<td markdown="span">authors</td>
<td markdown="span">array</td>
<td markdown="span">The learning object authors <i>name</i> and <i> firstname</i>
</td>
</tr>
<tr>
<td markdown="span">summary</td>
<td markdown="span">string</td>
<td markdown="span">The learning object summary.
</td>
</tr>
<tr>
<tr>
<td markdown="span">whatYouWillLearn</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learning points (what you will learn).
</td>
</tr>
<td markdown="span">included</td>
<td markdown="span">string</td>
<td markdown="span">The learning object included.
</td>
</tr>
<tr>
<td markdown="span">targetAudience</td>
<td markdown="span">string</td>
<td markdown="span">The learning object target audience.
</td>
</tr>
<tr>
<td markdown="span">level</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object level in the library.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">List of web-service endpoint related to the object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoint related to the current object.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXXX-6B4F-1AC6-A461-3919BAE58A2C",
            "type": "Interactive learning resource",
            "subtype": "",
            "publisher": null,
            "trackingPropagation": false,
            "points": null,
            "contentVersions": {
                "en-GB": {
                    "guid": "XXXXXXXX-72CF-9026-57AF-9A24CFE9BE37",
                    "title": "The All-New Jaguar XKR-S",
                    "referenceNumber": "MOHI002",
                    "thumbnail": "https://yourdomain.crossknowledge.com/lo_picture/...",
                    "version": 1,
                    "duration": 30,
                    "status": "V",
                    "authors": [],
                    "summary": "",
                    "whatYouWillLearn": "",
                    "included": "",
                    "targetAudience": "",
                    "level": 0
                },
                "fr-FR": {
                    "guid": "XXXXXXX-D693-45DE-A67E-C899D8B520A2",
                    "title": "La nouvelle Jaguar XKR-S",
                    "referenceNumber": "MOHI002",
                    "thumbnail": "https://yourdomain.crossknowledge.com/lo_picture/...",
                    "version": 1,
                    "duration": 30,
                    "status": "V",
                    "authors": [ {
						  "name": "Doe",
						  "firstName": "John"
						}],
                    "summary": "",
                    "whatYouWillLearn": "",
                    "included": "",
                    "targetAudience": "",
                    "level": 0
                }
            },
            "_links": {
                "self": "/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-XXXXXX/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Content/XXXX-6B4F-1AC6-A461-3919BAE58A2C/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learningObject" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object (content)</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_learning_object_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Training/-->
<div id="offline_training_list" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service allows to get the list of existings trainings within the CrossKnowledge Learning Suite database.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object containing a list of trainings.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}


<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">page</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The page number that should be displayed, based on the limit number.</td>
<td markdown="span">Default: 1</td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Limit to search.</td>
<td markdown="span">Default: 10 | Range >= 50.</td>

</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Type of the training course.</td>
<td>One of the following: <br/>blended | eLearning | guided | learningChannel | knowledgeCommunity | learningFeed | campus
</td>

</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">GUID of the training course to look for	.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Title of the training course to look for (work as a "like" search), will also search in translated titles.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Training path code of the training course to look for.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Status of the training course to look for. Return all the training courses of the specified status.</td>
<td>One of the following:<ul><li>
P (Published)</li>
<li>C (In Construction)</li>
<li>A (Archived)</li></ul></td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Training?status=P HTTP/1.1
Host: yourdomain.jnstaging.crossknowledge.com
API-KEY: XXXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The training GUID.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The training modality.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The training publication status.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The training language.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The training title.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">List of web-service endpoints related to the object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">Current web-service endpoint of the object.
</td>
</tr>


</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 180,
    "count": 2,
    "value": [
        {
            "guid": "B105AE9A-99AD-D5F7-D38D-XXXX",
            "type": "knowledgeCommunity",
            "status": "P",
            "language": "en-GB",
            "title": "Sales Community",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Training/XXXX-99AD-D5F7-D38D-3098DAE628F9/",
                "sessions": "/API/ADMIN/v1/REST/Training/XXXX-99AD-D5F7-D38D-3098DAE628F9/Session/"
            }
        },
        {
            "guid": "ADA5D92B-0FE7-FBE1-9E35-XXXX",
            "type": "campus",
            "status": "P",
            "language": "en-GB",
            "title": "Campus Library",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Training/XXXX-0FE7-FBE1-9E35-44E5257B5C2E/",
                "sessions": "/API/ADMIN/v1/REST/Training/XXXX-0FE7-FBE1-9E35-44E5257B5C2E/Session/"
            }
        }
	]
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Invalid training status: must be P, C or A."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"This type '[type]' is not allowed"	</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Not found"</td>
<td markdown="span">**404**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	     <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>

	 </div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_trainings_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Training/{training_guid}/-->
<div id="offline_training_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to read the metadatas of a given training course.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object of the translated metadatas for a given training course.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">training_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training GUID to look for.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX1</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The modality of the training.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The publication status of the training.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The language of the training.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training.
</td>
</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The code of the training.
</td>
</tr>
<tr>
<td markdown="span">mode</td>
<td markdown="span">string</td>
<td markdown="span">The mode of the training.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">string</td>
<td markdown="span">The thumbnail of the training.
</td>
</tr>
<tr>
<td markdown="span">threshold</td>
<td markdown="span">string</td>
<td markdown="span">The training threshold.
</td>
</tr>
<tr>
<td markdown="span">cost</td>
<td markdown="span">string</td>
<td markdown="span">The training cost.
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">string</td>
<td markdown="span">The training duration.
</td>
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span">The description of the training.
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the welcome text of the training.
</td>
</tr>
<tr>
<td markdown="span">trainingCourseOverview</td>
<td markdown="span">string</td>
<td markdown="span">The trianing overview.
</td>
</tr>
<tr>
<td markdown="span">whoShouldAttend</td>
<td markdown="span">string</td>
<td markdown="span">The training audience.
</td>
</tr>
<tr>
<td markdown="span">furtheInformation</td>
<td markdown="span">string</td>
<td markdown="span">The training detailed information.
</td>
</tr>
<tr>
<td markdown="span">benefits</td>
<td markdown="span">string</td>
<td markdown="span">The training benefits.
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">object</td>
<td>The localized versions of the training.
<table>
		<colgroup>
		<col/>
		<col />
		</colgroup>
		<thead>
		<tr class="header">
		<th>Label</th>
		<th>Type</th>

		<th>Comment</th>

		</tr>
		</thead>
		<tbody>
		
			<tr>
			<td markdown="span">active</td>
			<td markdown="span">boolean</td>
			<td markdown="span">true to activate the language false otherwise (default is false)	
			</td>

			</tr>
			<tr>
			<td markdown="span">title</td>
			<td markdown="span">string</td>
			<td markdown="span">The training title	
			</td>

			</tr>
			<tr>
			<td markdown="span">cost</td>
			<td markdown="span">string</td>
			<td markdown="span">The training cost.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">duration</td>
			<td markdown="span">string</td>
			<td markdown="span">The training duration.	
			</td>

			</tr>
			<tr>
			<td markdown="span">description</td>
			<td markdown="span">string</td>
			<td markdown="span">The training description.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whatYouWillLearn</td>
			<td markdown="span">string</td>
			<td markdown="span">The training learning points.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">trainingCourseOverview</td>
			<td markdown="span">string</td>
			<td markdown="span">The training overview.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whoShouldAttend</td>
			<td markdown="span">string</td>
			<td markdown="span">The training audience.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">furtherInformation</td>
			<td markdown="span">string</td>
			<td markdown="span">The training detailed information.	
			</td>
			</tr>
			<tr>
			<td markdown="span">benefits</td>
			<td markdown="span">string</td>
			<td markdown="span">The training benefits.	
			</td>
			</tr>
			<tr>
			<td markdown="span">welcomeText</td>
			<td markdown="span">string</td>
			<td markdown="span">The training welcome text.	
			</td>
			</tr>
		</tbody>
		</table>

</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-B83E-7A8C-CA0D-B1A5E38F073D",
            "type": "eLearning",
            "status": "P",
            "language": "fr-FR",
            "title": "Découvrez une formation produit Mohive",
            "code": "",
            "mode": "normal",
            "thumbnail": "https://yourdomain.crossknowledge.com/lo_picture/..."
            "cost": "",
            "duration": "",
            "description": "",
            "whatYouWillLearn": "",
            "trainingCourseOverview": "",
            "whoShouldAttend": "",
            "furtherInformation": "",
			"welcomeText":  "<p>Bienvenue!</p>"
			"benefits": "",
            "translations": {
                "en-GB": {
                    "active": false,
                    "title": "",
                    "cost": "",
                    "duration": "",
                    "description": "",
                    "whatYouWillLearn": "",
                    "trainingCourseOverview": "",
                    "whoShouldAttend": "",
                    "furtherInformation": "",
                    "welcomeText": "",
                    "benefits": ""
                },
				...
			},
			"_links": {
                "self": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/",
                "sessions": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/Session/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>

<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"	</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Not Found"	</td>
<td markdown="span">**404**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!-- POST API/ADMIN/v1/REST/Training/-->
<div id="offline_training_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to create a new training.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the translated metadatas of the newly created training</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span"><i title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training modality.	
</td>
<td markdown="span">one of the following: blended | blendedx | eLearning | learningChannel | knowledgeCommunity | learningFeed | campus
</td>	

</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training title	
</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training code.	
</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training publication status.	
</td>
<td markdown="span">One of the following:   C (under construction) | P (published) | A (archived), default is C.
</td> 
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training default code language.	
</td>
<td markdown="span">en-GB, fr-FR ...
</td> 
</tr>
<tr>
<td markdown="span">cost</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training cost.	
</td>
<td markdown="span">20 $.
</td> 
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training duration.	
</td>
<td markdown="span">1 hour and half.
</td> 
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training description.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">whatYouWillLearn</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training learning points.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">trainingCourseOverview</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training overview.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">whoShouldAttend</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training audience.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">furtherInformation</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training detailed information.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">benefits</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training benefits.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training welcome text.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td>The training metadatas translated versions (see parameters below).	
</td>
<td></td>
</tr>
</tbody>
</table>

<b>Translations array parameters:</b>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>

	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">true to activate the language false otherwise (default is false)	
	</td>
	<td markdown="span">true | false
	</td>
	</tr>
	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
	<td markdown="span">The training title	
	</td>
	<td markdown="span">
	</td>
	</tr>
	<tr>
	<td markdown="span">cost</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training cost.	
	</td>
	<td markdown="span">20 $.
	</td> 
	</tr>
	<tr>
	<td markdown="span">duration</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training duration.	
	</td>
	<td markdown="span">1 hour and half.
	</td> 
	</tr>
	<tr>
	<td markdown="span">description</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training description.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">whatYouWillLearn</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training learning points.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">trainingCourseOverview</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training overview.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">whoShouldAttend</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training audience.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">furtherInformation</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training detailed information.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">benefits</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training benefits.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training welcome text.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/ADMIN/v1/REST/Training/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

type=learningChannel&title=Tofu+Fighter!&status=P&cost=300%24&language=en-GB&duration=1h+30.
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The modality of the training.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The publication status of the training.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The language of the training.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training.
</td>
</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The code of the training.
</td>
</tr>
<tr>
<td markdown="span">mode</td>
<td markdown="span">string</td>
<td markdown="span">The mode of the training.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">string</td>
<td markdown="span">The thumbnail of the training.
</td>
</tr>
<tr>
<td markdown="span">threshold</td>
<td markdown="span">string</td>
<td markdown="span">The training threshold.
</td>
</tr>
<tr>
<td markdown="span">cost</td>
<td markdown="span">string</td>
<td markdown="span">The training cost.
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">string</td>
<td markdown="span">The training duration.
</td>
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span">The description of the training.
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the welcome text of the training.
</td>
</tr>
<tr>
<td markdown="span">trainingCourseOverview</td>
<td markdown="span">string</td>
<td markdown="span">The trianing overview.
</td>
</tr>
<tr>
<td markdown="span">whoShouldAttend</td>
<td markdown="span">string</td>
<td markdown="span">The training audience.
</td>
</tr>
<tr>
<td markdown="span">furtheInformation</td>
<td markdown="span">string</td>
<td markdown="span">The training detailed information.
</td>
</tr>
<tr>
<td markdown="span">benefits</td>
<td markdown="span">string</td>
<td markdown="span">The training benefits.
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">object</td>
<td>The localized versions of the training.
<table>
		<colgroup>
		<col/>
		<col />
		</colgroup>
		<thead>
		<tr class="header">
		<th>Label</th>
		<th>Type</th>

		<th>Comment</th>

		</tr>
		</thead>
		<tbody>
	
			<tr>
			<td markdown="span">active</td>
			<td markdown="span">boolean</td>
			<td markdown="span">true to activate the language false otherwise (default is false)	
			</td>

			</tr>
			<tr>
			<td markdown="span">title</td>
			<td markdown="span">string</td>
			<td markdown="span">The training title	
			</td>

			</tr>
			<tr>
			<td markdown="span">cost</td>
			<td markdown="span">string</td>
			<td markdown="span">The training cost.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">duration</td>
			<td markdown="span">string</td>
			<td markdown="span">The training duration.	
			</td>

			</tr>
			<tr>
			<td markdown="span">description</td>
			<td markdown="span">string</td>
			<td markdown="span">The training description.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whatYouWillLearn</td>
			<td markdown="span">string</td>
			<td markdown="span">The training learning points.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">trainingCourseOverview</td>
			<td markdown="span">string</td>
			<td markdown="span">The training overview.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whoShouldAttend</td>
			<td markdown="span">string</td>
			<td markdown="span">The training audience.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">furtherInformation</td>
			<td markdown="span">string</td>
			<td markdown="span">The training detailed information.	
			</td>
			</tr>
			<tr>
			<td markdown="span">benefits</td>
			<td markdown="span">string</td>
			<td markdown="span">The training benefits.	
			</td>
			</tr>
			<tr>
			<td markdown="span">welcomeText</td>
			<td markdown="span">string</td>
			<td markdown="span">The training welcome text.	
			</td>
			</tr>
		</tbody>
		</table>

</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXX-A8D8-CE53-1E4F-F6E245D9DF25",
            "type": "learningChannel",
            "status": "P",
            "language": "en-GB",
            "title": "Tofu Fighter!",
            "code": "",
            "mode": "singleton",
            "thumbnail": "https://yourdomain.crossknowledge.com/training_picture/guid/...",
            "threshold": null,
            "cost": "300$",
            "duration": "1h 30.",
            "description": "",
            "whatYouWillLearn": "",
            "trainingCourseOverview": "",
            "whoShouldAttend": "",
            "furtherInformation": "",
            "welcomeText": "",
            "benefits": "",
            "translations": {
                "en-US": {
                    "active": false,
                    "title": "Vegan Master!",
                    "cost": "",
                    "duration": "",
                    "description": "",
                    "whatYouWillLearn": "",
                    "trainingCourseOverview": "",
                    "whoShouldAttend": "",
                    "furtherInformation": "",
                    "welcomeText": "",
                    "benefits": ""
                },
				...
			},
			"_links": {
                "self": "/API/ADMIN/v1/REST/Training/XXXXX-A8D8-CE53-1E4F-F6E245D9DF25/",
                "sessions": "/API/ADMIN/v1/REST/Training/XXXXX-A8D8-CE53-1E4F-F6E245D9DF25/Session/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Training/XXXXX-A8D8-CE53-1E4F-F6E245D9DF25/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Oops, something went wrong."	</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid training status: must be P, C or A."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"This language doesn't exist."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"This type '%sentType%' is not allowed."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--PUT API/ADMIN/v1/REST/Training/{training_guid}/-->
<div id="offline_training_put" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to update an existing training course.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-warning">PUT</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object of the metadatas of the updated training.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">training_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training GUID to update.	
</td>
<td markdown="span">
</td>	

</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training title	
</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training code.	
</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training publication status.	
</td>
<td markdown="span">One of the following:   C (under construction) | P (published) | A (archived), default is C.
</td> 
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training default code language.	
</td>
<td markdown="span">en-GB, fr-FR ...
</td> 
</tr>
<tr>
<td markdown="span">cost</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training cost.	
</td>
<td markdown="span">20 $.
</td> 
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training duration.	
</td>
<td markdown="span">1 hour and half.
</td> 
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training description.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">whatYouWillLearn</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training learning points.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">trainingCourseOverview</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training overview.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">whoShouldAttend</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training audience.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">furtherInformation</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training detailed information.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">benefits</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training benefits.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The training welcome text.	
</td>
<td markdown="span">
</td> 
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td>The training metadatas translated versions (see parameters below).	

	
</td> 
<td></td>
</tr>
</tbody>
</table>
<b>Translations array parameters :</b>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>

	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">true to activate the language false otherwise (default is false)	
	</td>
	<td markdown="span">true | false
	</td>
	</tr>
	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
	<td markdown="span">The training title	
	</td>
	<td markdown="span">
	</td>
	</tr>
	<tr>
	<td markdown="span">cost</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training cost.	
	</td>
	<td markdown="span">20 $.
	</td> 
	</tr>
	<tr>
	<td markdown="span">duration</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training duration.	
	</td>
	<td markdown="span">1 hour and half.
	</td> 
	</tr>
	<tr>
	<td markdown="span">description</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training description.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">whatYouWillLearn</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training learning points.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">trainingCourseOverview</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training overview.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">whoShouldAttend</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training audience.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">furtherInformation</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training detailed information.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">benefits</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training benefits.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span">The training welcome text.	
	</td>
	<td markdown="span">
	</td> 
	</tr>
</tbody>
</table>
<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
PUT /API/ADMIN/v1/REST/Training/XXXXX-A8D8-CE53-1E4F-F6E245D9DF25/ HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
API-KEY: XXXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache

translations%5Ben-US%5D%5Btitle%5D=Plant+based+fighter!
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of trainings returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The modality of the training.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The publication status of the training.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The language of the training.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training.
</td>
</tr>
<tr>
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The code of the training.
</td>
</tr>
<tr>
<td markdown="span">mode</td>
<td markdown="span">string</td>
<td markdown="span">The mode of the training.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">string</td>
<td markdown="span">The thumbnail of the training.
</td>
</tr>
<tr>
<td markdown="span">threshold</td>
<td markdown="span">string</td>
<td markdown="span">The training threshold.
</td>
</tr>
<tr>
<td markdown="span">cost</td>
<td markdown="span">string</td>
<td markdown="span">The training cost.
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">string</td>
<td markdown="span">The training duration.
</td>
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span">The description of the training.
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the welcome text of the training.
</td>
</tr>
<tr>
<td markdown="span">trainingCourseOverview</td>
<td markdown="span">string</td>
<td markdown="span">The trianing overview.
</td>
</tr>
<tr>
<td markdown="span">whoShouldAttend</td>
<td markdown="span">string</td>
<td markdown="span">The training audience.
</td>
</tr>
<tr>
<td markdown="span">furtheInformation</td>
<td markdown="span">string</td>
<td markdown="span">The training detailed information.
</td>
</tr>
<tr>
<td markdown="span">benefits</td>
<td markdown="span">string</td>
<td markdown="span">The training benefits.
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">object</td>
<td>The localized versions of the training.

<table>
		<colgroup>
		<col/>
		<col />
		</colgroup>
		<thead>
		<tr class="header">
		<th>Label</th>
		<th>Type</th>

		<th>Comment</th>

		</tr>
		</thead>
		<tbody>

			<tr>
			<td markdown="span">active</td>
			<td markdown="span">boolean</td>
			<td markdown="span">true to activate the language false otherwise (default is false)	
			</td>

			</tr>
			<tr>
			<td markdown="span">title</td>
			<td markdown="span">string</td>
			<td markdown="span">The training title	
			</td>

			</tr>
			<tr>
			<td markdown="span">cost</td>
			<td markdown="span">string</td>
			<td markdown="span">The training cost.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">duration</td>
			<td markdown="span">string</td>
			<td markdown="span">The training duration.	
			</td>

			</tr>
			<tr>
			<td markdown="span">description</td>
			<td markdown="span">string</td>
			<td markdown="span">The training description.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whatYouWillLearn</td>
			<td markdown="span">string</td>
			<td markdown="span">The training learning points.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">trainingCourseOverview</td>
			<td markdown="span">string</td>
			<td markdown="span">The training overview.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">whoShouldAttend</td>
			<td markdown="span">string</td>
			<td markdown="span">The training audience.	
			</td>
 
			</tr>
			<tr>
			<td markdown="span">furtherInformation</td>
			<td markdown="span">string</td>
			<td markdown="span">The training detailed information.	
			</td>
			</tr>
			<tr>
			<td markdown="span">benefits</td>
			<td markdown="span">string</td>
			<td markdown="span">The training benefits.	
			</td>
			</tr>
			<tr>
			<td markdown="span">welcomeText</td>
			<td markdown="span">string</td>
			<td markdown="span">The training welcome text.	
			</td>
			</tr>
		</tbody>
		</table>
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXX-A8D8-CE53-1E4F-F6E245D9DF25",
            "type": "learningChannel",
            "status": "P",
            "language": "en-GB",
            "title": "Tofu Fighter!",
            "code": "",
            "mode": "singleton",
            "thumbnail": "https://yourdomain.crossknowledge.com/training_picture/guid/...",
            "threshold": null,
            "cost": "300$",
            "duration": "1h 30.",
            "description": "",
            "whatYouWillLearn": "",
            "trainingCourseOverview": "",
            "whoShouldAttend": "",
            "furtherInformation": "",
            "welcomeText": "",
            "benefits": "",
            "translations": {
                "en-US": {
                    "active": false,
                    "title": "Plant based fighter!",
                    "cost": "",
                    "duration": "",
                    "description": "",
                    "whatYouWillLearn": "",
                    "trainingCourseOverview": "",
                    "whoShouldAttend": "",
                    "furtherInformation": "",
                    "welcomeText": "",
                    "benefits": ""
                },
				...
			},
			"_links": {
                "self": "/API/ADMIN/v1/REST/Training/XXXX-A8D8-CE53-1E4F-F6E245D9DF25/",
                "sessions": "/API/ADMIN/v1/REST/Training/XXXX-A8D8-CE53-1E4F-F6E245D9DF25/Session/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Training/XXXX-A8D8-CE53-1E4F-F6E245D9DF25/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No message: training was not found with the provided training guid	"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Oops, something went wrong."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"This language does not exist.	"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">Invalid training status: must be P, C or A.	</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>

</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Training/{training_guid}/Session/-->
<div id="offline_session_list_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Session/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to read the sessions of a given training course existing within the CrossKnowledge Learning Suite database.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/Session/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the training sessions list.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">training_guid</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the training GUID
</td>
<td markdown="span"> abcdef-12345-XXXXXXX-XXXXXXX1
</td>
</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Training/XXXXXX-B83E-7A8C-CA0D-B1A5E38F073D/Session/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXXXX-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The training session GUID.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The training session language.
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The training session start date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The training session end date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoints related to the current object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 2,
    "count": 2,
    "value": [
        {
            "guid": "XXXX-9499-F0CF-F4413413883C",
            "language": "fr-FR",
            "start": "2012-09-06",
            "end": "",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Session/XXXX-9499-F0CF-F4413413883C/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/"
            }
        },
        {
            "guid": "XXXX-0652-3C4D-908B-8475A9E0D1CD",
            "language": "fr-FR",
            "start": "2015-06-24",
            "end": "",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Session/XXXX-0652-3C4D-908B-8475A9E0D1CD/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/Session/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**</td>
</tr>

</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_sessions_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Session/{session_guid}/-->
<div id="offline_session_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to read the metadatas of a given session.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Session/{session_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the metadatas of the session.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">session_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the training session GUID.</td>
<td>abcdef-12345-XXXXXXX-XXXXXXX1
</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Session/XXXX-E21E-9499-F0CF-F4413413883C/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training session counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The training session GUID.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The training session language.
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The training session start date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The training session end date(YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The training session title.
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">The training session welcome text.
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">object</td>
<td>Object containing the translated metadatas of the training session.
<table>
		<colgroup>
		<col/>
		<col />
		</colgroup>
		<thead>
		<tr class="header">
		<th>Label</th>
		<th>Type</th>
		<th>Comment</th>
		</tr>
		</thead>
		<tbody>
		
			<tr>
			<td markdown="span">active</td>
			<td markdown="span">boolean</td>
			<td markdown="span">true to activate the language false otherwise (default is false)	
			</td>
			</tr>
			<tr>
			<td markdown="span">title</td>
			<td markdown="span">string</td>
			<td markdown="span">translated session title	
			</td>
			</tr>
			<tr>
			<td markdown="span">welcomeText</td>
			<td markdown="span">string</td>
			<td markdown="span">translated session welcome text	
			</td>
			</tr>
		</tbody>
		</table>
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXXX-E21E-9499-F0CF-F4413413883C",
            "language": "en-US",
            "start": "2012-09-06",
            "end": "",
            "title": "Vegan master.",
			"welcomeText": "<p>Helle world!</p>"
            "translations": {
                "en-GB": {
                    "active": false,
                    "title": "",
                    "welcomeText": ""
                },
                "fr-FR": {
                    "active": false,
                    "title": "",
                    "welcomeText": ""
                },
				...
			},
			"_links": {
                "self": "/API/ADMIN/v1/REST/Session/XXXXX-E21E-9499-F0CF-F4413413883C/",
                "training": "/API/ADMIN/v1/REST/Training/XXXXX-B83E-7A8C-CA0D-B1A5E38F073D/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Session/XXXXX-E21E-9499-F0CF-F4413413883C/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>

<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_session_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/ADMIN/v1/REST/Training/{training_guid}/Session/-->
<div id="offline_session_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Session/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to create a new training session to a given training course.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/Session/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the newly created training session metadatas.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the training session title.</td>
<td>Size >= 255
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the start date of the training session.</td>
<td>yyyy-mm-dd
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the end date of the training session.</td>
<td>yyyy-mm-dd
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the welcome text  of the training session (Rich-text allowed).</td>
<td>
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the training session translated information (title and welcome text) indexed by code language (see parameters below).</td>
<td>
</td>
</tr>
</tbody>
</table>
<b>Translations array parameters :</b>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>

	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span"> the training session activation.</td>
	<td>
	true | false
	</td>
	</tr>
	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
	<td markdown="span">The training session translated title	
	</td>
	<td markdown="span">
	</td>
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span"> the training session translated welcome text.</td>
	<td>
	</td>
	</tr>
</tbody>
</table>


<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/ADMIN/v1/REST/Training/XXXX-C3E7-53FD-A8E8-B300FEE8EE68/Session/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

title=Tofu+Fighter!&start=2017-09-27&end=2018-09-27
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The training session GUID.</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The training session code language.</td>
</tr>

<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The training session start date.</td>
</tr>

<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The training session end date .</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the training session welcome text.</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td>object</td>
<td>The training session metadatas translated versions.
	<table>
	<colgroup>
	<col/>
	<col />
	</colgroup>
	<thead>
	<tr class="header">
	<th>Label</th>
	<th>Type</th>
	<th>Comment</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span">Define if the translated version is active or not.</td>
	</tr>

	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span">The training session title .</td>
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span">the training session welcome text.</td>
	</tr>
	</tbody>
	</table>
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXX-4C9D-DE71-6B13-FAEBB13B5E21",
            "language": "fr-FR",
            "start": "2017-09-27",
            "end": "2018-09-27",
            "title": "Tofu Fighter!",
            "welcomeText": "",
            "translations": {
                "en-GB": {
                    "active": true,
                    "title": "How to be a Vegan Master!",
                    "welcomeText": "Hello young Veganwan!"
                },
				...
			}
			"_links": {
                "self": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-C3E7-53FD-A8E8-B300FEE8EE68/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No message: training was not found with the provided training GUID	"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Training has singleton session, can't add or update new session.	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"This date must be greater than "%begindate%".	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Training course declarative status is set to Active. Sessions cannot be added when a training course is not published.	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Oops, something went wrong."</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**</td>
</tr>

</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_session_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--PUT API/ADMIN/v1/REST/Session/{session_guid}/-->
<div id="offline_session_put" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to update a given training session information.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Session/{session_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-warning">PUT</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the updated training session information.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">session_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the training session GUID.</td>
<td>
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the training session title.</td>
<td>Size >= 255
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the start date of the training session.</td>
<td>yyyy-mm-dd
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the end date of the training session.</td>
<td>yyyy-mm-dd
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the welcome text  of the training session (Rich-text allowed).</td>
<td>
</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span"> the training session translated information indexed by code language.</td>
<td>
</td>
</tr>
</tbody>
</table>

<b>Translations array parameters :</b>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>

	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span"> the training session activation.</td>
	<td>
	true | false
	</td>
	</tr>
	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
	<td markdown="span">The training session translated title	
	</td>
	<td markdown="span">
	</td>
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
	<td markdown="span"> the training session translated welcome text.</td>
	<td>
	</td>
	</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
PUT /API/ADMIN/v1/REST/Session/XXXXX-DE71-6B13-FAEBB13B5E21/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

title=Tofu+Fighter!&start=2017-09-27&end=2018-10-31
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The training session GUID.</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The training session code language.</td>
</tr>

<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The training session start date.</td>
</tr>

<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The training session end date .</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the training session welcome text.</td>
</tr>
<tr>
<td markdown="span">translations</td>
<td>object</td>
<td>The trainig session metadatas translated versions.
	<table>
	<colgroup>
	<col/>
	<col />
	</colgroup>
	<thead>
	<tr class="header">
	<th>Label</th>
	<th>Type</th>
	<th>Comment</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	<td markdown="span">active</td>
	<td markdown="span">boolean</td>
	<td markdown="span">Define if the translated version is active or not.</td>
	</tr>

	<tr>
	<td markdown="span">title</td>
	<td markdown="span">string</td>
	<td markdown="span">The training session title .</td>
	</tr>
	<tr>
	<td markdown="span">welcomeText</td>
	<td markdown="span">string</td>
	<td markdown="span">the training session welcome text.</td>
	</tr>
	</tbody>
	</table>
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-4C9D-DE71-6B13-FAEBB13B5E21",
            "language": "fr-FR",
            "start": "2017-09-27",
            "end": "2018-10-31",
            "title": "Tofu Fighter!",
            "welcomeText": "",
            "translations": {
                "en-GB": {
                    "active": true,
                    "title": "How to be a Vegan Master!",
                    "welcomeText": "Hello young Veganwan!"
                },
				...
			}
			"_links": {
                "self": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-C3E7-53FD-A8E8-B300FEE8EE68/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No message: training was not found with the provided training GUID	"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Training has singleton session, can't add or update new session.	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"This date must be greater than "%begindate%".	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Training course declarative status is set to Active. Sessions cannot be added when a training course is not published.	"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Oops, something went wrong."</td>
<td markdown="span">**400**</td>
</tr>

<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_session_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>



<!--POST API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/-->
<div id="offline_training_session_register_learner_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to register a learner to a give training session.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the registration information.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">session_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the training session GUID.
</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX
</td>
</tr>
<tr>
<td markdown="span">learner_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the learner GUID.
</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX
</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/ADMIN/v1/REST/Session/XXXX-0652-3C4D-908B-8475A9/Register/XXXX-47C3-CD84-A35C-8AB862/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the registration.
</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training session.
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training.
</td>
</tr>
<tr>
<td markdown="span">learnerGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.
</td>
</tr>
<tr>
<td markdown="span">registrationDate</td>
<td markdown="span">string</td>
<td markdown="span">The registration date.
</td>
</tr>
<tr>
<td markdown="span">firstLaunchDate</td>
<td markdown="span">string</td>
<td markdown="span">The first access date to the registration.
</td>
</tr>
<tr>
<td markdown="span">lastAccessDate</td>
<td markdown="span">string</td>
<td markdown="span">The last access date to the training.
</td>
</tr>
<tr>
<td markdown="span">completionDate</td>
<td markdown="span">string</td>
<td markdown="span">The first completion date of the training.
</td>
</tr>
<tr>
<td markdown="span">timespent</td>
<td markdown="span">integer</td>
<td markdown="span">The learner time spent (seconds) in the training session.
</td>
</tr>
<tr>
<td markdown="span">progress</td>
<td markdown="span">integer</td>
<td markdown="span">The learner progression in the training session.
</td>
</tr>
<tr>
<td markdown="span">progressMandatory</td>
<td markdown="span">integer</td>
<td markdown="span">The learner progression in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">integer</td>
<td markdown="span">The learner score in the training session.
</td>
</tr>
<tr>
<td markdown="span">progressStatus</td>
<td markdown="span">string</td>
<td markdown="span">The learner status in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">points</td>
<td markdown="span">integer</td>
<td markdown="span">The learner points in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoints related to the current object (registration).
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of to the current object (registration).
</td>
</tr>
<tr>
<td markdown="span">session</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the trainnig session related to the registration.
</td>
</tr>
<tr>
<td markdown="span">training</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the trainnig related to the registration.
</td>
</tr>
<tr>
<td markdown="span">learner</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the learner related to the registration.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-A9D0-B239-F091-344F27E0A49A",
            "sessionGuid": "XXXX-0652-3C4D-908B-8475A9E0D1CD",
            "trainingGuid": "XXXX-B83E-7A8C-CA0D-B1A5E38F073D",
            "learnerGuid": "XXXX-47C3-CD84-A35C-8AB8622AFCE6",
            "registrationDate": "2017-09-27 14:01:23",
            "firstLaunchDate": null,
            "lastAccessDate": null,
            "completionDate": null,
            "timeSpent": 0,
            "progress": 0,
            "progressMandatory": 0,
            "score": 0,
            "progressStatus": "N",
            "points": null,
            "_links": {
                "self": "/API/ADMIN/v1/REST/Registration/XXXX-A9D0-B239-F091-344F27E0A49A/",
                "session": "/API/ADMIN/v1/REST/Session/XXXX-0652-3C4D-908B-8475A9E0D1CD/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-B83E-7A8C-CA0D-B1A5E38F073D/",
                "learner": "/API/ADMIN/v1/REST/Learner/XXXX-47C3-CD84-A35C-8AB8622AFCE6/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Registration/XXXX-A9D0-B239-F091-344F27E0A49A/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#registration" class="btn btn-default navbar-btn cursorNorm" role="button">Registration</a>
		 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking</a>
 
		 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_training_session_register_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Registration/{registration_guid}/Report/
<div id="offline_regsitration_report_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Registration/{registration_guid}/Report/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the report related to registration.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Registration/{registration_guid}/Report/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the endpoint of each report the given registration</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">registration_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">the registration GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">

</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of report existing in the database.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of report returned by the web-service call out.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">the report GUID.
</td>
</tr>
<tr>
<td markdown="span">value._links</td>
<td markdown="span">object</td>
<td markdown="span">An object of report and context web-service endpoint.
</td>
</tr>
<tr>
<td markdown="span">_links.self</td>
<td markdown="span">string</td>
<td markdown="span">the report web-service endpoint.
</td>
</tr>
<tr>
<td markdown="span">_links.session</td>
<td markdown="span">string</td>
<td markdown="span">the session's report web-service endpoint.
</td>
</tr>
<tr>
<td markdown="span">_links.training</td>
<td markdown="span">string</td>
<td markdown="span">the training's report web-service endpoint.
</td>
</tr>
<tr>
<td markdown="span">_links.learner</td>
<td markdown="span">string</td>
<td markdown="span">the learner's report web-service endpoint.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">array</td>
<td markdown="span">An array of object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint.
</td>
</tr>

</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">

  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (report)</a>
	 <a href="glossary.html#registration" class="btn btn-default navbar-btn cursorNorm" role="button">Registration</a>

	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_registration_report_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>-->


<!--GET API/ADMIN/v1/REST/Registration/{registration_guid}/-->
<div id="offline_registration_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Registration/{registration_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to get a given registration information</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Registration/{registration_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the registration data.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">registration_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The registration GUID. </td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Registration/XXXX-5D10-3E39-9247-92E9A/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the registration.
</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training session.
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training.
</td>
</tr>
<tr>
<td markdown="span">learnerGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.
</td>
</tr>
<tr>
<td markdown="span">registrationDate</td>
<td markdown="span">string</td>
<td markdown="span">The registration date.
</td>
</tr>
<tr>
<td markdown="span">firstLaunchDate</td>
<td markdown="span">string</td>
<td markdown="span">The first access date to the registration.
</td>
</tr>
<tr>
<td markdown="span">lastAccessDate</td>
<td markdown="span">string</td>
<td markdown="span">The last access date to the training.
</td>
</tr>
<tr>
<td markdown="span">completionDate</td>
<td markdown="span">string</td>
<td markdown="span">The first completion date of the training.
</td>
</tr>
<tr>
<td markdown="span">timespent</td>
<td markdown="span">integer</td>
<td markdown="span">The learner time spent (seconds) in the training session.
</td>
</tr>
<tr>
<td markdown="span">progress</td>
<td markdown="span">integer</td>
<td markdown="span">The learner progression in the training session.
</td>
</tr>
<tr>
<td markdown="span">progressMandatory</td>
<td markdown="span">integer</td>
<td markdown="span">The learner progression in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">integer</td>
<td markdown="span">The learner score in the training session.
</td>
</tr>
<tr>
<td markdown="span">progressStatus</td>
<td markdown="span">string</td>
<td markdown="span">The learner status in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">points</td>
<td markdown="span">integer</td>
<td markdown="span">The learner points in the training session for mandatory contents.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoints related to the current object (registration).
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of to the current object (registration).
</td>
</tr>
<tr>
<td markdown="span">session</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the trainnig session related to the registration.
</td>
</tr>
<tr>
<td markdown="span">training</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the trainnig related to the registration.
</td>
</tr>
<tr>
<td markdown="span">learner</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the learner related to the registration.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-5D10-3E39-9247-92E9A53222B2",
            "sessionGuid": "XXXX-4C9D-DE71-6B13-FAEBB13B5E21",
            "trainingGuid": "XXXX-C3E7-53FD-A8E8-B300FEE8EE68",
            "learnerGuid": "XXXX-47C3-CD84-A35C-8AB8622AFCE6",
            "registrationDate": "2017-09-27 13:59:14",
            "firstLaunchDate": null,
            "lastAccessDate": null,
            "completionDate": null,
            "timeSpent": 0,
            "progress": 0,
            "progressMandatory": 0,
            "score": 0,
            "progressStatus": "N",
            "points": null,
            "_links": {
                "self": "/API/ADMIN/v1/REST/Registration/XXXX-5D10-3E39-9247-92E9A53222B2/",
                "session": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-C3E7-53FD-A8E8-B300FEE8EE68/",
                "learner": "/API/ADMIN/v1/REST/Learner/XXXX-47C3-CD84-A35C-8AB8622AFCE6/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Registration/XXXX-5D10-3E39-9247-92E9A53222B2/"
    }
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#registration" class="btn btn-default navbar-btn cursorNorm" role="button">Registration</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Report)</a>

	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_registration_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--DELETE API/ADMIN/v1/REST/Registration/{registration_guid}/-->
<div id="offline_registration_delete" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Registration/{registration_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to delete a given registration object.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Registration/{registration_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-danger">DELETE</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object in response of the delete action.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">registration_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">the registration GUID.</td>
<td markdown="span"> abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
DELETE /API/ADMIN/v1/REST/Registration/XXXX-A9D0-B239-F091-344F27E0A49A/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<p>No return.</p>

<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>

</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#learningObject" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Report)</a>
	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_registration_delete" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Learner/-->
<div id="offline_learner_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to search for a learner profile or to list all learners information.</p>
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learner profile information.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">page</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The page number that should be displayed, based on the limit number	</td>
<td markdown="span">Default : 1</td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Max number of record to search.</td>
<td markdown="span">Default: 10 Max: 50</td>

</tr>

<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner login.</td>
<td markdown="span">richard.roe</td>

</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner reference number.</td>
<td markdown="span">abc123</td>

</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner lastname.</td>
<td markdown="span">Roe</td>

</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner firstname.</td>
<td markdown="span">Richard</td>

</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner email.</td>
<td markdown="span">richard.roe@veganmaster.com</td>

</tr>
<tr>
<td markdown="span">entityguid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner entity GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">enabled</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner status.</td>
<td markdown="span">true (active) | false (inactive)</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Learner/?name=doe&amp;enabled=true HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners accounts counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners accounts returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.
</td>
</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span">The learner login.
</td>
</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span">The learner reference number.
</td>
</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span">The learner lastname.
</td>
</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span">The learner firstname.
</td>
</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span">The learner email.
</td>
</tr>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner entity GUID.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type (in the example below i for Interactive content).
</td>
</tr>
<tr>
<td markdown="span">enabled</td>
<td markdown="span">string</td>
<td markdown="span">The learner status.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoints related to the current object (learner).
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoint of the current object (learner).
</td>
</tr>
<tr>
<td markdown="span">registrations</td>
<td markdown="span">integer</td>
<td markdown="span">The web-service enpoint of the registrations of the learner.
</td>
</tr>
<tr>
<td markdown="span">first</td>
<td markdown="span">string</td>
<td markdown="span">The web-service enpoint of the search result first page.
</td>
</tr>
<tr>
<td markdown="span">last</td>
<td markdown="span">string</td>
<td markdown="span">The web-service enpoint of the search result last page.
</td>
</tr>

</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-FA8B-9DCA-0490-EFC90A0A4A9D",
            "login": "john.doe@veganmaster.com",
            "referenceNumber": "Do not delete",
            "name": "Doe",
            "firstName": "John",
            "email": "john.doe@veganmaster.com",
            "entityGuid": "XXXX-E3C0-578F-4EE4-F39B406097E5",
            "enabled": true,
            "_links": {
                "self": "/API/ADMIN/v1/REST/Learner/XXXX-FA8B-9DCA-0490-EFC90A0A4A9D/",
                "registrations": "/API/ADMIN/v1/REST/Learner/XXXX-FA8B-9DCA-0490-EFC90A0A4A9D/Registration/"
            }
        }
    ],
    "_links": {
        "first": "/API/ADMIN/v1/REST/Learner/?limit=10&page=1",
        "last": "/API/ADMIN/v1/REST/Learner/?limit=10&page=1",
        "self": "/API/ADMIN/v1/REST/Learner/?name=doe&enabled=true"
    }
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"enabled is not a boolean"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">" "page" : this value should be a valid number."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">" "limit" : this value should be 1 or more."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**404**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>

</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_learner_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/ADMIN/v1/REST/Learner/-->
<div id="offline_learner_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to create a new learner.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the newly created learner information.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>


<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">the learner login.</td>
<td markdown="span">richard.roe</td>

</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner reference number.</td>
<td markdown="span">abc123</td>

</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner lastname.</td>
<td markdown="span">Roe</td>

</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner firstname.</td>
<td markdown="span">Richard</td>

</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner email.</td>
<td markdown="span">richard.roe@veganmaster.com</td>

</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner (code) language.</td>
<td markdown="span">en-GB</td>

</tr>
<tr>
<td markdown="span">entityguid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner entity GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner status.</td>
<td markdown="span">Y (active) | D (inactive) | U (active between two dates "start" - "end")</td>

</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner activation date.</td>
<td markdown="span">yyyy-mm-dd</td>

</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner deactivation date.</td>
<td markdown="span">yyyy-mm-dd</td>

</tr>
<tr>
<td markdown="span">customFields</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner custom fields (only string and integer custom field type allowed).</td>
<td markdown="span">customFields['guid']='value'</td>

</tr>
<tr>
<td markdown="span">presentation</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner presentation.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">web</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner web-site(portfolio).</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">twitter</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner twitter profile.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">linkedIn</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner linked in profile.</td>
<td markdown="span"></td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/ADMIN/v1/REST/Learner/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

login=richard.roe%40tofufighter.com&name=Roe&firstname=Richard&status=U&start=2017-09-20&end=2017-09-29
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.
</td>
</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span">The learner login.
</td>
</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span">The learner reference number.
</td>
</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span">The learner lastname.
</td>
</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span">The learner firstname.
</td>
</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span">The learner email.
</td>
</tr>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner entityGuid.
</td>
</tr>
<tr>
<td markdown="span">enabled</td>
<td markdown="span">true</td>
<td markdown="span">The learner account status.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The learner code language.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The learner account status type.
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The learner activation start date.
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The learner activation end date.
</td>
</tr>
<tr>
<td markdown="span">customFields</td>
<td markdown="span">object</td>
<td markdown="span">The learner account custom fields.
</td>
</tr>
<tr>
<td markdown="span">presentation</td>
<td markdown="span">string</td>
<td markdown="span">The learner presentation.
</td>
</tr>
<tr>
<td markdown="span">web</td>
<td markdown="span">string</td>
<td markdown="span">The learner portfolio.
</td>
</tr>
<tr>
<td markdown="span">twitter</td>
<td markdown="span">string</td>
<td markdown="span">The learner twitter profile.
</td>
</tr>
<tr>
<td markdown="span">linkedIn</td>
<td markdown="span">string</td>
<td markdown="span">The learner linked in profile.
</td>
</tr>
<tr>
<td markdown="span">points</td>
<td markdown="span">integer</td>
<td markdown="span">The learner points number.
</td>
</tr>
<tr>
<td markdown="span">badges</td>
<td markdown="span">integer</td>
<td markdown="span">The learner badges number.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">string</td>
<td markdown="span">The web-services endpoints related to the current object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object.
</td>
</tr>
<tr>
<td markdown="span">registrations</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the learner registrations.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXX-D5B3-6C3C-13E7-D0413EA98F49",
            "login": "richard.roe@tofufighter.com2",
            "referenceNumber": "",
            "name": "Roe",
            "firstName": "",
            "email": "richard.roe@tofufighter.com",
            "entityGuid": "XXXX-E3C0-578F-4EE4-F39B406097E5",
            "enabled": true,
            "language": "en-GB",
            "status": "U",
            "start": "2017-09-20",
            "end": "2017-09-29",
            "customFields": {
                "XXXX-BE6B-19BB-1FB7-7090040590CD": "Kale Yeah!",
                "XXXX-B01F-9087-30D5-CF198F7EE27D": "",
                "XXXX-BBEE-E2C2-EFB7-320A5FDA419D": 0
            },
            "presentation": "",
            "web": "",
            "twitter": "",
            "linkedIn": "",
            "points": 0,
            "badges": 0,
            "_links": {
                "self": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/",
                "registrations": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/Registration/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"login" : "this value should not be blank."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"status": "Invalid learner status: it must be Y, N or U."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>

</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_learner_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/-->
<div id="offline_learner_token_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to get the learner authentication token.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learner authentication token.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">learner_guid</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">the learner GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Learner/XXXX-7D28-82B0-1388-A60892F2299B/AuthToken HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learner authentication token counted by the web-service.
</td>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learner authentication token returned by the web-service.
</td>
</tr>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">token</td>
<td markdown="span">string</td>
<td markdown="span">The 6 digits learner authentication token.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoints related to the current object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service enpoint of the current object.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": {
        "token": "WZF7PN"
    },
    "_links": {
        "self": "/API/ADMIN/v1/REST/Learner/XXXX-7D28-82B0-1388-A60892F2299B/AuthToken"
    }
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content."</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#learner_learning_objects_themes_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>



<!--GET https://ckauth.crossknowledge.com/api/learner/authenticate.json-->
<div id="ckauth_learner_authenticate" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/Learner/Authenticate
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service grant access to a client application.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>https://ckauth.crossknowledge.com/api/learner/authenticate.json</i></p>

<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns an authentication token to client application. This authentication token is used to get an access token.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">token</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The 6 digits code.</td>
<td markdown="span">A1B23C</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">

GET /api/learner/authenticate.json?token=A1B23C  HTTP/1.1
Host: ckauth.crossknowledge.com
Cache-Control: no-cache
</code>
</pre>


<p style="font-size: 15px"><strong>Response: </strong></p>
<p>Returned data: </p>

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if yes (true) or no (false) the web-service request was a success.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">learnerLogin</td>
<td markdown="span">string</td>
<td markdown="span">The learner login.
</td>
</tr>
<tr>
<td markdown="span">password</td>
<td markdown="span">string</td>
<td markdown="span">The learner password.
</td>
</tr>
<tr>
<td markdown="span">instanceUrl</td>
<td markdown="span">string</td>
<td markdown="span">The learner learning resource server endpoint.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>

<pre>
<code class="language-json">
{
    "message": "Success",
    "totalResults": 1,
    "success": true,
    "value": {
        "learnerLogin": "richard.roe",
        "password": "zh2d3jpfyg",
        "instanceUrl": "yourdomain.crossknowledge.com/"
    }
}
</code>
</pre>

<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"Success"</td>
<td markdown="span">**200**</td>
</tr>
<td markdown="span">"Invalid token"</td>
<td markdown="span">**81004**
</td>

</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>

</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_administrator_login_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--PUT API/ADMIN/v1/REST/Learner/{learner_guid}/-->
<div id="offline_learner_put" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to update a given learner profile information</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/{learner_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-warning">PUT</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the updated profile information for a given learner.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>

<tr>
<td markdown="span">learner_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">the learner GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner login.</td>
<td markdown="span">richard.roe</td>

</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner reference number.</td>
<td markdown="span">abc123</td>

</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner lastname.</td>
<td markdown="span">Roe</td>

</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner firstname.</td>
<td markdown="span">Richard</td>

</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner email.</td>
<td markdown="span">richard.roe@veganmaster.com</td>

</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner (code) language.</td>
<td markdown="span">en-GB</td>

</tr>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner entity GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner status.</td>
<td markdown="span">Y (active) | N (inactive) | U (active between two dates "start" - "end")</td>

</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner activation date.</td>
<td markdown="span">yyyy-mm-dd</td>

</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner deactivation date.</td>
<td markdown="span">yyyy-mm-dd</td>

</tr>
<tr>
<td markdown="span">customFields</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner custom fields (only string and integer allowed).</td>
<td markdown="span">customFields['guid']='value'</td>

</tr>
<tr>
<td markdown="span">presentation</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner presentation.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">web</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner web-site(portfolio).</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">twitter</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner twitter profile.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">linkedIn</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the learner linked in profile.</td>
<td markdown="span"></td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
PUT /API/ADMIN/v1/REST/Learner/XXXX-82B0-1388-A60892F2299B/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

login=richard.roe%40kale.com&enabled=false&status=N
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learners returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.
</td>
</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span">The learner login.
</td>
</tr>
<tr>
<td markdown="span">referenceNumber</td>
<td markdown="span">string</td>
<td markdown="span">The learner reference number.
</td>
</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span">The learner lastname.
</td>
</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span">The learner firstname.
</td>
</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span">The learner email.
</td>
</tr>
<tr>
<td markdown="span">entityGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner entityGuid.
</td>
</tr>
<tr>
<td markdown="span">enabled</td>
<td markdown="span">true</td>
<td markdown="span">The learner account status.
</td>
</tr>
<tr>
<td markdown="span">language</td>
<td markdown="span">string</td>
<td markdown="span">The learner code language.
</td>
</tr>
<tr>
<td markdown="span">status</td>
<td markdown="span">string</td>
<td markdown="span">The learner account status type.
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">The learner activation start date.
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">The learner activation end date.
</td>
</tr>
<tr>
<td markdown="span">customFields</td>
<td markdown="span">object</td>
<td markdown="span">The learner account custom fields.
</td>
</tr>
<tr>
<td markdown="span">presentation</td>
<td markdown="span">string</td>
<td markdown="span">The learner presentation.
</td>
</tr>
<tr>
<td markdown="span">web</td>
<td markdown="span">string</td>
<td markdown="span">The learner portfolio.
</td>
</tr>
<tr>
<td markdown="span">twitter</td>
<td markdown="span">string</td>
<td markdown="span">The learner twitter profile.
</td>
</tr>
<tr>
<td markdown="span">linkedIn</td>
<td markdown="span">string</td>
<td markdown="span">The learner linked in profile.
</td>
</tr>
<tr>
<td markdown="span">points</td>
<td markdown="span">integer</td>
<td markdown="span">The learner points number.
</td>
</tr>
<tr>
<td markdown="span">badges</td>
<td markdown="span">integer</td>
<td markdown="span">The learner badges number.
</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">string</td>
<td markdown="span">The web-services endpoints related to the current object.
</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object.
</td>
</tr>
<tr>
<td markdown="span">registrations</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the learner registrations.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXXX-D5B3-6C3C-13E7-D0413EA98F49",
            "login": "richard.roe@kale.com",
            "referenceNumber": "",
            "name": "Roe",
            "firstName": "",
            "email": "richard.roe@tofufighter.com",
            "entityGuid": "XXXX-E3C0-578F-4EE4-F39B406097E5",
            "enabled": false,
            "language": "en-GB",
            "status": "N",
            "start": "2017-09-20",
            "end": "2017-09-29",
            "customFields": {
                "XXXX-BE6B-19BB-1FB7-7090040590CD": "Kale Yeah!",
                "XXXX-B01F-9087-30D5-CF198F7EE27D": "",
                "XXXX-BBEE-E2C2-EFB7-320A5FDA419D": 0
            },
            "presentation": "",
            "web": "",
            "twitter": "",
            "linkedIn": "",
            "points": 0,
            "badges": 0,
            "_links": {
                "self": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/",
                "registrations": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/Registration/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Learner/XXXX-D5B3-6C3C-13E7-D0413EA98F49/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"login" : "this value should not be blank."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"status": "Invalid learner status: it must be Y, N or U."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_learner_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/-->
<div id="offline_learner_registration_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/
&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to get the registrations of a given learner.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the registrations information of the learner.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">learner_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learner GUID.</td>
<td markdown="span"></td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Learner/XXXX-47C3-CD84-A35C-8AB8622/Registration/ HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of registration returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An array or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The registration GUID.</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The training session GUID.</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The trianing GUID.</td>
</tr>
<tr>
<td markdown="span">learnerGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner GUID.</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoints related to the current object.</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object (learner's registration).</td>
</tr>
<tr>
<td markdown="span">session</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the training session registration.</td>
</tr>
<tr>
<td markdown="span">training</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of training session registration.</td>
</tr>
<tr>
<td markdown="span">learner</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the learner.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-5D10-3E39-9247-92E9A53222B2",
            "sessionGuid": "XXXX-4C9D-DE71-6B13-FAEBB13B5E21",
            "trainingGuid": "XXXX-C3E7-53FD-A8E8-B300FEE8EE68",
            "learnerGuid": "XXXX-47C3-CD84-A35C-8AB8622AFCE6",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Registration/XXXX-5D10-3E39-9247-92E9A53222B2/",
                "session": "/API/ADMIN/v1/REST/Session/XXXX-4C9D-DE71-6B13-FAEBB13B5E21/",
                "training": "/API/ADMIN/v1/REST/Training/XXXX-C3E7-53FD-A8E8-B300FEE8EE68/",
                "learner": "/API/ADMIN/v1/REST/Learner/XXXX-47C3-CD84-A35C-8AB8622AFCE6/"
            }
        },
		...
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Learner/XXXX-47C3-CD84-A35C-8AB8622AFCE6/Registration/"
    }
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content."</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
          <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#learningObject" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_learner_registration_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/ADMIN/v1/REST/Entity/{entity_guid}-->
<div id="offline_entity_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Entity/{entity_guid}&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to get a given entity information.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Entity/{entity_guid}</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the entity information.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">entity_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The entity GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Entity/XXXX-E3C0-578F-4EE4-F39B406097E5 HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of entity counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of entity returned by the web-service call out.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The entity GUID.</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The entity title.</td>
</tr>
<tr>
<td markdown="span">tree</td>
<td markdown="span">string</td>
<td markdown="span">The parent entity in the entity's tree.</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoint related to the current object.</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object (entity).</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-E3C0-578F-4EE4-F39B406097E5",
            "title": "All users",
            "tree": "All users",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Entity/XXXX-E3C0-578F-4EE4-F39B406097E5/"
            }
        }
    ],
    "_links": {
        "self": "/API/ADMIN/v1/REST/Entity/XXXX-E3C0-578F-4EE4-F39B406097E5/"
    }
}
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**204**
</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#entity" class="btn btn-default navbar-btn cursorNorm" role="button">Entity</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_entity" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--GET API/ADMIN/v1/REST/Entity/-->
<div id="offline_entity_list" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Entity/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allows to search or to list all existing entities.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Entity/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the entity information.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>
{{site.data.alerts.note}}
<p>This web-service requires a valid API key to be used. To do this, you must set your API Key within your HTTP Header request.
</p>
HTTP Header name:
<pre>
API-KEY<br>

</pre>
{{site.data.alerts.end}}

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](http://page.crossknowledge.com/contact-EN.html)." type="info" %}

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">page</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">The page number that should be displayed, based on the limit number	</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not Required" class="fa fa-times"></i></td>
<td markdown="span">Limit to search.</b></td>
<td markdown="span"> Default : 10 Max. 50</td>

</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="No Required" class="fa fa-times"></i></td>
<td markdown="span">Filter on title (pattern like here: %title%).</b></td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">title_exact</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="No Required" class="fa fa-times"></i></td>
<td markdown="span">Filter on the entity exact title.</b></td>
<td markdown="span"></td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/ADMIN/v1/REST/Entity/?title=paris&amp;title_exact=paris school of business HTTP/1.1
Host: yourdomain.crossknowledge.com
API-KEY: XXXX-4E19-752A-DB81-5087AB7CA438	
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of entity counted by the web-service.
</td>
</tr>
<tr>
<td markdown="span">count</td>
<td markdown="span">integer</td>
<td markdown="span">The number of entity returned by the web-service call out.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">array</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">guid</td>
<td markdown="span">string</td>
<td markdown="span">The entity GUID.</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The entity title.</td>
</tr>
<tr>
<td markdown="span">tree</td>
<td markdown="span">string</td>
<td markdown="span">The parent entity in the entity's tree.</td>
</tr>
<tr>
<td markdown="span">_links</td>
<td markdown="span">object</td>
<td markdown="span">The web-service endpoint related to the current object.</td>
</tr>
<tr>
<td markdown="span">self</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the current object (entity).</td>
</tr>
<tr>
<td markdown="span">first</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the search result first page.</td>
</tr>
<tr>
<td markdown="span">last</td>
<td markdown="span">string</td>
<td markdown="span">The web-service endpoint of the search result last page.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalCount": 1,
    "count": 1,
    "value": [
        {
            "guid": "XXXX-70F2-4151-7BEC-0450900144C4",
            "title": "Paris School of Business",
            "tree": "All users|Paris School of Business",
            "_links": {
                "self": "/API/ADMIN/v1/REST/Entity/XXXX-70F2-4151-7BEC-0450900144C4/"
            }
        }
    ],
    "_links": {
        "first": "/API/ADMIN/v1/REST/Entity/?limit=10&page=1",
        "last": "/API/ADMIN/v1/REST/Entity/?limit=10&page=1",
        "self": "/API/ADMIN/v1/REST/Entity/?title=paris&title_exact=paris+school+of+business"
    }
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"page": "This value should be a valid number."</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Unauthorized."</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#entity" class="btn btn-default navbar-btn cursorNorm" role="button">Entity</a>

</div>

</div>
<div class="panel-footer">

<a href="/samples_admin.html#offline_entity_get_2" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--GET API/ADMIN/v1/REST/Tracking/{tracking_guid
<div id="learner_trackings_item_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Report/{report_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to retrieve a report.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Report/{report_guid}/</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the report details.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Required</th>
<th>Comment</th>
<th>Values</th>

</tr>
</thead>
<tbody>
<tr>
<td markdown="span">report_guid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The report GUID.</b></td>
<td markdown="span"> abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>

</tbody>
</table>


<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">

</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p>Returned data: </p>
<table>
<colgroup>
<col/>
<col />
</colgroup>
<thead>
<tr class="header">
<th>Label</th>
<th>Type</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">message</td>
<td markdown="span">string</td>
<td markdown="span">a message indicating the success or the reason of the failure</td>
</tr>
<tr>
<td markdown="span">success</td>
<td markdown="span">boolean</td>
<td markdown="span">Describes if the web-service call was a success or not. (true or false).
</td>
</tr>
<tr>
<td markdown="span">totalCount</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects tracking row returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">firstLaunchTime</td>
<td markdown="span">datetime</td>
<td markdown="span">The date and time when the Learning Object was first launch for the Registration by the learner</td>


</tr>
<tr>
<td markdown="span">completionTime</td>
<td markdown="span">datetime</td>
<td markdown="span">The date and time when the Learning Object was completed for the Registration by the learner</td>

</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">The tracking item ID.
</td>
</tr>
<tr>
<td markdown="span">itemId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object session (context) item ID.
</td>
</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object progression achieved by the learner on the current session.
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span">The learner training session's registration guid.
</td>
</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">float</td>
<td markdown="span">The score achieved by the learner on the learning object (item id) in the current session.
</td>
</tr>
<tr>
<td markdown="span">scoreMax</td>
<td markdown="span">float</td>
<td markdown="span">The max score achievable by the learner on the learning object (item id) in the current session..
</td>
</tr>
<tr>
<td markdown="span">timespent</td>
<td markdown="span">integer</td>
<td markdown="span">The time spent by the learner on the learning object in the current session.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">

  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col />
<col  />
</colgroup>
<thead>
<tr class="header">
<th>Message</th>
<th>Code</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">"OK"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Not Found"</td>
<td markdown="span">**204**</td>
</tr>
<tr>
<td markdown="span">"No Content"</td>
<td markdown="span">**404**</td>
</tr>

</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	  <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (report)</a>
	<a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>


</div>
</div>
<div class="panel-footer">
<a href="/samples_admin.html#offline_report_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>
}/-->
