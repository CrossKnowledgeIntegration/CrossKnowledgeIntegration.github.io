---
title: Learner API Web-services Samples.
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: 12/09, 2017
tags: 
summary: "The CrossKnowledge Learner API Web-services is built on HTTP REST pattern"
sidebar: home_sidebar
permalink: samples.html
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

<!--POST API/v1/REST/Learner/login.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_login_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;&nbsp;API/v1/REST/learner/login&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/login.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service authenticates the learner by creating a HTTP Session object on the server. As long as this HTTP Session is available, you'll be able to make web-services call out to get the data of the [authenticated learner](/ckauth_workflow.html). </p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
'cache-control' => 'no-cache',
'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
	"login" => "john.doe",
	"password" => "iamjohndoethevegan" //Your data here.
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
HttpResponse <String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json")
.header("content-type", "application/x-www-form-urlencoded")
.header("cache-control", "no-cache")
.body("login=john.doe&password=iamjohndoethevegan") //Your data here.
.asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "login=john.doe&password=iamjohndoethevegan", ParameterType.RequestBody); //Your data here.
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "login=john.doe&password=iamjohndoethevegan" //Your data here.

headers = {
	'content-type': "application/x-www-form-urlencoded",
	'cache-control': "no-cache",
	}

conn.request("POST", "/API/v1/REST/Learner/login.json", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="js">
<pre>
<code class="language-javascript">
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {"login" : "john.doe", "password" : "iamjohndoethevegan"}
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

<!--POST API/v1/REST/Learner/mobileLogin.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_mobile_login_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;&nbsp;API/v1/REST/learner/mobileLogin&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/mobileLogin.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service authenticates the learner by creating a HTTP Session object on the server. As long as this HTTP Session is available, you'll be able to make web-services call out to get the data of the [authenticated learner](/ckauth_workflow.html). </p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
'cache-control' => 'no-cache',
'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
	"login" => "john.doe",
	"password" => "iamjohndoethevegan", //Your data here.
	"deviceId" => "kale1"
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
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json")
.header("content-type", "application/x-www-form-urlencoded")
.header("cache-control", "no-cache")
.body("login=john.doe&password=iamjohndoethevegan&deviceId=kale1") //Your data here.
.asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp1">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "login=john.doe&password=iamjohndoethevegan&deviceId=kale1", ParameterType.RequestBody); //Your data here.
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python1">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "login=john.doe&password=iamjohndoethevegan&deviceId=kale1" //Your data here.

headers = {
	'content-type': "application/x-www-form-urlencoded",
	'cache-control': "no-cache",
	}

conn.request("POST", "/API/v1/REST/Learner/mobileLogin.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache",
  },
  "data": {"login" : "john.doe", "password" : "iamjohndoethevegan", "deviceId" : "kale1"}
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

<!--DELETE API/v1/REST/Learner/login.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_login_delete" class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;&nbsp;API/v1/REST/learner/login&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/learner/login.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service logs out the learner by killing a HTTP Session object on the server.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json');
$request->setMethod(HTTP_METH_DELETE);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');

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
HttpResponse<span markdown="span"><String></span> response = Unirest.delete("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json")
.header("content-type", "application/x-www-form-urlencoded")
.header("cache-control", "no-cache")
.asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp2">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json");
var request = new RestRequest(Method.DELETE);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python2">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = ""

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("DELETE", "/API/v1/REST/Learner/login.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json",
  "method": "DELETE",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {}
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

<!--DELETE API/v1/REST/Learner/mobileLogin.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_mobile_login_delete" class="panel-title"><span class="label label-danger method">DELETE</span>&nbsp;&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;&nbsp;API/v1/REST/learner/mobileLogin&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Learner/mobileLogin.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service logs out the learner by killing a HTTP Session object on the server.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json');
$request->setMethod(HTTP_METH_DELETE);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');

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
HttpResponse<span markdown="span"><String></span> response = Unirest.delete("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json")
.header("content-type", "application/x-www-form-urlencoded")
.header("cache-control", "no-cache")
.asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp3">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json");
var request = new RestRequest(Method.DELETE);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python3">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = ""

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("DELETE", "/API/v1/REST/Learner/mobileLogin.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json",
  "method": "DELETE",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {}
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

<!--GET API/v1/REST/learner/profile.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_profile_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/profile&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Learner/profile.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service allow to get the profile information of the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'learnerLogin' => 'john.doe' //Your data here.
));

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
<div role="tabpanel" class="tab-pane" id="java4">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json?learnerLogin=")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp4">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json?learnerLogin=richard.roe");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Learner/profile.json?learnerLogin=richard.roe", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json?learnerLogin=richard.roe",
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

