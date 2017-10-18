---
title: Administration API Web-services Samples.
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: 12/09, 2017
tags: 
summary: "The CrossKnowledge Administration API Web-services is built on HTTP REST pattern"
sidebar: home_sidebar
permalink: samples_admin.html
folder: API Samples
---
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
</style>
<script>

	$("#toc").hide();

</script>

<!--GET API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_administrator_login_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Admin/{administrator_login}/AutoConnectionUrl/{context_type}/{context_guid}</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service will creates a SSO URL in order to sign-in an administrator to the back office. To generate the SSO link, the CKLS check only that the user exists and he is enabled. It does not check user rights and restrictions.</p>

<ul id="profileTabs" class="nav nav-tabs">
<li class="active" ><a href="#php" data-toggle="tab">PHP</a></li>
<li><a href="#java" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp" data-toggle="tab">C#</a></li>
<li><a href="#python" data-toggle="tab">Python</a></li>
<li><a href="#js" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438',
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl")
  .header("api-key", "14AA9064-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python">
<pre>
<code class="language-python">
import requests

url = "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Admin/admin/AutoConnectionUrl",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>

</div>

<!--PUT API/ADMIN/v1/REST/Administrator/{administrator_login}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_administrator_update_put" class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Administrator/{administrator_login}/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong><i> API/ADMIN/v1/REST/Administrator/{administrator_login}/
</i></p>
<h4>Description:</h4>
<p markdown="span" >This web-service updates the entity of the administrator in the database.</p>

<ul id="profileTabs1" class="nav nav-tabs">
<li class="active" ><a href="#php1" data-toggle="tab">PHP</a></li>
<li><a href="#java1" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp1" data-toggle="tab">C#</a></li>
<li><a href="#python1" data-toggle="tab">Python</a></li>
<li><a href="#js1" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php1">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Administrator/admin/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'entityGuid' => 'XXXX-289D-2D56-24DE-AC7140E412AA'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java1">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.put("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Administrator/admin/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("entityGuid=XXXX-289D-2D56-24DE-AC7140E412AA")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp1">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Administrator/admin/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "entityGuid=XXXX-289D-2D56-24DE-AC7140E412AA", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python1">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.jnstaging.crossknowledge.com")

payload = "entityGuid=XXXX-289D-2D56-24DE-AC7140E412AA"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache",
    }

conn.request("PUT", "/API/ADMIN/v1/REST/Administrator/admin/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js1">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Administrator/admin/",
  "method": "PUT",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  },
  "data": {
	'entityGuid' : 'XXXX-289D-2D56-24DE-AC7140E412AA'
	}
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Training/{training_guid}/Content/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_contents_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Content/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/Content/</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service allows to get the learning objects associated to a given training course.</p>

