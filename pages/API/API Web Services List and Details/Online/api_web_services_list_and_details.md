---
title: Learner API Web-services.
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: August 30, 2017
tags: 
summary: "This API allows to get and set data on behalf of the authenticated learner."
permalink: api_web_services_list_and_details.html
folder: API Web Services List and Details
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
.hljs-string{
    color: #99ffa1;
}
.hljs-built_in{
	color: #ff8d8d;
	}
.hljs-number{	
	color: #ffe564;
	}

	
.btn-primary {
	color: #333333;
	background-color: #ffffff;
	border-color: #cccccc;
}

</style>
<script>

	$("#toc").hide();

</script>

<!--POST API/v1/REST/learner/login.json-->
<div id="learner_login_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/login&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service authenticates the learner by creating a HTTP Session object on the server. As long as this HTTP Session is available, you'll able to make web-services call out to get the data of the [authenticated learner](/ckauth_workflow.html). </p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/login.json</i></p>

<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service created a HTTP session on the server and returns a json object.</p>

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
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The login of the learner.</td>
<td markdown="span">john.doe</td>

</tr>
<tr>
<td markdown="span">password</td>
<td markdown="span">string</td>

<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>

<td markdown="span">The password of the learner.
</td>
<td markdown="span">iamjondoethevegan!</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/v1/REST/Learner/login.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

login=john.doe&password=iamjohndoethevegan!
</code>
</pre>


<p style="font-size: 15px"><strong>Response: </strong></p>
<p>Returned data: </p>
{{site.data.alerts.note}}
<p>This web-service returns an authentication cookie in the HTTP Header response that you can use as an access token to call out another web-service.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>