<!--GET API/v1/REST/Learner/manager.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner-manager_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/manager&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Learner/manager.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web service returns learner’s managing information. It returns the active managers IDs of the [authenticated learner](/ckauth_workflow.html) as stored in CrossKnowledge database.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/manager.json');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}ho $ex;
}
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="java5">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/manager.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp5">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/manager.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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

<!-- GET API/v1/REST/learner/subordinates.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_subordinates_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/subordinates&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Learner/subordinates.json</i></p>
<h4>Description:</h4>
<p markdown="span">This web service returns learner’s managing information. It inherits from Manager as it returns the active subordinates IDs of the [authenticated learner](/ckauth_workflow.html) as stored in CrossKnowledge database.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Learner/subordinates.json');
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
<div role="tabpanel" class="tab-pane" id="java6">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/login.json")
.header("content-type", "application/x-www-form-urlencoded")
.header("cache-control", "no-cache")
.body("") //Your data here.
.asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp6">
<pre>
<code class="language-csharp">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/subordinates.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python6">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Learner/subordinates.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/subordinates.json",
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

<!--GET API/v1/REST/Discussions/list.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/learner/Discussions/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/list.json</i></p>
<h4>Description:</h4>
<p markdown="span">Returns available discussions of the connected learner and their comments. The discussions are returned from the newest to the oldest, accordingly to their visibility and the optionnal filter on context. Comments for a given discussion are returned from the newest to the oldest as well.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json');
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
<div role="tabpanel" class="tab-pane" id="java7">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp7">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python7">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache",
    }

