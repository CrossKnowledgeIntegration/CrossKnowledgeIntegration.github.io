---
title: CrossKnowledge API Authentication Service.
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: 18/09, 2017
tags: 
summary: "This page gives an overview of the CrossKnowledge Authorization and Authentication scenarios that CrossKnwoledge supports, and provides links to more detailed content."
sidebar: home_sidebar
permalink: ckauth_workflow.html
folder: API CrossKnowledge Auth
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
h3{
	color: #4a4747
	}
</style>


<h2>Understand CKAuth. key principles.</h2>

<div>

	<p>Your client application requests user authentication credentials from the CrossKnowledge Authorization Server, then request an access token to the CrossKnowledge Authentication Server, extracts a token from the response, and sends the token to the CrossKnowledge Learner API that you want to access.</p>

		
	{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-mobile fa-stack-1x fa-inverse'></i></span>&nbsp;The CrossKnowedge Authorization & Authentication service is natively built to enable mobile application to access CrossKnowledge Learner API." type="success" %}


	<h2>Basic steps. </h2>
	
	All applications follow a basic pattern when accessing a CrossKnowledge Learner API using CKAuth. At a high level, you follow four steps:
	
	<h3> 1.Obtain an authentication token from the CrossKnowledge Authorization Server.</h3>
	<br/>
	<p>Before your client application can access user data using CrossKnowledge Learner API, it must obtain an authentication token that grants access to the API. There are several ways to make this requests.
	<br/>For example, your application can ask to the user to provide its 6 digits authorization code that will be used to get an authentication token on it's behalf. Or, your application can request for a 6 digits code by using the user identifier.</p>
	<p>If the CrossKnowledge Authorization Server grants the permission, it will sends back an authentication token to your application that will be used to get an access token to the API.</p>
	
	<h3> 2.Obtain an access token from the CrossKnowledge Authentication Server.</h3> 
	<br/>
	<p>After your application obtains an authentication token, it sends the token to a CrossKnowledge Authentication Server using an <code class="language-red">HTTP POST</code> request. The authentication server will then respond with an access token that will be used by your application to call CrossKnowledge API web-services.
	The access token is only valid for the current authenticated user on your application. This means it can't be used to get private data from another user.</p>
	
	<h3>3.Get user data using CrossKnowledge Learner API.</h3> 
	<p>Now that your application owns a valid access token, it can get user data using the CrossKnowledge Learner API web-services. Your application can call any of the web-services available using that access token.</p>
	
	
	<h2>Authentication and Authorization workflow</h2>

	<h3> 1. Application authorization based on user authorization code.</h3>
	<br/>
	<p>In this scenario, your application must use the 6 digits code provided by the user to get a granted access from the CrossKnowledge authorization Server.</p>
	
		{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-info fa-stack-1x fa-inverse'></i></span>&nbsp;The 6 digits code used by the user is available from the its CrossKnowlegde portal." type="info" %}
		<div>
			<img src="images/CKAUTH.png" alt="ckauth_workflow_1" title="ckauth_workflow_1" />
		</div>
		
	<h3> 2. Application authorization based on user identifier.</h3>
	<br/>
	<p>In this scenario, your application must use the user identifier to get an authorization token from the CrossKnowledge Authorization Server.</p>

		{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-info fa-stack-1x fa-inverse'></i></span>&nbsp;The user identifier choose by your application must be shared with the CrossKnowledge platform. If this identifier is valid, the CrossKnowledge Authorization Server will grant access to your application by responding with an authentication token." type="info" %}

		<div>
			<img src="images/CKAUTHv2.png" alt="ckauth_workflow_2" title="ckauth_workflow_2" />
		</div>
	<h2>CKAuth web-services.</h2>

	<p>To obtain an authentication token and an access token to the CrossKnowedge Learner API, your application must use the following CKAuth. web-services:
	
	<ul>
		<li>Get Authorization Token:<br/>
	
			<div id="offline_learner_credentials_get" class="panel panel-default">

			<div class="panel-heading">

			<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;<a href="api_web_services_list_and_details_admins.html#offline_learner_token_get" target="_blank">API/Admin/Learner/Authorization/Token/</a>
			&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
			</div>
			</div>
		</li>
	
	<li>Get Authentication Token: <br/>

		<div id="offline_learner_credentials_get" class="panel panel-default">

		<div class="panel-heading">

		<div class="panel-title"><span class="label label-info method">GET</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;<a href="api_web_services_list_and_details_admins.html#ckauth_learner_authenticate" target="_blank">API/Learner/Authenticate/</a>
		&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
		</div>
		</div>
	</li>
	<li>Get Access Token:<br/>
	
		<div id="online_learner_mobile_authentication_get" class="panel panel-default">

		<div class="panel-heading">

		<div class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;<a href="api_web_services_list_and_details.html#learner_mobile_login_post" target="_blank">API/Learner/mobileLogin/</a>&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
		</div>
		</div>
	</li>
	</ul>
	
<h2>Extract access token from authentication server response.</h2>
<p>To use the CrossKnowledge Learner API web-services, you'll need to extract the access token from the authentication server then set your access token as a cookie in your HTTP Request Header.</p>
<p>The following code samples show how to extract the access token when the authentication was a success.</p>

<div class="panel panel-default">
<div class="panel-heading">
<div id="learner_authentication_post" class="panel-title"><span class="label label-success method">POST</span>&nbsp;<i style="cursor: pointer" data-toggle="tooltip" data-original-title="HTTPS" class="fa fa-lock"></i>&nbsp;API/Learner/mobileLogin&nbsp;<span class="label label-warning" style="color: #77777a; background-color: #fff">version 1.0</span></div>
</div>
<div class="panel-body">
<p style="font-size: 15px"><strong>Endpoint :</strong> <i>API/v1/REST/Learner/mobileLogin.json</i></p>

<h4>Description:</h4>
<p markdown="span" >This web-service authenticates the learner by creating a HTTP Session on the server.</p>

<ul id="profileTabs" class="nav nav-tabs">
<li class="active" ><a href="#php" data-toggle="tab">PHP</a></li>
<li><a href="#csharp" data-toggle="tab">C#</a></li>
</ul>

<div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="php">
<pre>
<code class="language-php">
$curl = curl_init();
$cookie = "";

curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($curl, CURLOPT_HEADER, 1);

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "login=john.doe@veganmaster.com&password=bvupehp5z42fwj9uxyxv&deviceid=iphone10",
  CURLOPT_HTTPHEADER => array(
    "cache-control: no-cache",
    "content-type: application/x-www-form-urlencoded",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

//Grab access token from authentication server HTTP Response.

if ($err) {
  echo "cURL Error #:" . $err;
} else {

	 // get access token
	preg_match_all('/^Set-Cookie:\s*([^;]*)/mi', $response, $m);
	$cookie = $m[1][3];

}

//Call out a CrossKnowedge Learner API Web-Service by setting the access token in the HTTP Request Header.
curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, 0);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, 0);
curl_setopt($curl, CURLOPT_COOKIE, $cookie);

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json?john.doe@veganmaster.com",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "cache-control: no-cache",

  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
</code>
</pre>
</div>

<div role="tabpanel" class="tab-pane" id="csharp">
<pre>
<code class="language-csharp">
 public void call()
{
	var client = new RestClient("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/mobileLogin.json");

	var request = new RestRequest(Method.POST);
	request.AddHeader("cache-control", "no-cache");
	request.AddHeader("content-type", "application/x-www-form-urlencoded");
	request.AddParameter("application/x-www-form-urlencoded", "login=john.doe@veganmaster.com&password=bvupehp5z42fwj9uxyxv&deviceid=iphone10", ParameterType.RequestBody);
	IRestResponse response = client.Execute(request);

	//Extract access token from authentication server HTTP Reponse Header
	string header = response.Headers[5].ToString();
	string pattern = "(EasyquizzServerSID=[a-z0-9]+)(?!.*EasyquizzServerSID=[a-z0-9])";    // Variable Name 1

	var cookieAuthName = "";
	var cookieAuthValue = "";

	//Get access token 
	foreach (Match m in Regex.Matches(header, re2))
	{
		string[] cookieJar = m.Value.Split('=');
		cookieAuthName = cookieJar[0];
		cookieAuthValue = cookieJar[1];

	}


	//Call out a CrossKnowedge Learner API Web-Service by setting the access token in the HTTP Request Header.

	Uri dn = new Uri("https://yourdomain.crossknowledge.com/API/v1/REST/Learner/profile.json?john.doe@veganmaster.com");
	client.BaseUrl = dn;
	request.Method = Method.GET;
	request.AddHeader("cache-control", "no-cache");
	request.AddParameter(cookieAuthName, cookieAuthValue, ParameterType.Cookie);
	response = client.Execute(request);

	Console.Write(response.Content.ToString());
	Console.ReadLine();

   
}
</code>
</pre>
</div>

</div>
</div>
</div>