<pre>
<code class="language-json">
{
"message": "Login successful",
"success": true,
"totalResults": 1,
"value": {}
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
<td markdown="span">"Login successful"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: login"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: password"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access denied"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Forbidden"</td>
<td markdown="span">**403**
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
<a href="/samples.html#learner_login_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--DELETE API/v1/REST/learner/login.json-->
<div id="learner_login_delete" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/login&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service logout the [authenticated learner](/ckauth_workflow.html) by killing the HTTP session on the server</p>

<p style="font-size: 15px"><strong>Endpoint :</strong><i> API/v1/REST/learner/login.json</i></p>

<p style="font-size: 15px"><strong>Method : </strong><span class="label label-danger">DELETE</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p markdown="span" >This web-service returns a JSON object after the learner is logged out.</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<p>No parameters required.</p>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
DELETE /API/v1/REST/learner/login.json HTTP/1.1
Host: yourdomain.crossknowledge.com 
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
"message": "Logged out",
"success": true,
"totalResults": 1,
"value": {}
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
<td markdown="span">"Login successful"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Access denied"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Forbidden"</td>
<td markdown="span">**403**
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
<a href="/samples.html#learner_authenticate_delete" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/v1/REST/learner/mobileLogin.json-->
<div id="learner_mobile_login_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/mobileLogin&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service authenticates the learner by creating a HTTP Session on the server.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/mobileLogin.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p> This web-service return json response and HTTP Cookie (access token) in the header of the response.</p>
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
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The login of the learner.</td>
<td markdown="span">john.doe</td>

</tr>
<tr>
<td markdown="span">password</td>
<td markdown="span">string</td>

<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>

<td markdown="span">The password of the learner.
</td>
<td markdown="span">iamjohndoethevegan!.</td>

</tr>
<tr>
<td markdown="span">deviceid</td>
<td markdown="span">string</td>

<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>

<td markdown="span">The device id of the learner.
</td>
<td markdown="span">kale1.</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
POST /API/v1/REST/Learner/mobileLogin.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

login=john.doe&password=iamjohndoethevegan!&deviceid=kale1
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>

<p> Returned data:</p>
{{site.data.alerts.note}}
<p>This web-service returns an authentication cookie in the HTTP Header response that you can use as an access token to call out another web-service.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">mainColor</td>
<td markdown="span">string</td>
<td markdown="span">The hexa code color of the CrossKnowledge mobile app UI as set in the CrossKnowledge platform.
</td>
</tr>
<tr>
<td markdown="span">logoUrl</td>
<td markdown="span">object</td>
<td markdown="span">The client logo URI as set in the CrossKnowledge platform.
</td>
</tr>
</tbody>
</table>
<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "Login successful",
    "success": true,
    "totalResults": 1,
    "value": {
        "mainColor": "#745da1",
        "logoUrl": "https://yourdomain.crossknowledge.com/data/medias/yourClientLogo.png"
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
<td markdown="span">"Login successful"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Access denied: not logged-in."</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Forbidden"</td>
<td markdown="span">**403**
</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: login"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: password"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: deviceid"</td>
<td markdown="span">**400**
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
<a href="/samples.html#learner_mobile_login_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--DELETE API/v1/REST/learner/mobileLogin.json-->
<div id="learner_mobile_login_delete" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/mobileLogin&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service logs out the user by killing the HTTP Session on the server.</p>
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/mobileLogin.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-danger">DELETE</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>
<p>No parameters required.</p>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
DELETE /API/v1/REST/Learner/mobileLogin.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of results returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
"message": "Logged out",
"success": true,
"totalResults": 1,
"value": {}
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
<td markdown="span">"Logged out"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Forbidden"</td>
<td markdown="span">**403**
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
<a href="/samples.html#learner_mobile_login_delete" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/learner/profile.json-->
<div id="learner_profile_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/profile&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span" >This web-service allow to get the profile information of the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/profile.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns the profile information of the learner.</p>

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
<td markdown="span">learnerLogin</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The login of the learner.</td>
<td markdown="span">john.doe</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/learner/profile.json?learnerLogin=john.doe HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
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
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">login</td>
<td markdown="span">string</td>
<td markdown="span">login of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span">name of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">firstname</td>
<td markdown="span">string</td>
<td markdown="span">firstname of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">email</td>
<td markdown="span">string</td>
<td markdown="span">email of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">lastAccessDate</td>
<td markdown="span">string</td>
<td markdown="span">last connexion of the learner to the CrossKnowledge platform as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">normalPictureUri</td>
<td markdown="span">string</td>
<td markdown="span">profile picture of the learner as stored in CrossKnowledge database (small size).
</td>
</tr>
<tr>
<td markdown="span">bigPictureUri</td>
<td markdown="span">string</td>
<td markdown="span">profile picture of the learner as stored in CrossKnowledge database (big size).
</td>
</tr>
<tr>
<td markdown="span">displayName</td>
<td markdown="span">string</td>
<td markdown="span">Concatenation of the learner firstname and lastname.
</td>
</tr>
<tr>
<td markdown="span">presentation</td>
<td markdown="span">string</td>
<td markdown="span">presentation of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">webUrl</td>
<td markdown="span">string</td>
<td markdown="span">public website url of the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">linkedin</td>
<td markdown="span">string</td>
<td markdown="span">linkedin profile url the learner as stored in CrossKnowledge database.
</td>
</tr>
<tr>
<td markdown="span">twitter</td>
<td markdown="span">string</td>
<td markdown="span">twitter profile url of the learner as stored in CrossKnowledge database.
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
    "totalResults": 1,
    "value": {
        "id": 1,
        "login": "johndoe@isalive.com",
        "name": "Doe",
        "firstname": "Jogn",
        "email": "johndoe@isalive.com",
        "lastAccessDate": "2017-09-01 09:37:58",
        "normalPictureUrl": "https://yourdomain.crossknowledge.com/candidate_picture/...",
        "bigPictureUrl": "https://yourdomain.com/candidate_picture/...",
        "displayName": "John Doe",
        "presentation": "",
        "webUrl": "",
        "linkedInUrl": "",
        "twitterUrl": ""
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
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Not found"</td>
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
<a href="/samples.html#learner_profile_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/learner/manager.json-->
<div id="learner_manager_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/manager&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service returns learner’s managing information. It returns the active managers IDs of the [authenticated learner](/ckauth_workflow.html) as stored in CrossKnowledge database.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/manager.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns the manager IDs of the learner</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<p><i>No parameter</i></p>

<p style="font-size: 15px"><strong>Request : </strong></p>

{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}


<pre>
<code class="language-http">
GET /API/v1/REST/learner/manager.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">managerIds</td>
<td markdown="span">array</td>
<td markdown="span">array of managers IDs of the learner as stored in CrossKnowledge database.
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
    "value": {
        "managerIds": [ //authentificated learner managers's accounts IDs.
            4,5,9 
        ]
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
<td markdown="span">"Management is disabled"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#manager" class="btn btn-default navbar-btn cursorNorm" role="button">Manager</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_manager_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!-- GET API/v1/REST/learner/subordinates.json-->
<div id="learner_subordinates_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/subordinates&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service returns learner’s managing information. It inherits from Manager as it returns the active subordinates IDs of the [authenticated learner](/ckauth_workflow.html) as stored in CrossKnowledge database.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/subordinates.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns the subordinates IDs of the learner</p>
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
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">limitedSub</td>
<td markdown="span">boolean</td>
<td markdown="span"><i title="Not required" class="fa fa-times"></i></td>
<td markdown="span">If true, it will limit the list of subordinates to the direct ones, whatever else, it will return all the surbordonates	
</td>
<td markdown="span">true | false</td>	

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Limits the number of ids returned	
</td>
<td markdown="span">Range >= 1
</td>
</tr>
<tr>
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Number of ids of subordinates to ignore in the request	
</td>
<td markdown="span">Range >= 1
</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/learner/subordinates.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of subordinates returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">subordinatesIds</td>
<td markdown="span">array</td>
<td markdown="span">array of IDs of the subordinates as stored in CrossKnowledge database.
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
    "value": {
        "subordinatesIds": [ //authentificated learner managers's accounts IDs.
            459,23,56
        ]
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
<td markdown="span">"Management is disabled"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#subordinates" class="btn btn-default navbar-btn cursorNorm" role="button">subordinates</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_subordinates_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/Discussions/list.json-->
<div id="learner_discussions_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/Discussions/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">Returns available discussions of the connected learner and their comments. The discussions are returned from the newest to the oldest, accordingly to their visibility and the optionnal filter on context. Comments for a given discussion are returned from the newest to the oldest as well.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/Discussions/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns available discussions of the authentificated learner and their comments.</p>
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
<td markdown="span">context</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The [context](/glossary.html#context) of the discussion.</td>
<td markdown="span"> LearningObject | TrainingSession | Training
</td>
</tr>
<tr>
<td markdown="span">contextGuid</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">GUID to add a filter on. Either Learning Object GUID or Training Session GUID or Training GUID(specified in the context parameter)		
</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Limit of discussions to search (ie number of discussions max. to return)</td>		
<td>10 (Default) | 1(Min.) | 50(Max.)
</td>
</tr>
<tr>
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Number of ids of discussions to ignore in the request. If offset is above or equal to the actual number of filtered discussions, an error is returned.</td>
<td>Default: 0
</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/Discussions/list.json?offset=1 HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of subordinates returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the discussion item.</td>
</tr>
<tr>
<td markdown="span">date</td>
<td markdown="span">datatime</td>
<td markdown="span">Date and time when the discussion was posted. (yyyy-mm-dd hh:ii:ss).</td>
</tr>
<tr>
<td markdown="span">context</td>
<td markdown="span">string</td>
<td markdown="span">Context in which the discussion was posted (Training, Learning Object or Training Session).</td>
</tr>
<tr>
<td markdown="span">contextGuid</td>
<td markdown="span">string</td>
<td markdown="span">Guid (identifier) of the context in which the discussion was posted (Training, Learning Object or Training Session).</td>
</tr>
<tr>
<td markdown="span">followed</td>
<td markdown="span">boolean</td>
<td markdown="span">Specifiy if the discussion is followed by the authentificated learner (false: not followed, true: followed).</td>
</tr>
<tr>
<td markdown="span">contributed</td>
<td markdown="span">boolean</td>
<td markdown="span">Specifiy if the discussion is contributed by the [authenticated learner](/ckauth_workflow.html) (false: not contributed, true: contributed).</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">Title of the discussion item. (topic)</td>
</tr>
<tr>
<td markdown="span">comments</td>
<td markdown="span">array</td>
<td markdown="span">Array of object containing the comments associated to the discussion item.</td>
</tr>
<tr>
<td markdown="span">comments.id</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the comment item.</td>
</tr>
<tr>
<td markdown="span">comments.date</td>
<td markdown="span">date</td>
<td markdown="span">Date and time when the discussion was posted. (yyyy-mm-dd hh:ii:ss).</td>
</tr>
<tr>
<td markdown="span">comment</td>
<td markdown="span">string/html</td>
<td markdown="span">Text of the comment item.</td>
</tr>
<tr>
<td markdown="span">like</td>
<td markdown="span">boolean</td>
<td markdown="span">Specify if the comment was liked by the [authenticated learner](/ckauth_workflow.html) or not (0: not liked, 1: liked)</td>
</tr>
<tr>
<td markdown="span">author</td>
<td markdown="span">object</td>
<td markdown="span">Contains the information about the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.login</td>
<td markdown="span">string</td>
<td markdown="span">The username of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.name</td>
<td markdown="span">string</td>
<td markdown="span">The name of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.firstname</td>
<td markdown="span">string</td>
<td markdown="span">The firstname of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.normalPictureUri</td>
<td markdown="span">string</td>
<td markdown="span">The profile picture URI of the author of the comment.</td>
</tr>
</tbody>

</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalResults": 2,
    "value": [
        {
            "id": 191,
            "date": "2017-06-14 19:50:04",
            "context": "TrainingSession",
            "contextGuid": "392570F0-ACC7-xxxxxxxxxxxxxxxx",
            "followed": false,
            "contributed": false,
            "title": "Are you John Doe?",
            "comments": [
                {
                    "id": 268,
                    "date": "2017-06-14 19:50:04",
                    "comment": "<p>Not really!</p>",
                    "like": 1,
                    "author": {
                        "login": "Richard.Roe",
                        "name": "Roe",
                        "firstname": "Richard",
                        "normalPictureUrl": "yourdomain.crossknowledge.com/candidate_picture/..."
                    }
                }
            ]
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
<td markdown="span">"There are no current discussions"</td>
<td markdown="span">**200**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"The offset parameter is higher than the number of discussions"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Bad Parameter"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Context not found"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Discussion not visible by the user."</td>
<td markdown="span">**400**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussions" class="btn btn-default navbar-btn cursorNorm" role="button">Discussions</a>
	 <a href="glossary.html#comments" class="btn btn-default navbar-btn cursorNorm" role="button">Comments</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--PUT API/v1/REST/Discussions/Comments/{commentId}.json-->
<div id="learner_discussions_comment_like_put" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/Comments/{commentId}&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service allow the [authenticated learner](/ckauth_workflow.html) to like a comment.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/Comments/{commentId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-warning">PUT</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object.</p>
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
<td markdown="span">commentId</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the comment id.
</td>
<td markdown="span"> Range >= 1
</td>
</tr>
<tr>
<td markdown="span">like</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">If yes or no the [authenticated learner](/ckauth_workflow.html) likes the comment. (0: no liked, 1: Liked {default})	
</td>
<td markdown="span">true | false</td>

</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
PUT /API/v1/REST/Discussions/Comments/1.json?commentId=1&like=1 HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of subordinates returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "Liked",
    "success": true,
    "totalResults": 1,
    "value": null
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
<td markdown="span">"Liked"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Already liked"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Comment not liked"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing Mandatory Parameter : commentId"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Discussion not visible by the use"</td>
<td markdown="span">**403**</td>
</tr>
<tr>
<td markdown="span">"Comment not found"</td>
<td markdown="span">**404**</td>
</tr>



</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussions" class="btn btn-default navbar-btn cursorNorm" role="button">Discussions</a>
	 <a href="glossary.html#comments" class="btn btn-default navbar-btn cursorNorm" role="button">Comments</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_comment_like_put" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/v1/REST/Discussions/list.json-->
<div id="learner_discussions_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/list.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service allow the [authenticated learner](/ckauth_workflow.html) to create a new discussion with a new (first) post associated.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the ID of the newly created discussion (Topic).</p>
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
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">context</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> Class name of the object to which the discussion will be associated</td>
<td>| LearningObject | TrainingSession | Training
</td>
</tr>
<tr>
<td markdown="span">contextGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The GUID of the context object sepcified for the 'context" parameter	
</td>
<td>123456-abcedfg-xxxxxxxxxxxxxxxx</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> The title of the discussion (topic). If the context is "LearningObject", the title will be content title.</td>
<td>John Doe is alive!
</td>
</tr>
<tr>
<td markdown="span">comment</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The comment on the discussion</td>
<td>I've seen John Doe!
</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/Discussions/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Cache-Control: no-cache
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of discussions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">newTopicId</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the newly created discussion.
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
    "totalResults": 1,
    "value": {
        "newTopicId": 193
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
<td markdown="span">"Bad parameter: context"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: title"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: comment"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: context"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: contextGuid"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Context not found"</td>
<td markdown="span">**404**</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussions" class="btn btn-default navbar-btn cursorNorm" role="button">Discussions</a>
	 <a href="glossary.html#comments" class="btn btn-default navbar-btn cursorNorm" role="button">Comments</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/Discussions/{discussionId}.json-->
<div id="learner_discussions_item_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service allow to get all the comments of a given discussion available for a learner.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/{discussionId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with a list of comments for the given discussion.</p>
<p style="font-size: 15px"><strong>Parameters : </strong></p>

<span>No parameters required.</span>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/Discussions/195.json HTTP/1.1
Host: presales.jnstaging.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of discussions returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the comment item.</td>
</tr>
<tr>
<td markdown="span">date</td>
<td markdown="span">datatime</td>
<td markdown="span">Date and time when the comment was posted. (yyyy-mm-dd hh:ii:ss).</td>
</tr>

<tr>
<td markdown="span">comment</td>
<td markdown="span">string</td>
<td markdown="span">The text comment.</td>
</tr>

<tr>
<td markdown="span">like</td>
<td markdown="span">integer</td>
<td markdown="span">Number of likes.</td>
</tr>
<tr>
<td markdown="span">author</td>
<td markdown="span">object</td>
<td markdown="span">Contains the information about the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.login</td>
<td markdown="span">string</td>
<td markdown="span">The username of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.name</td>
<td markdown="span">string</td>
<td markdown="span">The name of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.firstname</td>
<td markdown="span">string</td>
<td markdown="span">The firstname of the author of the comment.</td>
</tr>
<tr>
<td markdown="span">author.normalPictureUri</td>
<td markdown="span">string</td>
<td markdown="span">The profile picture URI of the author of the comment.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalResults": 1,
    "value": [
        {
            "id": 271,
            "date": "2017-09-04 15:15:34",
            "comment": "No,I'm John Doe!",
            "like": 0,
            "author": {
                "login": "john.doe",
                "name": "Doe",
                "firstname": "John",
                "normalPictureUrl": "https://yourdomain.crossknowledge.com/candidate_picture/..."
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
<td markdown="span">"Bad parameter: context"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: title"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: comment"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: context"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Missing mandatory parameter: contextGuid"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Access denied"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Context not found"</td>
<td markdown="span">**404**</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussions" class="btn btn-default navbar-btn cursorNorm" role="button">Discussions</a>
	 <a href="glossary.html#comments" class="btn btn-default navbar-btn cursorNorm" role="button">Comments</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_item_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/v1/REST/Discussions/{discussionId}.json-->
<div id="learner_discussions_item_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service allow to update a given discussion available for a learner by adding a new comment.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/{discussionId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the ID of the created comment.</p>
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
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">comment</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> the text comment to add.
</td>
<td markdown="span">Richard Roe was a good man.</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/Discussions/195.json HTTP/1.1
Host: presales.jnstaging.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of discussions created by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">newPostId</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the newly created comment.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalResults": 1,
    "value": {
        "newPostId": 276
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
<td markdown="span">"Missing mandatory parameter: comment"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Discussion</a>
	 <a href="glossary.html#comment" class="btn btn-default navbar-btn cursorNorm" role="button">Comment</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_item_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>



<!--POST API/v1/REST/Discussions/Follow/{discussionId}.json-->
<div id="learner_discussions_follow_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/Follow/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web service allow to follow a given discussion available for the [authenticated learner](/ckauth_workflow.html) by adding a new comment.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/Follow/{discussionId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>
<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the ID of the created comment.</p>
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
<th>values</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">follow</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"> Follow or unfollow the discussion.
</td>
<td markdown="span"> 0: unfollow | 1: Follow (default)
</td>
</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/Discussions/195.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of discussion updated by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "Discussion subscribed",
    "success": true,
    "totalResults": 1,
    "value": null
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
<td markdown="span">"Discussion subscribed"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Discussion already subscribed"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Discussion not visible by the learner"</td>
<td markdown="span">**400**</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Discussion</a>
	 <a href="glossary.html#comment" class="btn btn-default navbar-btn cursorNorm" role="button">Comment</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_discussions_follow_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/Trainings/list.json-->
<div id="learner_trainings_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trainings/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the trainings information available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trainings/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the trainings information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Index to start the search.</td>
<td markdown="span">Default: 0</td>
</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Limit of the search.</td>
<td markdown="span">Default: 10 Max.: 50</td>
</tr>
<tr>
<td markdown="span">filter</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Filter on trainings only available for mobile.</td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/Trainings/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
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
<td markdown="span">locale</td>
<td markdown="span">string</td>
<td markdown="span">The language code of the training.
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
<td markdown="span">discussionEnabled</td>
<td markdown="span">boolean</td>
<td markdown="span">Define id the discussions are enabled on this training or not. True: Enabled False: Disabled. To learn more about discussion restrictions click here.
</td>
</tr>
<tr>
<td markdown="span">discussionRestricted</td>
<td markdown="span">boolean</td>
<td markdown="span">Define id the discussions are restricted to this training or not. True: Restricted False: Not Restricted. To learn more about discussion restrictions click here.
</td>
</tr>
<tr>
<td markdown="span">modality</td>
<td markdown="span">string</td>
<td markdown="span">modality of the training.
</td>
</tr>
<tr>
<td markdown="span">normalPictureUrl</td>
<td markdown="span">string</td>
<td markdown="span">The thumbnail of the training. (size: 220x124)
</td>
</tr>
<tr>
<td markdown="span">catalogInfo</td>
<td markdown="span">array</td>
<td markdown="span">A representation of the organisation of the training in the catalog.
</td>
</tr>
<tr>
<td markdown="span">catalogInfo.chapterName</td>
<td markdown="span">string</td>
<td markdown="span">The training's chapter in the catalog.
</td>
</tr>
<tr>
<td markdown="span">catalogInfo.guid</td>
<td markdown="span">string</td>
<td markdown="span">The training's chapter GUID in the catalog.
</td>
</tr>
<tr>
<td markdown="span">catalogInfo.parentGuid</td>
<td markdown="span">string</td>
<td markdown="span">The training's parent chapter GUID in the catalog.
</td>
</tr>
<tr>
<td markdown="span">isMobile</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the training is enabled for mobile app. True: Enabled False: Disabled.
</td>
</tr>
<tr>
<td markdown="span">trainingId</td>
<td markdown="span">integer</td>
<td markdown="span">ID of the training.
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
    "totalResults": 1,
    "value": [
        {
            "guid": "D65D7E08-XXXXXXX-XXXXXXX-D132-76DA",
            "title": "Improving Skills Negociation.",
            "code": "TCC",
            "locale": "en-US",
            "description": "Most sales professionals are always looking for ways...",
            "welcomeText": null,
            "discussionEnabled": true,
            "discussionRestricted": true,
            "modality": "guided",
            "normalPictureUrl": "https://yourdomain-assets.crossknowledge.com/lo_picture/...",
            "catalogInfo": [
                {
                    "chapterName": "Management Techniques",
                    "guid": "0139A842-5AAF-XXXXXXX-XXXXXXX",
                    "parentGuid": null
                },
                {
                    "chapterName": "Selling / Negotiation",
                    "guid": "20BE3B45-B727-XXXXXXX-XXXXXXX",
                    "parentGuid": "XXXXXXX-XXXXXXX-D0F1-773F8B1B1EFE"
                }
            ],
            "isMobile": false,
            "trainingId": 1625
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
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Discussion</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#catalog" class="btn btn-default navbar-btn cursorNorm" role="button">Training Catalog</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_trainings_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/TrainingSessions/list.json-->
<div id="learner_training_sessions_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/TrainingSessions/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the training sessions information available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/TrainingSessions/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the training sessions information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Index to start the search. </td>
<td markdown="span">Default: 0</td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Limit of the search.</td>
<td markdown="span"> Default: 10 Max.: 50</td>

</tr>
<tr>
<td markdown="span">modalities</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Values (separated by comma) of training modalities to search.</td>
<td markdown="span">kc,campus,distanciel,guided | Default: all</td>
</tr>
<tr>
<td markdown="span">filter</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Filter on training sessions available for mobile only.</td>

<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/TrainingSessions/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of training sessions returned by the web-service.
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
<td markdown="span">The GUID of the training session.
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The GUID of the training.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The title of the training session.
</td>
</tr>
<tr>
<td markdown="span">start</td>
<td markdown="span">string</td>
<td markdown="span">Start date of the session (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">end</td>
<td markdown="span">string</td>
<td markdown="span">End date of the session (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">description</td>
<td markdown="span">string</td>
<td markdown="span">The description of the training session.
</td>
</tr>
<tr>
<td markdown="span">welcomeText</td>
<td markdown="span">string</td>
<td markdown="span">the welcome text of the training session.
</td>
</tr>
<tr>
<td markdown="span">modality</td>
<td markdown="span">string</td>
<td markdown="span">modality of the training session.
</td>
</tr>
<tr>
<td markdown="span">progress</td>
<td markdown="span">integer</td>
<td markdown="span">The learner's progression (%) in the training session.
</td>
</tr>
<tr>
<td markdown="span">totalTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span">The learner total time spent (seconds) in the training session.
</td>
</tr>
<tr>
<td markdown="span">formattedTotalTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span">The learner formattted total time spent (hh:ii) in the training session.
</td>
</tr>
<tr>
<td markdown="span">isMobile</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the training session is enabled for mobile app. True: Enabled False: Disabled
</td>
</tr>
<tr>
<td markdown="span">accessible</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the training session is open for registration True: Open False: Close.
</td>
</tr>
<tr>
<td markdown="span">closed</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the training session is closed according to due time True: Open False: Close.
</td>
</tr>
<tr>
<td markdown="span">trainingUrl</td>
<td markdown="span">string</td>
<td markdown="span">The training session direct access URL.
</td>
</tr>
<tr>
<td markdown="span">normalPictureUrl</td>
<td markdown="span">string</td>
<td markdown="span">The thumbnail of the training session.
</td>
</tr>
<tr>
<td markdown="span">configurablePictureUrl</td>
<td markdown="span">string</td>
<td markdown="span">The responsive thumbnail of the training session.
</td>
</tr>
<tr>
<td markdown="span">guidedEarnedPoints</td>
<td markdown="span">integer</td>
<td markdown="span">The points earned on the session. (Only available for training modality = guided)
</td>
</tr>
<tr>
<td markdown="span">guidedThreshold</td>
<td markdown="span">integer</td>
<td markdown="span">The points threshold of the session. (Only available for training modality = guided)
</td>
</tr>
<tr>
<td markdown="span">guidedMainColor</td>
<td markdown="span">string</td>
<td markdown="span">The hex color of the training session UI. (Only available for training modality = guided)
</td>
</tr>
<tr>
<td markdown="span">showPoints</td>
<td markdown="span">boolean</td>
<td markdown="span">Define wheither or not points are visible or not for the learner from the UI. true: Visible false: not visible (Only available for training modality = guided)
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
    "totalResults": 1,
    "value": [
        {
            "guid": "392570F0-XXXXXXXX-CE4F-363B-XXXXXXXX",
            "trainingGuid": "D65D7E08-XXXXXXXX-D132-76DA-XXXXXXXX",
            "title": "Improving Skills Negociation.",
            "start": "2017-04-20",
            "end": "2017-09-29",
            "description": "Most sales professionals are always looking for ways to overcome customer objections and close the sale.\n",
            "modality": "guided",
            "welcomeText": "Most sales professionals are always looking for ways to overcome customer objections and close the sale.<br/>\n",
            "progress": 71,
            "totalTimeSpent": 6607,
            "formattedTotalTimeSpent": "1 h 50 min.",
            "isMobile": false,
            "accessible": true,
            "closed": false,
            "trainingUrl": "yourdomain.crossknowledge.com/site/path/1100",
            "normalPictureUrl": "yourdomain-assets.crossknowledge.com/lo_picture/...",
            "configurablePictureUrl": "yourdomain-assets.crossknowledge.com/lo_picture/...",
            "guidedEarnedPoints": 48,
            "guidedThreshold": 68,
            "guidedMainColor": "#1a76e2",
            "showPoints": true
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
<td markdown="span">"The Offset parameter is greater than the total number of available training courses"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Discussion</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#sessions" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Reports)</a>

	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_training_sessions_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/LearningObjects/list-->
<div id="learner_learning_objects_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the learning objects (content) information available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Index to start the search.</td>
<td markdown="span"> Default: 0</td>

</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Limit of the search.</td>
<td markdown="span"> Default: 10 Max.: 50</td>

</tr>
<tr>
<td markdown="span">sort</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Descendant sort on: view | rate | update |lastAccessDate</td>
<td markdown="span">view | rate | update |lastAccessDate</td>

</tr>
<tr>
<td markdown="span">filter</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Filter on a duration range (mins)
</td>
<td markdown="span">short (max. 10) | medium (max. 30) | long (+30)</td>

</tr>
<tr>
<td markdown="span">types</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td>Array (separated by comma) containing the list of types.
Each Learning Objects found must match with a given type.</td>
<td>
<ul>
<li>v (video)</li>
<li>i (interactive content)</li>
<li>r (reading document)</li>
<li>q (Questionnaire)</li>
<li>w (web site)</li>
<li>a (audio)</li>
<li>s (work to submit)</li>
<li>c (In-class assessement)</li>
<li>d (document to download)</li>
<li>p (image)</li>
</ul>
</td>
</tr>
<tr>
<td markdown="span">theme</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Filter on a theme.</td>
<td markdown="span">My theme name</td>

</tr>
<tr>
<td markdown="span">linkedToLoId</td>
<td markdown="span">int</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>Filter on a linked learning object.</td>
<td markdown="span">Default: 0</td>

</tr>
<tr>
<td markdown="span">tags</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Array (separated by comma) containing the list of tags
which the learning object found must have.</td>
<td markdown="span">negociation, award, guilty, innocent</td>

</tr>
<tr>
<td markdown="span">keyword</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">filter on a keyword which the learning object found must have.</td>
<td markdown="span">sales negociation</td>

</tr>

<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">filter on a specific session GUID.</td>
<td markdown="span">123456-abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">folderId</td>
<td markdown="span">int</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">filter on a specific folder ID.</td>
<td markdown="span">Defulat: 0</td>

</tr>
<tr>
<td markdown="span">mobileTraining</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">If true, only Learning Objects related to a training course set "Available in the Mobile Application" will be returned.</td>
<td markdown="span">true | false</td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object session item ID (context).
</td>
</tr>
<tr>
<td markdown="span">loId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object id.
</td>
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
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The learnin object code.
</td>
</tr>
<tr>
<td markdown="span">locale</td>
<td markdown="span">string</td>
<td markdown="span">The language code of the learning object.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">object</td>
<td markdown="span">Thumbnail URIs of the learning object in 3 size: small | medium | large.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type (in the example below i for Interactive content).
</td>
</tr>
<tr>
<td markdown="span">typeLabel</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type label.
</td>
</tr>
<tr>
<td markdown="span">subtype</td>
<td markdown="span">string</td>
<td markdown="span">The learing object subtype.
</td>
</tr>
<tr>
<td markdown="span">author</td>
<td markdown="span">object</td>
<td markdown="span">The learing object author :  authorGuid (identifier) | authorFirstname (firstname) | authorLastname (lastname)
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object duration (mins.).
</td>
</tr>
<tr>
<tr>
<td markdown="span">summary</td>
<td markdown="span">string</td>
<td markdown="span">The learing object summary.
</td>
</tr>
<td markdown="span">learningPoints</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learning points (What you will learn).
</td>
</tr>
<tr>
<td markdown="span">includedInLo</td>
<td markdown="span">string</td>
<td markdown="span">The learning object detailed summary.
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
<td markdown="span">totalRate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total rate.
</td>
</tr>
<tr>
<td markdown="span">totalViews</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total views.
</td>
</tr>
<tr>
<td markdown="span">isFavourite</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object favourites number.
</td>
</tr>
<tr>
<td markdown="span">rate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object learner rate.
</td>
</tr>
<tr>
<td markdown="span">launchDate</td>
<td markdown="span">string</td>
<td markdown="span">The learning object last access date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learner progression (%).
</td>
</tr>
<tr>
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object tracking Id (can be used to get or set the tracking for a learner).
</td>
</tr>
<tr>
<td markdown="span">folder</td>
<td markdown="span">object</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">locales</td>
<td markdown="span">array</td>
<td markdown="span">The learning object available locales.
</td>
</tr>
<tr>
<td markdown="span">runtime</td>
<td markdown="span">string</td>
<td markdown="span">The learning object runtime.
</td>
</tr>
<tr>
<td markdown="span">isMobile</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is available for mobile.
</td>
</tr>
<tr>
<td markdown="span">isDownloadable</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is downloadable for offline access.
</td>
</tr>
<tr>
<td markdown="span">isMandatory</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is mandatory in the training session.
</td>
</tr>
<tr>
<td markdown="span">theme</td>
<td markdown="span">object</td>
<td markdown="span">The learning object theme.
</td>
</tr>
<tr>
<td markdown="span">modificationDate</td>
<td markdown="span">date</td>
<td markdown="span">The learning object last modification date (YYYY-MM-DD hh:ii:ss).
</td>
</tr>
<tr>
<td markdown="span">sortOrder</td>
<td markdown="span">integer</td>
<td markdown="span">The sort order of the learning object in the training session.
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span">The registration guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The trianing guid of the learner(learning object context).
</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The training session guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">scormData</td>
<td markdown="span">object</td>
<td markdown="span">The tracking data of the learner on the learning object (Scorm 1.2/ 2004) : activity_url | activity_id | version | raw_tracking_data
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
    "totalResults": 6,
    "value": [
        {
            "id": 32439,
            "loId": 2337,
            "guid": "OJNE012",
            "title": "谈判准备十步曲",
            "code": "OJNE312",
            "locale": "zh-CHS",
            "thumbnail": {
                "small": "yourdomain-assets.crossknowledge.com/lo_picture/...",
                "medium": "yourdomain-assets.crossknowledge.com/lo_picture/...",
                "large": "yourdomain-assets.crossknowledge.com/lo_picture/..."
            },
            "type": "i",
            "typeLabel": "Session",
            "subtype": "cksession",
            "author": {
                "authorGuid": "RICHARD_ROE_70",
                "authorFirstName": "Richard",
                "authorLastName": "Roe"
            },
            "duration": 30,
            "summary": "要取得谈判的成功",
            "learningPoints": <span markdown="span">"<ul><li>谈判准备的不同步骤 </li><li>每个步骤中需要问的问题  </li><li>什么是“BATNA”？  </li><li>什么是谈判策略？</li></ul>"</span>,
            "includedInLO": "",
            "targetAudience": "所有想要获得谈判成功的人",
            "level": "2",
            "totalRate": 0,
            "views": 5,
            "isFavourite": 0,
            "rate": 0,
            "launchDate": null,
            "progression": "5",
            "trackingId": 26116,
            "folder": null,
            "locales": [
                "zh-CHS",
                "ja-JP",
                "fr-FR",
                "en-US",
                "en-GB",
                "de-DE",
                "es-ES",
                "nl-NL",
                "pl-PL",
                "pt-BR",
                "ru-RU"
            ],
            "runtime": "scorm",
            "isMobile": false,
            "isDownloadable": false,
            "isMandatory": false,
            "theme": {
                "theme": "Find John Doe at Tokyo."
            },
            "modificationDate": "2015-09-15 00:11:52",
            "sortOrder": 14,
            "registrationGuid": "XXXXXXXXX-21FD-EEBB-D8E8-XXXXXXXXX81502",
            "trainingGuid": "D65D7E08-223B-D132-7XXXXXXXXX916BA49",
            "sessionGuid": "392570XXXXXXXXX7-CE4F-363B-422XXXXXXXXXDAE5",
            "scormData": {
                "activity_url": "",
                "activity_id": 0,
                "version": "scorm2004",
                "raw_tracking_data": "{\"cmi._version\":\"1.0\",\"cmi.learner_id\":\"johndoe@isalive.com\",\"cmi.learner_name\":\"Mbouani,Brice\",\"cmi.extra_parameters\":\"student_e_mail=brice.mbouani@crossknowledge.com\",\"cmi.location\":\"\",\"cmi.completion_status\":\"incomplete\",\"cmi.completion_threshold\":\"1\",\"cmi.credit\":\"credit\",\"cmi.entry\":\"resume\",\"cmi.total_time\":0,\"cmi.max_time_allowed\":\"\",\"cmi.exit\":\"suspend\",\"cmi.session_time\":\"PT0H0M0S\",\"cmi.mode\":\"normal\",\"cmi.suspend_data\":\"\",\"cmi.launch_data\":\"\",\"cmi.progress_measure\":\"\",\"cmi.scaled_passing_score\":\"\",\"cmi.time_limit_action\":\"continue,no message\",\"cmi.success_status\":\"unknown\",\"cmi.learner_preference.language\":\"en-GB\",\"cmi.learner_preference.audio_level\":\"1\",\"cmi.learner_preference.audio_captioning\":\"0\",\"cmi.learner_preference.delivery_speed\":\"1\",\"cmi.score.raw\":\"\",\"cmi.score.min\":\"\",\"cmi.score.max\":\"\",\"cmi.score.scaled\":\"\",\"cmi.objectives._count\":\"0\",\"cmi.interactions._count\":\"0\"}"
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
<td markdown="span">"Invalid parameter offset"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter limit"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'sort' must be in: view, rate, lastAccessDate, update"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'types' must be in: v, i, r, q, w, a, s, c, d, p"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#sessions" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Report)</a>
	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_objects_list" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/LearningObjects/{learningObjectId}.json-->
<div id="learner_learning_objects_item_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get a learning object (content) information available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object session item Id.</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">locale</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The learning object locale.</td>
<td markdown="span">en-GB</td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/32439.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">The training session ID (context).
</td>
</tr>
<tr>
<td markdown="span">loId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object id.
</td>
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
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The learnin object code.
</td>
</tr>
<tr>
<td markdown="span">locale</td>
<td markdown="span">string</td>
<td markdown="span">The language code of the learning object.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">object</td>
<td markdown="span">Thumbnail URIs of the learning object in 3 size: small | medium | large.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type (in the example below i for Interactive content).
</td>
</tr>
<tr>
<td markdown="span">typeLabel</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type label.
</td>
</tr>
<tr>
<td markdown="span">subtype</td>
<td markdown="span">string</td>
<td markdown="span">The learing object subtype.
</td>
</tr>
<tr>
<td markdown="span">author</td>
<td markdown="span">object</td>
<td markdown="span">The learing object author :  authorGuid (identifier) | authorFirstname (firstname) | authorLastname (lastname)
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object duration (mins.).
</td>
</tr>
<tr>
<tr>
<td markdown="span">summary</td>
<td markdown="span">string</td>
<td markdown="span">The learing object summary.
</td>
</tr>
<td markdown="span">learningPoints</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learning points (What you will learn).
</td>
</tr>
<tr>
<td markdown="span">includedInLo</td>
<td markdown="span">string</td>
<td markdown="span">The learning object detailed summary.
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
<td markdown="span">totalRate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total rate.
</td>
</tr>
<tr>
<td markdown="span">totalViews</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total views.
</td>
</tr>
<tr>
<td markdown="span">isFavourite</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object favourites number.
</td>
</tr>
<tr>
<td markdown="span">rate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object learner rate.
</td>
</tr>
<tr>
<td markdown="span">launchDate</td>
<td markdown="span">string</td>
<td markdown="span">The learning object last access date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learner progression (%).
</td>
</tr>
<tr>
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object tracking Id (can be used to get or set the tracking for a learner).
</td>
</tr>
<tr>
<td markdown="span">folder</td>
<td markdown="span">object</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">locales</td>
<td markdown="span">array</td>
<td markdown="span">The learning object available locales.
</td>
</tr>
<tr>
<td markdown="span">runtime</td>
<td markdown="span">string</td>
<td markdown="span">The learning object runtime.
</td>
</tr>
<tr>
<td markdown="span">isMobile</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is available for mobile.
</td>
</tr>
<tr>
<td markdown="span">isDownloadable</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is downloadable for offline access.
</td>
</tr>
<tr>
<td markdown="span">isMandatory</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is mandatory in the training session.
</td>
</tr>
<tr>
<td markdown="span">theme</td>
<td markdown="span">object</td>
<td markdown="span">The learning object theme.
</td>
</tr>
<tr>
<td markdown="span">modificationDate</td>
<td markdown="span">date</td>
<td markdown="span">The learning object last modification date (YYYY-MM-DD hh:ii:ss).
</td>
</tr>
<tr>
<td markdown="span">sortOrder</td>
<td markdown="span">integer</td>
<td markdown="span">The sort order of the learning object in the training session.
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span">The registration guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The trianing guid of the learner(learning object context).
</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The training session guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">scormData</td>
<td markdown="span">object</td>
<td markdown="span">The tracking data of the learner on the learning object (Scorm 1.2/ 2004) : activity_url | activity_id | version | raw_tracking_data
</td>
</tr>
<tr>
<td markdown="span">tags</td>
<td markdown="span">string</td>
<td markdown="span">The learning object tags.
</td>
</tr>
<tr>
<td markdown="span">contentURIs</td>
<td markdown="span">object</td>
<td markdown="span">The learning object direct access URI: launchURI | subtitleURIs
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
    "totalResults": 6,
    "value": [
        {
            "id": 32439,
            "loId": 2337,
            "guid": "OJNE012",
            "title": "谈判准备十步曲",
            "code": "OJNE312",
            "locale": "zh-CHS",
            "thumbnail": {
                "small": "yourdomain-assets.crossknowledge.com/lo_picture/...",
                "medium": "yourdomain-assets.crossknowledge.com/lo_picture/...",
                "large": "yourdomain-assets.crossknowledge.com/lo_picture/..."
            },
            "type": "i",
            "typeLabel": "Session",
            "subtype": "cksession",
            "author": {
                "authorGuid": "RICHARD_ROE_70",
                "authorFirstName": "Richard",
                "authorLastName": "Roe"
            },
            "duration": 30,
            "summary": "要取得谈判的成功",
            "learningPoints": <span markdown="span">"<ul><li>谈判准备的不同步骤 </li><li>每个步骤中需要问的问题  </li><li>什么是“BATNA”？  </li><li>什么是谈判策略？</li></ul>"</span>,
            "includedInLO": "",
            "targetAudience": "所有想要获得谈判成功的人",
            "level": "2",
            "totalRate": 0,
            "views": 5,
            "isFavourite": 0,
            "rate": 0,
            "launchDate": null,
            "progression": "5",
            "trackingId": 26116,
            "folder": null,
            "locales": [
                "zh-CHS",
                "ja-JP",
                "fr-FR",
                "en-US",
                "en-GB",
                "de-DE",
                "es-ES",
                "nl-NL",
                "pl-PL",
                "pt-BR",
                "ru-RU"
            ],
            "runtime": "scorm",
            "isMobile": false,
            "isDownloadable": false,
            "isMandatory": false,
            "theme": {
                "theme": "Find John Doe at Tokyo."
            },
            "modificationDate": "2015-09-15 00:11:52",
            "sortOrder": 14,
            "registrationGuid": "XXXXXXXXX-21FD-EEBB-D8E8-XXXXXXXXX81502",
            "trainingGuid": "D65D7E08-223B-D132-7XXXXXXXXX916BA49",
            "sessionGuid": "392570XXXXXXXXX7-CE4F-363B-422XXXXXXXXXDAE5",
            "scormData": {
                "activity_url": "",
                "activity_id": 0,
                "version": "scorm2004",
                "raw_tracking_data": "{\"cmi._version\":\"1.0\",\"cmi.learner_id\":\"johndoe@isalive.com\",\"cmi.learner_name\":\"Mbouani,Brice\",\"cmi.extra_parameters\":\"student_e_mail=brice.mbouani@crossknowledge.com\",\"cmi.location\":\"\",\"cmi.completion_status\":\"incomplete\",\"cmi.completion_threshold\":\"1\",\"cmi.credit\":\"credit\",\"cmi.entry\":\"resume\",\"cmi.total_time\":0,\"cmi.max_time_allowed\":\"\",\"cmi.exit\":\"suspend\",\"cmi.session_time\":\"PT0H0M0S\",\"cmi.mode\":\"normal\",\"cmi.suspend_data\":\"\",\"cmi.launch_data\":\"\",\"cmi.progress_measure\":\"\",\"cmi.scaled_passing_score\":\"\",\"cmi.time_limit_action\":\"continue,no message\",\"cmi.success_status\":\"unknown\",\"cmi.learner_preference.language\":\"en-GB\",\"cmi.learner_preference.audio_level\":\"1\",\"cmi.learner_preference.audio_captioning\":\"0\",\"cmi.learner_preference.delivery_speed\":\"1\",\"cmi.score.raw\":\"\",\"cmi.score.min\":\"\",\"cmi.score.max\":\"\",\"cmi.score.scaled\":\"\",\"cmi.objectives._count\":\"0\",\"cmi.interactions._count\":\"0\"}"
            },
			"tags": "协商, 合作, 工作与生活的平衡, 收购, 销售, 信念",
			"contentURIs": {
				"launchURI": "https://XXXXXXXXX.cloudfront.net/staticCourseContent/zh-CHS/XXXXXXXXX/",
				"subtitleURIs": []
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
<td markdown="span">"Invalid parameter offset"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter limit"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'sort' must be in: view, rate, lastAccessDate, update"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'types' must be in: v, i, r, q, w, a, s, c, d, p"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Report)</a>
	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_object_item_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--POST API/v1/REST/LearningObjects/{learningObjectId}.json-->
<div id="learner_learning_objects_item_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to set vote or add to favourite a learning object (content) available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/{learningObjectId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects updated information for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">vote</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object vote (rate number)..</td>
<td markdown="span">Range >= 1 (Max. 5) </td>

</tr>
<tr>
<td markdown="span">favourite</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Add learning object to learner's favourite list.</td>
<td markdown="span">0 (false) | 1 (true)</td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/LearningObjects/32439.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

vote=5&favourite=0
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects updated returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">rate</td>
<td markdown="span">integer</td>
<td markdown="span">The rate number set by the authenticated learner on the learning object.
</td>
</tr>
<tr>
<td markdown="span">totalRate</td>
<td markdown="span">integer</td>
<td markdown="span">The total rate number on the learning object.
</td>
</tr>
<tr>
<td markdown="span">totalVote</td>
<td markdown="span">string</td>
<td markdown="span">The total vote number on the learning object.
</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "ok",
    "success": true,
    "totalResults": 0,
    "value": {
        "rate": 5,
        "totalRate": 5,
        "totalVote": "(1 vote)"
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
<td markdown="span">"The vote value is not correct: n"</td>
<td markdown="span">**400**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	 <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking (Report)</a>
	 <a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_object_item_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/LearningObjects/themes.json-->
<div id="learner_learning_objects_themes_get" tsclass="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/themes&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the learning objects (content) themes list available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/themes.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects themes available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">Limit must be between 0 and 50</td>
<td markdown="span">Default: 10 Max. 50</td>

</tr>
<tr>
<td markdown="span">offset</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">Offset of the themes list.</td>
<td markdown="span">Default: 10</td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/themes.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects themes returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">title</td>
<td markdown="span">string</td>
<td markdown="span">The theme title.
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
    "totalResults": 135,
    "value": [
        {
            "title": "Sharing the vision"
        },
        {
            "title": "Developing Talents"
        },
        {
            "title": "Personal Development"
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
<td markdown="span">"Invalid parameter offset"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter limit"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#theme" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Objects Theme</a>
</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_objects_themes_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/LearningObjects/types.json-->
<div id="learner_learning_objects_types_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/types&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the learning objects (content) types list available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/types.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects types available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Parameters : </strong></p>

<p>No parameters required</p>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/types.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects types returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
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
    "totalResults": 10,
    "value": {
        "i": "Interactive learning resource",
        "r": "Reading document",
        "v": "Video",
        "q": "Questionnaire",
        "s": "Work to submit",
        "d": "Document to download",
        "w": "Web site",
        "c": "In-class assessment",
        "p": "Image",
        "a": "Audio"
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
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#discussion" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#type" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object Type</a>

</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_objects_types_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/LearningObjects/Download/item.json-->
<div id="learner_learning_objects_download_item_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/Download/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to download locally (mobile device) the learning objects (content) available for the [authenticated learner](/ckauth_workflow.html) for offline access.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/Download/{learningObjectId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the download URL of learning object available for the [authenticated learner](/ckauth_workflow.html).</p>

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
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">item</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object session item Id.</td>
<td markdown="span"></td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/Download/32439.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects download url returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">downloadUrl</td>
<td markdown="span">string</td>
<td markdown="span">The download URL of the content.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalResults": 1,
    "value": {
        "downloadUrl": "https://xxxxxxxxxx.s3.amazonaws.com/ojne612-en-gb-default.zip?AWSAc"
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
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"learner cannot access this Learning Object"</td>
<td markdown="span">**403**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#learningObject" class="btn btn-default navbar-btn cursorNorm" role="button">Learning Object</a>
	 <a href="glossary.html#scorm" class="btn btn-default navbar-btn cursorNorm" role="button">Scorm</a>
</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_learning_objects_download_item_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>


<!--GET API/v1/REST/PathSessionFolders/list.json-->
<div id="learner_path_session_folders_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/PathSessionFolders/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to get the training session's folders available for the [authenticated learner](/ckauth_workflow.html) for offline access.</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/PathSessionFolders/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the session's folders available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The training session GUID.</td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<!--<tr>
<td markdown="span">infoFor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>onlyMobile</i> Default: empty</td>
</tr>-->
</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
GET /API/v1/REST/PathSessionFolders/list.json?sessionGuid=XXXX-ACC7-CE4F-363B-4225535CDAE5 HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of path session folders url returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">The session folder id.</td>
</tr>
<tr>
<td markdown="span">name</td>
<td markdown="span">string</td>
<td markdown="span">The session folder name.</td>
</tr>
<tr>
<td markdown="span">parent_id</td>
<td markdown="span">integer</td>
<td markdown="span">The session folder parent id.</td>
</tr>
<tr>
<td markdown="span">sort_order</td>
<td markdown="span">integer</td>
<td markdown="span">The session folder sort order.</td>
</tr>
<tr>
<td markdown="span">context_id</td>
<td markdown="span">integer</td>
<td markdown="span">The session folder context id.</td>
</tr>
</tbody>
</table>

<h3>Example of JSON response :</h3>
<pre>
<code class="language-json">
{
    "message": "OK",
    "success": true,
    "totalResults": 1,
    "value": [
        {
            "id": 10,
            "name": "Folder1",
            "parent_id": 0,
            "sort_order": 1,
            "context_id": 8,
            
            "id": 11,
            "name": "Folder 2",
            "parent_id": 10,
            "sort_order": 2,
            "context_id": 8,
                    
            "id": 12,
            "name": "Folder 3",
            "parent_id": 11,
            "sort_order": 3,
            "context_id": 8,
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
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Missing Mandatory Parameter: sessionGuid"</td>
<td markdown="span">**500**
</td>
</tr>
</tbody>
</table>

<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#training" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	  <a href="glossary.html#session_folder" class="btn btn-default navbar-btn cursorNorm" role="button">Session Folder</a>


</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_path_session_folders_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--POST API/v1/REST/Trackings/list.json-->
<div id="learner_trackings_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to Create/Retrieve/Update learning objects tracking lines available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/list.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects tracking information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">trackings</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The list of tracking to create/ retrieve or update.</td>
<td markdown="span">Array of json objects.</td>

</tr>
<tr>
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The tracking ID in the LMS Report. Mandatory if <b>updating an existing tracking line only.</b></td>
<td markdown="span"> Range >= 1</td>

</tr>
<tr>
<td markdown="span">itemId</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object GUID. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">ABCD123</td>

</tr>
<tr>
<td markdown="span">data</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the tracking row data.
</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td>The amount of pregression achieved (%).</td>
<td>
Min. 0 | Max. 100
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learner's Registration where this Learning Object is referenced. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The score the learner achieved in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">scoreMax</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The maximum score value available in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">sessionTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"><i>The amount of time spent by the learner in the current training session (seconds). Mandatory if <b>totalTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">totalTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The amount of total time spent by the learner in the current training session (seconds). Mandatory if <b>sessionTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">firstLaunchTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was first launch for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>
<tr>
<td markdown="span">completionTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was completed for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/Trackings/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

trackings=[{"completionTime":"2017-12-27 10:40:38","firstLaunchTime":"2017-03-27 10:40:38","trackingId":26116,"itemId":null,"progression":100,"registrationGuid":null,"score":1000,"scoreMax":100,"sessionTimeSpent":null,"totalTimeSpent":10000}, {"completionTime":"2017-12-27 10:40:38","firstLaunchTime":"2017-12-27 10:40:38","trackingId":26119,"itemId":null,"progression":0,"registrationGuid": null,"score":100,"scoreMax":null,"sessionTimeSpent":null,"totalTimeSpent":6000}]

</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>
<p>The response values contains a list of all the Trackings successfully created and/or updated.</p>

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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects tracking lines returned by the web-service.
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
{
    "message": "Trackings successfully created and/or updated.",
    "success": true,
    "totalResults": 2,
    "value": [
        {
            "firstLaunchTime": "2017-03-27 10:40:38",
            "completionTime": "2017-12-27 10:40:38",
            "id": 26116,
            "itemId": "32439",
            "progression": 100,
            "registrationGuid": "XXXX-21FD-EEBB-D8E8-XXXXXXX-XXXXXXX",
            "score": 1000,
            "scoreMax": 100,
            "timeSpent": 87367
        },
        {
            "firstLaunchTime": "2017-07-25 07:36:15",
            "completionTime": "2017-09-08 12:14:49",
            "id": 26119,
            "itemId": "32438",
            "progression": 100,
            "registrationGuid": "7F3F9052-21FD-EEBB-D8E8-9XXXXXXX-XXXXXXX"",
            "score": 0,
            "scoreMax": 0,
            "timeSpent": 3600
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
<td markdown="span">"Trackings successfully created and\/or updated"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Trackings partially created and/or updated. Errors list:SessionTimeSpent (n) and TotalTimeSpent (n) must not be sent together."</td>
<td markdown="span">**206**</td>
</tr>
<tr>
<td markdown="span">"Trackings partially created and/or updated. Errors list:ItemId and id must not be sent together.\nItemId and registrationGuid must bought be sent together."</td>
<td markdown="span">**206**</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter {trackings}"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
<div class="glossary">
     <b>Glossary: </b>
     <a href="glossary.html#learner" class="btn btn-default navbar-btn cursorNorm" role="button">Learner</a>
	 <a href="glossary.html#trainins" class="btn btn-default navbar-btn cursorNorm" role="button">Training</a>
	 <a href="glossary.html#session" class="btn btn-default navbar-btn cursorNorm" role="button">Session</a>
	  <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking</a>
	<a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>

	  


</div>

</div>
<div class="panel-footer">
<a href="/samples.html#learner_trackings_list_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--GET API/v1/REST/Trackings/1.json-->
<div id="learner_tracking_item_get" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to retrieve a learning object tracking row available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/{trackingId}.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning object tracking information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The tracking ID in the LMS Report. Mandatory if <b>updating an existing tracking line only.</b></td>
<td markdown="span"> Range >= 1</td>

</tr>
<tr>
<td markdown="span">itemId</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object GUID. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">ABCD123</td>

</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td>The amount of pregression achieved (%).</td>
<td>
Min. 0 | Max. 100
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learner's Registration where this Learning Object is referenced. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The score the learner achieved in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">scoreMax</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The maximum score value available in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">sessionTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"><i>The amount of time spent by the learner in the current training session (seconds). Mandatory if <b>totalTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">totalTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The amount of total time spent by the learner in the current training session (seconds). Mandatory if <b>sessionTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">firstLaunchTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was first launch for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>
<tr>
<td markdown="span">completionTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was completed for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>

</tbody>
</table>


<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}




<pre>
<code class="language-http">
GET /API/v1/REST/Trackings/26119.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Cache-Control: no-cache
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>
<p>The response values contains the tracking row information.</p>

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
<td markdown="span">totalResults</td>
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
{
    "message": "Tracking successfully read.",
    "success": true,
    "totalResults": 1,
    "value": {
        "firstLaunchTime": "2017-07-25 07:36:15",
        "completionTime": "2017-09-08 12:14:49",
        "id": 26119,
        "itemId": "32438",
        "progression": 100,
        "registrationGuid": "XXXX-21FD-EEBB-D8E8-9A4400581502",
        "score": 0,
        "scoreMax": 0,
        "timeSpent": 3600
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
<td markdown="span">"Tracking successfully read."</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in."</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"The requested tracking item is not related to the learner."</td>
<td markdown="span">**404**
</td>
</tr>
<tr>
<td markdown="span">"The requested tracking item was not found."</td>
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
	  <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking</a>
	<a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>


</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_trackings_item_get" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--POST API/v1/REST/Trackings/item.json-->
<div id="learner_tracking_item_post" class="panel panel-default">

<div class="panel-heading">

<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to create or update a learning object exsiting tracking row available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/item.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-success">POST</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning object tracking information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The tracking ID in the LMS Report. Mandatory if <b>updating an existing tracking line only.</b></td>
<td markdown="span"> Range >= 1</td>

</tr>
<tr>
<td markdown="span">itemId</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learning object GUID. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">ABCD123</td>

</tr>
<tr>
<td markdown="span">data</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">the tracking row data.
</td>
<td markdown="span"></td>

</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td>The amount of pregression achieved (%).</td>
<td>
Min. 0 | Max. 100
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The learner's Registration where this Learning Object is referenced. Mandatory if <b>creating a new tracking line only.</b></td>
<td markdown="span">abcdef-12345-XXXXXXX-XXXXXXX</td>

</tr>
<tr>
<td markdown="span">score</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The score the learner achieved in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">scoreMax</td>
<td markdown="span">float</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span"><i>The maximum score value available in the Learning Object.</td>
<td markdown="span">Range >= 0.0</td>

</tr>
<tr>
<td markdown="span">sessionTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span"><i>The amount of time spent by the learner in the current training session (seconds). Mandatory if <b>totalTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">totalTimeSpent</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">The amount of total time spent by the learner in the current training session (seconds). Mandatory if <b>sessionTimeSpent == null</b></td>
<td markdown="span">Range >= 0</td>

</tr>
<tr>
<td markdown="span">firstLaunchTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was first launch for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>
<tr>
<td markdown="span">completionTime</td>
<td markdown="span">datetime</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">The date and time when the Learning Object was completed for the Registration by the learner</td>
<td markdown="span">YYYY-MM-DD hh:ii:ss</td>

</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>
{{site.data.alerts.note}}
<p>This web-service needs an authentication cookie in the HTTP Header request be called.
</p>
Cookie name:
<pre>
EasyquizzServerSID<br>

</pre>
{{site.data.alerts.end}}{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how to set CrossKnowledge authentication cookie in your HTTP header request](/ckauth_workflow.html)." type="info" %}

<pre>
<code class="language-http">
POST /API/v1/REST/Trackings/item.json HTTP/1.1
Host: yourdomain.crossknowledge.com
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

trackingId=26116&totalTimeSpent=9000&score=6000&progression=50&firstLaunchTime=2018-03-28+10%3A40%3A38&completionTime=2018-03-31+10%3A40%3A38
</code>
</pre>

<p style="font-size: 15px"><strong>Response: </strong></p>
<p>The response values contains the tracking row information.</p>

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
<td markdown="span">totalResults</td>
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
{
    "message": "Tracking successfully",
    "success": true,
    "totalResults": 1,
    "value": {
        "firstLaunchTime": "2018-03-28 10:40:38",
        "completionTime": "2018-03-31 10:40:38",
        "id": 26116,
        "itemId": "32439",
        "progression": 100,
        "registrationGuid": "7F3F9052-21FD-XXXXXXX-XXXXXXX-D0F1-773F8B",
        "score": 6000,
        "scoreMax": 100,
        "timeSpent": 173767
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
<td markdown="span">"Tracking successfully"</td>
<td markdown="span">**200**</td>
</tr>
<tr>
<td markdown="span">"Date Times must be a valid SQL datetime (2018-03-31\n10:40:38 received).,The completion time should be a valide SQL date.."</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in."</td>
<td markdown="span">**401**
</td>
</tr>
<tr>
<td markdown="span">"Tracking not found: n."</td>
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
	  <a href="glossary.html#tracking" class="btn btn-default navbar-btn cursorNorm" role="button">Tracking</a>
	<a href="glossary.html#context" class="btn btn-default navbar-btn cursorNorm" role="button">Context</a>

	  


</div>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_trackings_item_post" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>

<!--GET API/v1/REST/search/lo
<div class="panel panel-default">

<div class="panel-heading">

<div class="panel-title">API/v1/REST/search/learningObject&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">

<p style="font-size: 15px"><strong>Description :</strong></p>
<p markdown="span">This web-service allow to search for learning objects (content) information available for the [authenticated learner](/ckauth_workflow.html).</p>

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/search/lo.json</i></p>
<p style="font-size: 15px"><strong>Method : </strong><span class="label label-info">GET</span></p>

<p style="font-size: 15px"><strong>Return :</strong></p>
<p>This web-service returns a json object with the learning objects information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">start</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">Index to start the search.</td>
</tr>
<tr>
<td markdown="span">limit</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Number of results to return</td>
</tr>
<tr>
<td markdown="span">keyword</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Search keyword.</td>
</tr>
<tr>
<td markdown="span">context</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">Search context(comma separated): lo | training</td>
</tr>
<tr>
<td markdown="span">contextId</td>
<td markdown="span">integer</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Search context id, session id</td>
</tr>
<tr>
<td markdown="span">lang</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">learner search language.
</td>
</tr>
<tr>
<td markdown="span">fetchSecondLanguage</td>
<td markdown="span">boolean</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Required" class="fa fa-check"></i></td>
<td markdown="span">Fetch the result for the second language: true | false.
</td>
</tr>
<tr>
<td markdown="span">content_editor</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Content editor.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Content type: 0 (all type)| i (interactive learning resource) | v (video) | r (reading document) | others (Others)
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Content duration: 0 (all durations)| less_10(-10 min) | 10_to_30 (10 to 30 min) | more_30 ( + 30 mins)
</td>
</tr>
<tr>
<td markdown="span">theme</td>
<td markdown="span">string</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Content theme.
</td>
</tr>
<tr>
<td markdown="span">sort</td>
<td markdown="span">array</td>
<td markdown="span"><i style="cursor: pointer" data-toggle="tooltip" data-original-title="Not required" class="fa fa-times"></i></td>
<td markdown="span">Content sort: date |views |rating
</td>
</tr>

</tbody>
</table>

<p style="font-size: 15px"><strong>Request : </strong></p>

<pre>
<code class="language-http">
GET /API/v1/REST/LearningObjects/list.json HTTP/1.1
Host: yourdomain.crossknowledge.com
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
<td markdown="span">totalResults</td>
<td markdown="span">integer</td>
<td markdown="span">The number of learning objects returned by the web-service.
</td>
</tr>
<tr>
<td markdown="span">value</td>
<td markdown="span">object</td>
<td markdown="span">An object or a list of objects containing the data in response to the request.
</td>
</tr>
<tr>
<td markdown="span">id</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object session item ID (context).
</td>
</tr>
<tr>
<td markdown="span">loId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object id.
</td>
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
<td markdown="span">code</td>
<td markdown="span">string</td>
<td markdown="span">The learnin object code.
</td>
</tr>
<tr>
<td markdown="span">locale</td>
<td markdown="span">string</td>
<td markdown="span">The language code of the learning object.
</td>
</tr>
<tr>
<td markdown="span">thumbnail</td>
<td markdown="span">object</td>
<td markdown="span">Thumbnail URIs of the learning object in 3 size: small | medium | large.
</td>
</tr>
<tr>
<td markdown="span">type</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type (in the example below i for Interactive content).
</td>
</tr>
<tr>
<td markdown="span">typeLabel</td>
<td markdown="span">string</td>
<td markdown="span">The learning object type label.
</td>
</tr>
<tr>
<td markdown="span">subtype</td>
<td markdown="span">string</td>
<td markdown="span">The learing object subtype.
</td>
</tr>
<tr>
<td markdown="span">author</td>
<td markdown="span">object</td>
<td markdown="span">The learing object author :  authorGuid (identifier) | authorFirstname (firstname) | authorLastname (lastname)
</td>
</tr>
<tr>
<td markdown="span">duration</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object duration (mins.).
</td>
</tr>
<tr>
<tr>
<td markdown="span">summary</td>
<td markdown="span">string</td>
<td markdown="span">The learing object summary.
</td>
</tr>
<td markdown="span">learningPoints</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learning points (What you will learn).
</td>
</tr>
<tr>
<td markdown="span">includedInLo</td>
<td markdown="span">string</td>
<td markdown="span">The learning object detailed summary.
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
<td markdown="span">totalRate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total rate.
</td>
</tr>
<tr>
<td markdown="span">totalViews</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object total views.
</td>
</tr>
<tr>
<td markdown="span">isFavourite</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object favourites number.
</td>
</tr>
<tr>
<td markdown="span">rate</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object learner rate.
</td>
</tr>
<tr>
<td markdown="span">launchDate</td>
<td markdown="span">string</td>
<td markdown="span">The learning object last access date (YYYY-MM-DD).
</td>
</tr>
<tr>
<td markdown="span">progression</td>
<td markdown="span">string</td>
<td markdown="span">The learning object learner progression (%).
</td>
</tr>
<tr>
<td markdown="span">trackingId</td>
<td markdown="span">integer</td>
<td markdown="span">The learning object tracking Id (can be used to get or set the tracking for a learner).
</td>
</tr>
<tr>
<td markdown="span">folder</td>
<td markdown="span">object</td>
<td markdown="span">
</td>
</tr>
<tr>
<td markdown="span">locales</td>
<td markdown="span">array</td>
<td markdown="span">The learning object available locales.
</td>
</tr>
<tr>
<td markdown="span">runtime</td>
<td markdown="span">string</td>
<td markdown="span">The learning object runtime.
</td>
</tr>
<tr>
<td markdown="span">isMobile</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is available for mobile.
</td>
</tr>
<tr>
<td markdown="span">isDownloadable</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is downloadable for offline access.
</td>
</tr>
<tr>
<td markdown="span">isMandatory</td>
<td markdown="span">boolean</td>
<td markdown="span">Define if the learning object is mandatory in the training session.
</td>
</tr>
<tr>
<td markdown="span">theme</td>
<td markdown="span">object</td>
<td markdown="span">The learning object theme.
</td>
</tr>
<tr>
<td markdown="span">modificationDate</td>
<td markdown="span">date</td>
<td markdown="span">The learning object last modification date (YYYY-MM-DD hh:ii:ss).
</td>
</tr>
<tr>
<td markdown="span">sortOrder</td>
<td markdown="span">integer</td>
<td markdown="span">The sort order of the learning object in the training session.
</td>
</tr>
<tr>
<td markdown="span">registrationGuid</td>
<td markdown="span">string</td>
<td markdown="span">The registration guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">trainingGuid</td>
<td markdown="span">string</td>
<td markdown="span">The trianing guid of the learner(learning object context).
</td>
</tr>
<tr>
<td markdown="span">sessionGuid</td>
<td markdown="span">string</td>
<td markdown="span">The training session guid of the learner (learning object context).
</td>
</tr>
<tr>
<td markdown="span">scormData</td>
<td markdown="span">object</td>
<td markdown="span">The tracking data of the learner on the learning object (Scorm 1.2/ 2004) : activity_url | activity_id | version | raw_tracking_data
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
    "totalResults": 6,
    "value": [
        {
            "id": 32439,
            "loId": 2337,
            "guid": "OJNE012",
            "title": "谈判准备十步曲",
            "code": "OJNE312",
            "locale": "zh-CHS",
            "thumbnail": {
                "small": "yourdomain-assets.crossknowledge.com/lo_picture/guid/OJNE312zh-CHS/width/120/height/67/loGuid/OJNE012/resourceType/C/",
                "medium": "yourdomain-assets.crossknowledge.com/lo_picture/guid/OJNE312zh-CHS/width/224/height/126/loGuid/OJNE012/resourceType/C/",
                "large": "yourdomain-assets.crossknowledge.com/lo_picture/guid/OJNE312zh-CHS/width/640/height/360/loGuid/OJNE012/resourceType/C/"
            },
            "type": "i",
            "typeLabel": "Session",
            "subtype": "cksession",
            "author": {
                "authorGuid": "RICHARD_ROE_70",
                "authorFirstName": "Richard",
                "authorLastName": "Roe"
            },
            "duration": 30,
            "summary": "要取得谈判的成功，首先必须精心准备。在谈判准备阶段要仔细分析你的谈判目标，预计对方的目标，考虑如何同时满足双方目标。此外，还需要设想各种可能的方案。谈判准备还涉及你的谈判策略。本课程将向你介绍好的销售准备的各个步骤，并通过实际案例，引导你体验整个过程。",
            "learningPoints": "<ul><li>谈判准备的不同步骤 </li><li>每个步骤中需要问的问题  </li><li>什么是“BATNA”？  </li><li>什么是谈判策略？</li></ul>",
            "includedInLO": "",
            "targetAudience": "所有想要获得谈判成功的人",
            "level": "2",
            "totalRate": 0,
            "views": 5,
            "isFavourite": 0,
            "rate": 0,
            "launchDate": null,
            "progression": "5",
            "trackingId": 26116,
            "folder": null,
            "locales": [
                "zh-CHS",
                "ja-JP",
                "fr-FR",
                "en-US",
                "en-GB",
                "de-DE",
                "es-ES",
                "nl-NL",
                "pl-PL",
                "pt-BR",
                "ru-RU"
            ],
            "runtime": "scorm",
            "isMobile": false,
            "isDownloadable": false,
            "isMandatory": false,
            "theme": {
                "theme": "Find John Doe at Tokyo."
            },
            "modificationDate": "2015-09-15 00:11:52",
            "sortOrder": 14,
            "registrationGuid": "XXXXXXXXX-21FD-EEBB-D8E8-XXXXXXXXX81502",
            "trainingGuid": "D65D7E08-223B-D132-7XXXXXXXXX916BA49",
            "sessionGuid": "392570XXXXXXXXX7-CE4F-363B-422XXXXXXXXXDAE5",
            "scormData": {
                "activity_url": "",
                "activity_id": 0,
                "version": "scorm2004",
                "raw_tracking_data": "{\"cmi._version\":\"1.0\",\"cmi.learner_id\":\"johndoe@isalive.com\",\"cmi.learner_name\":\"Mbouani,Brice\",\"cmi.extra_parameters\":\"student_e_mail=brice.mbouani@crossknowledge.com\",\"cmi.location\":\"\",\"cmi.completion_status\":\"incomplete\",\"cmi.completion_threshold\":\"1\",\"cmi.credit\":\"credit\",\"cmi.entry\":\"resume\",\"cmi.total_time\":0,\"cmi.max_time_allowed\":\"\",\"cmi.exit\":\"suspend\",\"cmi.session_time\":\"PT0H0M0S\",\"cmi.mode\":\"normal\",\"cmi.suspend_data\":\"\",\"cmi.launch_data\":\"\",\"cmi.progress_measure\":\"\",\"cmi.scaled_passing_score\":\"\",\"cmi.time_limit_action\":\"continue,no message\",\"cmi.success_status\":\"unknown\",\"cmi.learner_preference.language\":\"en-GB\",\"cmi.learner_preference.audio_level\":\"1\",\"cmi.learner_preference.audio_captioning\":\"0\",\"cmi.learner_preference.delivery_speed\":\"1\",\"cmi.score.raw\":\"\",\"cmi.score.min\":\"\",\"cmi.score.max\":\"\",\"cmi.score.scaled\":\"\",\"cmi.objectives._count\":\"0\",\"cmi.interactions._count\":\"0\"}"
            }
        }
	]
}
  
</code>
</pre>


<p style="font-size: 15px"><strong>Codes and messages: </strong></p>
<table class="code_messages">
<colgroup>
<col width="70%" />
<col width="30%" />
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
<td markdown="span">"Invalid parameter offset"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter limit"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'sort' must be in: view, rate, lastAccessDate, update"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Invalid parameter value: 'types' must be in: v, i, r, q, w, a, s, c, d, p"</td>
<td markdown="span">**400**
</td>
</tr>
<tr>
<td markdown="span">"Access Denied: Not logged-in"</td>
<td markdown="span">**401**
</td>
</tr>
</tbody>
</table>
</div>
<div class="panel-footer">
<a href="/samples.html#learner_authentication_api" class="btn btn-default"><span class="fa-stack fa-lg"><i class="fa fa-square fa-stack-2x"></i><i class="fa fa-code fa-stack-1x fa-inverse" data-toggle="tooltip" data-original-title="Get code snippet"></i></span>&nbsp;</a>
</div>

</div>-->