conn.request("GET", "/API/v1/REST/Discussions/list.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json",
  "method": "GET",
  "headers": {
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

<!--PUT API/v1/REST/Discussions/Comments/{commentId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_comment_like_put" class="panel-title"><span class="label label-warning method">PUT</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/Comments/{commentId}&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/comments.json</i></p>
<h4>Description:</h4>
<p markdown="span">This web service allow the [authenticated learner](/ckauth_workflow.html) to like a comment.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Comments/277.json');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'like' => '1' //Your data here.
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
HttpResponse<span markdown="span"><String></span> response = Unirest.put("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Comments/277.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("like=1")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp8">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Comments/277.json");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "like=1", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python8">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "like=1"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("PUT", "/API/v1/REST/Discussions/Comments/277.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Comments/277.json",
  "method": "PUT",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {
    "like": "1"
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

<!--POST API/v1/REST/Discussions/list.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/list.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/list.json</i></p>
<h4>Description:</h4>
<p markdown="span">This web service allows the [authenticated learner](/ckauth_workflow.html) to create a new discussion with a new (first) post associated.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  "context" => "TrainingSession",
  "contextGuid" => "392570F0-ACC7-CE4F-363B-XXXXXXX",
  "comment" => "Bos Taurus.",
  "title" => "vegan beast"		//Your data here.
  
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
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("context=TrainingSession&contextGuid=392570F0-ACC7-CE4F-363B-XXXXXXX&comment=Bos Taurus&title=Vegan Beast")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp9">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "context=TrainingSession&contextGuid=392570F0-ACC7-CE4F-363B-XXXXXXX&comment=Bos Taurus&title=Vegan Beast", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);;
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python9">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "context=TrainingSession&contextGuid=392570F0-ACC7-CE4F-363B-XXXXXXX&comment=Bos Taurus&title=Vegan Beast";

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/Discussions/list.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/list.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
	},
  "data": {"context" : "TrainingSession", "contextGuid" : "392570F0-ACC7-CE4F-363B-XXXXXXX", "comment" : "Bos Taurus", "title" : "Vegan Beast"}
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

<!--GET API/v1/REST/Discussions/{discussionId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_item_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/{discussionId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web service allow to get all the comments of a given discussion available for a learner.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/193.json');
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
<div role="tabpanel" class="tab-pane" id="java10">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/193.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp10">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/193.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python10">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Discussions/193.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/193.json",
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

<!--POST API/v1/REST/Discussions/{discussionId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_item_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/{discussionId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web service allow to update a given discussion available for a learner by adding a new comment.</p>

<ul id="profileTabs11" class="nav nav-tabs">
<li class="active" ><a href="#php" data-toggle="tab">PHP</a></li>
<li><a href="#java" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp" data-toggle="tab">C#</a></li>
<li><a href="#python" data-toggle="tab">Python</a></li>
<li><a href="#js" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php11">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/197.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  "comment" => "Bos Taurus"
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
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/197.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("comment=Bos Taurus")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp11">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/197.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "comment=Bos Taurus", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python11">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "comment=Bos Taurus"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/Discussions/197.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/197.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {"comment" : "Bos Taurus"}
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

<!--POST API/v1/REST/Discussions/Follow/{discussionId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_discussions_follow_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Discussions/Follow/{discussionId}.json&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Discussions/Follow/{discussionId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web service allow to follow a given discussion available for the [authenticated learner](/ckauth_workflow.html) by adding a new comment.</p>

<ul id="profileTabs12" class="nav nav-tabs">
<li class="active" ><a href="#php" data-toggle="tab">PHP</a></li>
<li><a href="#java" data-toggle="tab">JAVA</a></li>
<li><a href="#csharp" data-toggle="tab">C#</a></li>
<li><a href="#python" data-toggle="tab">Python</a></li>
<li><a href="#js" data-toggle="tab">Javascript (Ajax)</a></li>			
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php12">
<pre>
<code class="language-php">
$request = new HttpRequest();
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Follow/199.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  "follow" => 1
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
HttpResponse<String> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Follow/199.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("follow=1")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp12">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Follow/199.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "follow=1", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python12">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "follow=1"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/Discussions/Follow/199.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Discussions/Follow/199.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {"follow" : 1}
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

<!--GET API/v1/REST/Trainings/list.json-->

<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trainings_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trainings/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trainings/list.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get the trainings information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/Trainings/list.json');
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
<div role="tabpanel" class="tab-pane" id="java13">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/Trainings/list.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp13">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Trainings/list.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/Trainings/list.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/Trainings/list.json",
  "method": "GET",
  "headers": {
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

<!--GET API/v1/REST/TrainingSessions/list.json-->

<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_training_sessions_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/TrainingSessions/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/TrainingSessions/list.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get the training sessions information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/TrainingSessions/list.json');
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
<div role="tabpanel" class="tab-pane" id="java14">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/TrainingSessions/list.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp14">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/TrainingSessions/list.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/TrainingSessions/list.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/TrainingSessions/list.json",
  "method": "GET",
  "headers": {
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

<!--GET API/v1/REST/LearningObjects/list-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/list.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get the learning objects (content) information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/list.json');
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
<div role="tabpanel" class="tab-pane" id="java15">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/list.json")
  .header("cache-control", "no-cache")
  .asString();;
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp15">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/list.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/LearningObjects/list.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/list.json",
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

<!--GET API/v1/REST/LearningObjects/{learningObjectId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_item_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/{learningObjectItemId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get a learning object (content) information available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'locale' => 'en-GB'
));

$request->setHeaders(array(
  'postman-token' => '6c2f9a9a-2b5e-30b2-b2b5-9a11b8520be4'
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
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json?locale=en-GB")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp16">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json?locale=en-GB");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python16">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/LearningObjects/32439.json?locale=en-GB", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json?locale=en-GB",
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

<!--POST API/v1/REST/LearningObjects/{learningObjectId}.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_item_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/{learningObjectItemId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to set vote or add to favourite a learning object (content) available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
	"vote" => 4,
	"favourite" => 0
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
HttpResponse<span markdown="span"><String></span> response = Unirest.post("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json")
  .header("content-type", "application/x-www-form-urlencoded")
  .header("cache-control", "no-cache")
  .body("vote=4&favourite=1")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp17">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/x-www-form-urlencoded");
request.AddParameter("application/x-www-form-urlencoded", "vote=4&favourite=1", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python17">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = "vote=4&favourite=1"

headers = {
    'content-type': "application/x-www-form-urlencoded",
    'cache-control': "no-cache"
    }

conn.request("POST", "/API/v1/REST/LearningObjects/32439.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/32439.json",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "cache-control": "no-cache"
  },
  "data": {"vote" : 4, "favourite" : 1}
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

<!--GET API/v1/REST/LearningObjects/themes.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_themes_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/themes&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">

<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/themes.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get the learning objects (content) themes list available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/themes.json');
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
<div role="tabpanel" class="tab-pane" id="java18">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/themes.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp18">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/themes.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python18">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/LearningObjects/themes.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/themes.json",
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

<!--GET API/v1/REST/LearningObjects/types.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_types_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/types&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/types.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to get the learning objects (content) types list available for the [authenticated learner](/ckauth_workflow.html).</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/types.json');
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
<div role="tabpanel" class="tab-pane" id="java19">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/types.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp19">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/types.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/LearningObjects/types.json", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/types.json",
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

<!--GET API/v1/REST/LearningObjects/Download/item.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_learning_objects_download_item_get"  class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/LearningObjects/Download/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/LearningObjects/Download/{learningObjectItemId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to download locally (mobile device) the learning objects (content) available for the [authenticated learner](/ckauth_workflow.html) for offline access.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/Download/32439.json');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  
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
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/Download/32439.json")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp20">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/Download/32439.json");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="python20">
<pre>
<code class="language-python">
import http.client

conn = http.client.HTTPSConnection("yourdomain.crossknowledge.com")

payload = ""

headers = {
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/LearningObjects/Download/32439.json", payload, headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/LearningObjects/Download/32439.json",
  "method": "GET",
  "headers": {
    "cache-control": "no-cache"
  },
  "data": {}
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

<!--GET API/v1/REST/PathSessionFolders/list.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_path_session_folders_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/PathSessionFolders/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/PathSessionFolders/list.json</i></p>


<h4>Description:</h4>
<p markdown="span">This web-service allow to get the training session's folders available for the [authenticated learner](/ckauth_workflow.html) for offline access.</p>

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
$request->setUrl('https://yourdomain.crossknowledge.com/API/v1/REST/PathSessionFolders/list.json');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'sessionGuid' => '392570F0-ACC7-CE4F-363B-XXXXXXXX'
));

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
<div role="tabpanel" class="tab-pane" id="java21">
<pre>
<code markdown="span" class="language-java">
HttpResponse<span markdown="span"><String></span> response = Unirest.get("https://yourdomain.crossknowledge.com/API/v1/REST/PathSessionFolders/list.json?sessionGuid=392570F0-ACC7-CE4F-363B-XXXXXXXX")
  .header("cache-control", "no-cache")
  .asString();
</code>
</pre>
</div>
<div role="tabpanel" class="tab-pane" id="csharp21">
<pre>
<code class="language-csharp">
var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/PathSessionFolders/list.json?sessionGuid=392570F0-ACC7-CE4F-363B-XXXXXXXX");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
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
    'cache-control': "no-cache"
    }

conn.request("GET", "/API/v1/REST/PathSessionFolders/list.json?sessionGuid=392570F0-ACC7-CE4F-363B-XXXXX", headers=headers)

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
  "url": "https://yourdomain.crossknowledge.com/API/v1/REST/PathSessionFolders/list.json?sessionGuid=392570F0-ACC7-CE4F-363B-4XXXXXXXXX",
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

<!--POST API/v1/REST/Trackings/list.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_list_post"  class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/list&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/list.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to Create/Retrieve/Update learning objects tracking lines available for the [authenticated learner](/ckauth_workflow.html).</p>

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

<!--GET API/v1/REST/Trackings/1.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_item_get" class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/{trackingId}.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to retrieve a learning object tracking row available for the [authenticated learner](/ckauth_workflow.html).</p>

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

<!--POST API/v1/REST/Trackings/item.json-->
<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_trackings_item_post"  class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/v1/REST/Trackings/item&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Trackings/item.json</i></p>

<h4>Description:</h4>
<p markdown="span">This web-service allow to create or update a learning object exsiting tracking row available for the [authenticated learner](/ckauth_workflow.html).</p>

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
</div>