<ul id="profileTabs2" class="nav nav-tabs">
<li class="active" ><a href="#php2" data-toggle="tab">PHP</a></li>
<li><a href="#java2" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp2" data-toggle="tab">C#</a></li>
<li><a href="#python2" data-toggle="tab">Python</a></li>
<li><a href="#js2" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php2">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Content/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java2">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Content/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp2">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Content/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python2">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Content/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js2">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Content/",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Content/{content_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_learning_object_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Content/{content_guid}/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Content/{content_guid}/
</i></p>
<h4>Description:</h4>
<p markdown="span">This web-service allows to read the metadatas of a given learning object.</p>

<ul id="profileTabs3" class="nav nav-tabs">
<li class="active" ><a href="#php3" data-toggle="tab">PHP</a></li>
<li><a href="#java3" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp3" data-toggle="tab">C#</a></li>
<li><a href="#python3" data-toggle="tab">Python</a></li>
<li><a href="#js3" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php3">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-3919BAE58A2C/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java3">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-3919BAE58A2C/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp3">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-3919BAE58A2C/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python3">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-3919BAE58A2C/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js3">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Content/B6574E49-6B4F-1AC6-A461-3919BAE58A2C/",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Training/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service allows to get the list of existings trainings within the CrossKnowledge Learning Suite database.</p>

<ul id="profileTabs4" class="nav nav-tabs">
<li class="active" ><a href="#php4" data-toggle="tab">PHP</a></li>
<li><a href="#java4" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp4" data-toggle="tab">C#</a></li>
<li><a href="#python4" data-toggle="tab">Python</a></li>
<li><a href="#js4" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php4">
<pre>
<code class="language-php">

$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java4">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp4">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python4">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/ADMIN/v1/REST/Training", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js4">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Training/{training_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to read the metadatas of a given training course.</p>

<ul id="profileTabs5" class="nav nav-tabs">
<li class="active" ><a href="#php5" data-toggle="tab">PHP</a></li>
<li><a href="#java5" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp5" data-toggle="tab">C#</a></li>
<li><a href="#python5" data-toggle="tab">Python</a></li>
<li><a href="#js5" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php5">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java5">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp5">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python5">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Learner/manager.json", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js5">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/manager.json",
  "method": "GET",
  "headers": {
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!-- POST API/ADMIN/v1/REST/Training/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/</i></p>
<h4>Description:</h4>
<p markdown="span">This web-service allows to create a new training.</p>

<ul id="profileTabs6" class="nav nav-tabs">
<li class="active" ><a href="#php6" data-toggle="tab">PHP</a></li>
<li><a href="#java6" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp6" data-toggle="tab">C#</a></li>
<li><a href="#python6" data-toggle="tab">Python</a></li>
<li><a href="#js6" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php6">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'type' => 'learningChannel',
  'title' => 'Tofu Fighter!',
  'status' => 'P',
  'cost' => '300$',
  'language' => 'en-GB',
  'duration' => '1h 30.',
  'translations' => array(
					'en-US' => array(
						'title' => 'Vegan Master!'
						)
					)
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java6">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("type=learningChannel&title=Tofu%20Fighter!&status=P&cost=300%24&language=en-GB&duration=1h%2030.&translations%5Ben-US%5D%5Btitle%5D=Vegan%20Master!")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp6">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "type=learningChannel&title=Tofu%20Fighter!&status=P&cost=300%24&language=en-GB&duration=1h%2030.&translations%5Ben-US%5D%5Btitle%5D=Vegan%20Master!", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python6">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "type=learningChannel&title=Tofu%20Fighter!&status=P&cost=300%24&language=en-GB&duration=1h%2030.&translations%5Ben-US%5D%5Btitle%5D=Vegan%20Master!"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache",
    }

conn.request("POST", "/API/ADMIN/v1/REST/Training/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js6">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/",
  "method": "POST",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  },
  "data": {
    "type": "learningChannel",
    "title": "Tofu Fighter!",
    "status": "P",
    "cost": "300$",
    "language": "en-GB",
    "duration": "1h 30.",
    "translations" : {
		"en-US" : {
			"title" : "Vegan Master!"
			}
	}
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--PUT API/ADMIN/v1/REST/Training/{training_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_put" class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/</i></p>
<h4>Description:</h4>
<p markdown="span">This web-service allows to update an existing training course.</p>

<ul id="profileTabs7" class="nav nav-tabs">
<li class="active" ><a href="#php7" data-toggle="tab">PHP</a></li>
<li><a href="#java7" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp7" data-toggle="tab">C#</a></li>
<li><a href="#python7" data-toggle="tab">Python</a></li>
<li><a href="#js7" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php7">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/5D261940-A8D8-CE53-1E4F-F6E245D9DF25/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'translations' => array(
	'en-US' => array(
		'title' => 'Plant based fighter!'
		)
	)
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java7">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.put("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/5D261940-A8D8-CE53-1E4F-F6E245D9DF25/")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .body("translations%5Ben-US%5D%5Btitle%5D=Plant%20based%20fighter!")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp7">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/5D261940-A8D8-CE53-1E4F-F6E245D9DF25/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "translations%5Ben-US%5D%5Btitle%5D=Plant%20based%20fighter!", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python7">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "translations%5Ben-US%5D%5Btitle%5D=Plant%20based%20fighter!"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("PUT", "/API/ADMIN/v1/REST/Training/5D261940-A8D8-CE53-1E4F-F6E245D9DF25/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js7">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/5D261940-A8D8-CE53-1E4F-F6E245D9DF25/",
  "method": "PUT",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache",
  },
  "data": {
    "translations" : {
		"en-US" : {
			"title" : "Tofu Fighter!"
			}
	}
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Training/{training_guid}/Session/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_session_list_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Session/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Training/{training_guid}/Session/</i></p>
<h4>Description:</h4>
<p markdown="span">This web-service allows to read the sessions of a given training course existing within the CrossKnowledge Learning Suite database.</p>

<ul id="profileTabs8" class="nav nav-tabs">
<li class="active" ><a href="#php8" data-toggle="tab">PHP</a></li>
<li><a href="#java8" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp8" data-toggle="tab">C#</a></li>
<li><a href="#python8" data-toggle="tab">Python</a></li>
<li><a href="#js8" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php8">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Session/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java8">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Session/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp8">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Session/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python8">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Session/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js8">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/811BC183-B83E-7A8C-CA0D-B1A5E38F073D/Session/",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Session/{session_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_session_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/list.json</i></p>
<h4>Description:</h4>
<p markdown="span">This web-service allows to read the metadatas of a given session.</p>

<ul id="profileTabs9" class="nav nav-tabs">
<li class="active" ><a href="#php9" data-toggle="tab">PHP</a></li>
<li><a href="#java9" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp9" data-toggle="tab">C#</a></li>
<li><a href="#python9" data-toggle="tab">Python</a></li>
<li><a href="#js9" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php9">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/D71C8064-E21E-9499-F0CF-F4413413883C/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java9">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/D71C8064-E21E-9499-F0CF-F4413413883C/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp9">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/D71C8064-E21E-9499-F0CF-F4413413883C/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python9">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Session/D71C8064-E21E-9499-F0CF-F4413413883C/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js9">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/D71C8064-E21E-9499-F0CF-F4413413883C/",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--POST API/ADMIN/v1/REST/Training/{training_guid}/Session/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_session_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Training/{training_guid}/Session/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/{discussionId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to create a new training session to a given training course.</p>

<ul id="profileTabs10" class="nav nav-tabs">
<li class="active" ><a href="#php10" data-toggle="tab">PHP</a></li>
<li><a href="#java10" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp10" data-toggle="tab">C#</a></li>
<li><a href="#python10" data-toggle="tab">Python</a></li>
<li><a href="#js10" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php10">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/EEDA24F6-C3E7-53FD-A8E8-B300FEE8EE68/Session/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'title' => 'ToFu Fighter',
  'start' =>  '2017-09-27',
  'end' => '2018-09-27'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java10">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/EEDA24F6-C3E7-53FD-A8E8-B300FEE8EE68/Session/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body('title=Tofu Fighter&start=2017-09-27&end=2018-09-27')
  .asString();;
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp10">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/EEDA24F6-C3E7-53FD-A8E8-B300FEE8EE68/Session/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "title=Tofu Fighter&start=2017-09-27&end=2018-09-27", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python10">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "title=Tofu Fighter&start=2017-09-27&end=2018-09-27"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache",
    }

conn.request("POST", "/API/ADMIN/v1/REST/Training/EEDA24F6-C3E7-53FD-A8E8-B300FEE8EE68/Session/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js10">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Training/EEDA24F6-C3E7-53FD-A8E8-B300FEE8EE68/Session/",
  "method": "POST",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  },
  "data": {
  
	  'title' : 'ToFu Fighter',
	  'start' :  '2017-09-27',
	  'end' : '2018-09-27'
		}
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--PUT API/ADMIN/v1/REST/Session/{session_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_session_put"  class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>

<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Session/{session_guid}/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to update a given training session information.</p>

<ul id="profileTabs11" class="nav nav-tabs">
<li class="active" ><a href="#php11" data-toggle="tab">PHP</a></li>
<li><a href="#java11" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp11" data-toggle="tab">C#</a></li>
<li><a href="#python11" data-toggle="tab">Python</a></li>
<li><a href="#js11" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php11">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://presales.jnstaging.crossknowledge.com/API/ADMIN/v1/REST/Session/36FB0DA7-4C9D-DE71-6B13-FAEBB13B5E21/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'postman-token' => '552ed8b8-3e43-7cf4-9b0c-d497db9bf628',
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => '14AA9064-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(

  'translations'  => array(
				'en-US' => array(
					'active' => true
					)
				)
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java11">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.put("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/36FB0DA7-4C9D-DE71-6B13-FAEBB13B5E21/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("title=&start=&end=&translations%5Ben-GB%5D%5Bactive%5D=")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp11">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/36FB0DA7-4C9D-DE71-6B13-FAEBB13B5E21/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "title=&start=&end=&translations%5Ben-GB%5D%5Bactive%5D=", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python11">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "title=&start=&end=&translations%5Ben-GB%5D%5Bactive%5D="

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("PUT", "/API/ADMIN/v1/REST/Session/36FB0DA7-4C9D-DE71-6B13-FAEBB13B5E21/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js11">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/36FB0DA7-4C9D-DE71-6B13-FAEBB13B5E21/",
  "method": "PUT",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {
	
	'translations' : 
				'en-US' : {
					'active' => true
					}
				
  
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--POST API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_training_session_register_learner_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Session/{session_guid}/Register/{learner_guid}/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to register a learner to a give training session.</p>

<ul id="profileTabs12" class="nav nav-tabs">
<li class="active" ><a href="#php12" data-toggle="tab">PHP</a></li>
<li><a href="#java12" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp12" data-toggle="tab">C#</a></li>
<li><a href="#python12" data-toggle="tab">Python</a></li>
<li><a href="#js12" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php12">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/7687DDDE-0652-3C4D-908B-8475A9E0D1CD/Register/51711782-47C3-CD84-A35C-8AB8622AFCE6/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java12">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/7687DDDE-0652-3C4D-908B-8475A9E0D1CD/Register/51711782-47C3-CD84-A35C-8AB8622AFCE6/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp12">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/7687DDDE-0652-3C4D-908B-8475A9E0D1CD/Register/51711782-47C3-CD84-A35C-8AB8622AFCE6/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python12">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache",
    }

conn.request("POST", "/API/ADMIN/v1/REST/Session/7687DDDE-0652-3C4D-908B-8475A9E0D1CD/Register/51711782-47C3-CD84-A35C-8AB8622AFCE6/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js12">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Session/7687DDDE-0652-3C4D-908B-8475A9E0D1CD/Register/51711782-47C3-CD84-A35C-8AB8622AFCE6/",
  "method": "POST",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Registration/{registration_guid}/-->

<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_registration_get"  class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Registration/{registration_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Registration/{registration_guid}/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to get a given registration information</p>

<ul id="profileTabs13" class="nav nav-tabs">
<li class="active" ><a href="#php13" data-toggle="tab">PHP</a></li>
<li><a href="#java13" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp13" data-toggle="tab">C#</a></li>
<li><a href="#python13" data-toggle="tab">Python</a></li>
<li><a href="#js13" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php13">
<pre>
<code class="language-php">

$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/AC15C46A-5D10-3E39-9247-92E9A53222B2');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java13">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/AC15C46A-5D10-3E39-9247-92E9A53222B2")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp13">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/AC15C46A-5D10-3E39-9247-92E9A53222B2");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python13">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Registration/AC15C46A-5D10-3E39-9247-92E9A53222B2", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js13">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/AC15C46A-5D10-3E39-9247-92E9A53222B2",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--DELETE API/ADMIN/v1/REST/Registration/{registration_guid}/-->

<div class="panel panel-default">
<div class="panel-heading">
<div d="offline_registration_delete"  class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Registration/{registration_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Registration/{registration_guid}/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to delete a given registration object.</p>

<ul id="profileTabs14" class="nav nav-tabs">
<li class="active" ><a href="#php14" data-toggle="tab">PHP</a></li>
<li><a href="#java14" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp14" data-toggle="tab">C#</a></li>
<li><a href="#python14" data-toggle="tab">Python</a></li>
<li><a href="#js14" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php14">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/354131E0-A9D0-B239-F091-344F27E0A49A/');
$request->setMethod(HTTP_METH_DELETE);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java14">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.delete("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/354131E0-A9D0-B239-F091-344F27E0A49A/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp14">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/354131E0-A9D0-B239-F091-344F27E0A49A/");
var request = new RestRequest(Method.DELETE);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python14">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("DELETE", "/API/ADMIN/v1/REST/Registration/354131E0-A9D0-B239-F091-344F27E0A49A/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js14">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Registration/354131E0-A9D0-B239-F091-344F27E0A49A/",
  "method": "DELETE",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Learner/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_learner_get"  class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to search for a learner profile or to list all learners information.</p>

<ul id="profileTabs15" class="nav nav-tabs">
<li class="active" ><a href="#php15" data-toggle="tab">PHP</a></li>
<li><a href="#java15" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp15" data-toggle="tab">C#</a></li>
<li><a href="#python15" data-toggle="tab">Python</a></li>
<li><a href="#js15" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php15">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'name' => 'doe',
  'enabled' => 'true'
));

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java15">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://presales.jnstaging.crossknowledge.com/API/ADMIN/v1/REST/Learner/?name=doe&enabled=true")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp15">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/?name=doe&enabled=true");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python15">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/ADMIN/v1/REST/Learner/?name=doe&enabled=true", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js15">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/?name=doe&enabled=true",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--POST API/ADMIN/v1/REST/Learner/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_learner_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/
</div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to create a new learner.</p>

<ul id="profileTabs16" class="nav nav-tabs">
<li class="active" ><a href="#php16" data-toggle="tab">PHP</a></li>
<li><a href="#java16" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp16" data-toggle="tab">C#</a></li>
<li><a href="#python16" data-toggle="tab">Python</a></li>
<li><a href="#js16" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php16">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'login' => 'richard.roe',
  'name' => 'Roe',
  'firstname' => 'Richard',
  'enabled' => true
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java16">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("login=richard.roe&enabled=true")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp16">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "login=richard.roe&enabled=true", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python16">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "login=richard.roe&enabled=true"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache",
    }

conn.request("POST", "/API/ADMIN/v1/REST/Learner/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js16">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/",
  "method": "POST",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {
	"login": "richard.roe",
	"enabled" : true
	}
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/-->
<div class="panel panel-default">
<div class="panel-heading">
<div d="offline_learner_token_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/{learner_guid}/AuthToken/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to get the learner authentication token.</p>

<ul id="profileTabs17" class="nav nav-tabs">
<li class="active" ><a href="#php17" data-toggle="tab">PHP</a></li>
<li><a href="#java17" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp17" data-toggle="tab">C#</a></li>
<li><a href="#python17" data-toggle="tab">Python</a></li>
<li><a href="#js17" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php17">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/AuthToken');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java17">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/AuthToken")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp17">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/AuthToken");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python17">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/AuthToken", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js17">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/AuthToken",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--PUT API/ADMIN/v1/REST/Learner/{learner_guid}/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_learner_put" class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/themes.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to update a given learner profile information</p>

<ul id="profileTabs18" class="nav nav-tabs">
<li class="active" ><a href="#php18" data-toggle="tab">PHP</a></li>
<li><a href="#java18" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp18" data-toggle="tab">C#</a></li>
<li><a href="#python18" data-toggle="tab">Python</a></li>
<li><a href="#js18" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php18">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'login' => 'richard.roe@kale.com',
  'enabled' => 'false',
  'status' => 'N'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java18">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.put("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("login=richard.roe%40kale.com&enabled=false&status=N")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp18">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
request.AddParameter("application/x-www-form-urlencoded", "login=richard.roe%40kale.com&enabled=false&status=N", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python18">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "login=richard.roe%40kale.com&enabled=false&status=N"

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("PUT", "/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js18">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/4AB68D3C-7D28-82B0-1388-A60892F2299B/",
  "method": "PUT",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  },
  "data": {
    "login": "richard.roe@kale.com",
    "enabled": false,
    "status": "N"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_learner_registration_get"  class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/
</div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Learner/{learner_guid}/Registration/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to get the registrations of a given learner.</p>

<ul id="profileTabs19" class="nav nav-tabs">
<li class="active" ><a href="#php19" data-toggle="tab">PHP</a></li>
<li><a href="#java19" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp19" data-toggle="tab">C#</a></li>
<li><a href="#python19" data-toggle="tab">Python</a></li>
<li><a href="#js19" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php19">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/51711782-47C3-CD84-A35C-8AB8622AFCE6/Registration/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache'
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java19">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/51711782-47C3-CD84-A35C-8AB8622AFCE6/Registration/")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp19">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/51711782-47C3-CD84-A35C-8AB8622AFCE6/Registration/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python19">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/ADMIN/v1/REST/Learner/51711782-47C3-CD84-A35C-8AB8622AFCE6/Registration/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js19">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Learner/51711782-47C3-CD84-A35C-8AB8622AFCE6/Registration/",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Entity/-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_entity_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Entity/{entity_guid}&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Entity/</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allows to get a given entity information.</p>

<ul id="profileTabs20" class="nav nav-tabs">
<li class="active" ><a href="#php20" data-toggle="tab">PHP</a></li>
<li><a href="#java20" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp20" data-toggle="tab">C#</a></li>
<li><a href="#python20" data-toggle="tab">Python</a></li>
<li><a href="#js20" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php20">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'page' => '1',
  'title' => 'paris',
  'title_exact' => 'paris school of business'
));

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => 'XXXX-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java20">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/?page=1&title=paris&title_exact=paris%20school%20of%20business")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp20">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/?page=1&title=paris&title_exact=paris%20school%20of%20business");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python20">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/ADMIN/v1/REST/Entity/?page=1&title=paris&title_exact=paris%20school%20of%20business", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js20">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/?page=1&title=paris&title_exact=paris%20school%20of%20business",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/ADMIN/v1/REST/Entity/{entity_guid}-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="offline_entity_get"  class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/ADMIN/v1/REST/Entity/{entity_guid}&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/ADMIN/v1/REST/Entity/{entity_guid}</i></p>


<h4>Description:</h4>
<p markdown="span">This web-service allows to get a given entity information.</p>

<ul id="profileTabs21" class="nav nav-tabs">
<li class="active" ><a href="#php21" data-toggle="tab">PHP</a></li>
<li><a href="#java21" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp21" data-toggle="tab">C#</a></li>
<li><a href="#python21" data-toggle="tab">Python</a></li>
<li><a href="#js21" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php21">
<pre>
<code class="language-php">

$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/7D8532CB-E3C0-578F-4EE4-F39B406097E5');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'api-key' => '14AA9064-4E19-752A-DB81-5087AB7CA438'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java21">
<pre>
<code markdown="span" class="language-java">
HttpResponse<String> response = Unirest.get("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/7D8532CB-E3C0-578F-4EE4-F39B406097E5")
  .header("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp21">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/7D8532CB-E3C0-578F-4EE4-F39B406097E5");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("api-key", "XXXX-4E19-752A-DB81-5087AB7CA438");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python21">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'api-key': "XXXX-4E19-752A-DB81-5087AB7CA438",
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/ADMIN/v1/REST/Entity/7D8532CB-E3C0-578F-4EE4-F39B406097E5", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js21">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/ADMIN/v1/REST/Entity/7D8532CB-E3C0-578F-4EE4-F39B406097E5",
  "method": "GET",
  "headers": {
    "api-key": "XXXX-4E19-752A-DB81-5087AB7CA438",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--POST API/v1/REST/Trackings/list.json
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_list_post"  class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/list.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to Create/Retrieve/Update learning objects tracking lines available for the [authenticated learner](/api_web_services_list_and_details.htm#api_learner_auth).</p>

<ul id="profileTabs22" class="nav nav-tabs">
<li class="active" ><a href="#php22" data-toggle="tab">PHP</a></li>
<li><a href="#java22" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp22" data-toggle="tab">C#</a></li>
<li><a href="#python22" data-toggle="tab">Python</a></li>
<li><a href="#js22" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php22">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/list.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(
	
	//Your data here.
);

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java22">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/list.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("") //Your data here.
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp22">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/list.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "", ParameterType.RequestBody); //Your data here.

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python22">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "" //Your data here.

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/Trackings/list.json", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js22">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/list.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": "" //Your data here.
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--GET API/v1/REST/Trackings/1.json
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_item_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/{trackingId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to retrieve a learning object tracking row available for the [authenticated learner](/api_web_services_list_and_details.htm#api_learner_auth).</p>

<ul id="profileTabs23" class="nav nav-tabs">
<li class="active" ><a href="#php23" data-toggle="tab">PHP</a></li>
<li><a href="#java23" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp23" data-toggle="tab">C#</a></li>
<li><a href="#python23" data-toggle="tab">Python</a></li>
<li><a href="#js23" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php23">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/26116.json');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java23">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/26116.json")
  .header("cache-control", "no-cache")
  .asString();;
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp23">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/26116.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python23">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Trackings/26116.json", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js23">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/26116.json",
  "method": "GET",
  "headers": {
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>

<!--POST API/v1/REST/Trackings/item.json
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_item_post"  class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/item.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to create or update a learning object exsiting tracking row available for the [authenticated learner](/api_web_services_list_and_details.htm#api_learner_auth).</p>

<ul id="profileTabs24" class="nav nav-tabs">
<li class="active" ><a href="#php24" data-toggle="tab">PHP</a></li>
<li><a href="#java24" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp24" data-toggle="tab">C#</a></li>
<li><a href="#python24" data-toggle="tab">Python</a></li>
<li><a href="#js24" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php24">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/item.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  "trackingId" => 26116,
  "progression" => 100,
  "score" => 100,
  "firstLaunchTime" => "2018-03-28 10:40:38",
  "completionTime" => "2018-03-31 10:40:38",
  "sessionTimeSpent" => "3600"
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java24">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/item.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("trackingId=26116&progression=100&score=100&firstLaunchTime=2018-03-28%2010%3A40%3A38&completionTime=2018-03-31%2010%3A40%3A38&sessionTimeSpent=3600")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp24">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/item.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "trackingId=26116&progression=100&score=100&firstLaunchTime=2018-03-28%2010%3A40%3A38&completionTime=2018-03-31%2010%3A40%3A38&sessionTimeSpent=3600", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python24">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "trackingId=26116&progression=100&score=100&firstLaunchTime=2018-03-28%2010%3A40%3A38&completionTime=2018-03-31%2010%3A40%3A38&sessionTimeSpent=3600"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/Trackings/item.json", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js24">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Trackings/item.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
    "postman-token": "88c9f118-6087-da5f-5d93-803251a19fff"
  },
  "data": {
	"trackingId" : "26116",
	"sessionTimeSpent" : 3600,
	"score" : "100",
	"sessionTimeSpent" : "3600",
    "firstLaunchTime": "2018-03-28 10:40:38",
    "completionTime": "2018-03-31 10:40:38"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
</code>
</pre>
</div>
</div>
</div>
</div>-->