---
title: OAuth2
keywords: ...
last_updated: October 24, 2017
tags:
sidebar: home_sidebar
permalink: oauth2.html
folder: Authentication
---

## About OAuth2.0


OAuth2.0 is an authentication framework that provides a way for apps to gain limited access to a user's protected resources (provided by CrossKnowledge Learning Suite in this scope), without the need for the user to divulge their login credentials to the app.

From that framework, a third-party client application can obtain limited access to an HTTP(S) service to be granted by the resource owner by orchestrating an approval interaction between the resource server (RS) and the Authentication Server (AS).


## CrossKnowledge Learning Suite as Service Provider

Sometimes our clients need to reuse their users database, and has that service provided from one single central service, the Authentication Server. 
One or more third-party HTTP(S) client applications can connect to and authenticate their users without having access to the users database (from the Authentication Server). 
CrossKnowledge Learning Suite (CKLS) can (and is not limited to) integrate as a Resource Server (and Resource Owner) to an Authentication Server using OAuth2.0 framework.

* `Authentication Server (AS)`: The entity in charge of granting access through the OAuth2.0 framework, to the list of available clients (The client’s central authentication service).
* `Client (CLI)`: Some external app service that refers to the resource owner for granting access to limited access resource (The browser for us).
* `Resource Owner (RO)`: An HTTP(S) entity that is capable of granting access to a limited access resource (CrossKnowledge and their partners through CKLS).
* `Resource Server (RS)`: An HTTP(S) service or partner hosts the Protected Resource for the Resource Owner. (CrossKnowledge Learning Suite).
* `Protected Resource (PR)`: Data owned by the Resource Owner.
* `Authorization Grant (AG)`: Gives the Client permission to retrieve an access token on behalf of the end user.
* `Access Token (AT)`: A long string of characters that serves as a credential used to access protected resources.

From that approach, the ROcan delegate to an AS if an end-user has permission to access a PR through a CLI.


## How to set up

To have that setup, the AS accesses its own clients managing tool to add a valid RS service to its clients list. 
On the TP side, it the setup is done based on the information based on the RO setup, and which properties are available.

### Setup the Resource Owner party

For setting up a new client to a resource owner, follow these steps standards steps (they may vary depending on your resource owner’s implementation).
1.	Add a new application
2.	When asked for the application platform, select Website (or HTTP service)
3.	Fill in the application name. This name will be displayed to learners when they log in for the first time, so it is recommended to include the instance's name in it.
4.	If available, on the confirmation pop-up, choose the category that best suits your CKLS platform.
5.	From the client page, copy the ClientID and ClientSecret, and fill in the Contact Email field
6.	On the Advanced Settings page, in the Security section, fill in the Valid OAuth redirect URIs field with the following URLs (if your instance supports HTTPS, write 'https://' instead of 'http://'):
  a.	http://{Your instance URL}
  b.	http://{Your instance URL}/authentication/OAuth2/callback.php?driverType=TYPE_BO
  c.	http://{Your instance URL}/authentication/OAuth2/callback.php?driverType=TYPE_FO
7.	Check the client status
8.	Confirm the settings on success.

### Setup the Third-Party Client

For setting up a new resource owner to the third-party client, the following information are required:

Required informations | Description
--- | ---
`Attribute to login` | This is the path to the element of the json returned by the resource endpoint which will be used to match an existing learner. Basically, if you choose to match an email adress in the CKLS Field used for authentication, it will be the path to email adresse of the user in the json.
`Authorization endpoint URL` |the url of the Authorisation Server (eg : https://www.facebook.com/dialog/oauth)
`Scope (comma-separated list)` | the scope we want to reach, basically it is a group of data defined by the resource endpoint we want to get, which will require authorisation by the user at first connection on the authorisation server ( eg : email)
`Token endpoint URL` | the url of the Authorization Server which will deliver the token with the code returned by the Authorization endpoint ( eg : https://graph.facebook.com/oauth/access_token)
`Token mapping` | in the json returned by the Token Endpoint, the path to the token, level being materialized by >. ( eg : access_token )
`Resource endpoint URL` | the url to request for user information with the token ( eg : https://graph.facebook.com/me?fields=email,first_name,last_name)
`Pass token parameter to resource endpoint as` | [GET Parameter / Header attribute] select how the token is passed in the request, either as a get parameter or as a header attribute ( eg : Header attribute )
`Token index in request` | the name of the token parameter in either the Get of the Header ( when in header, most of the time it is "Bearer", and as get parameter "token", then again it's up to the foreign server this is not an Oauth2 standard). (eg : OAuth )
`Resource fields mapping` | Mapping in the json returned by the resource server of the fields, level being materialized by the '>' as for the token.

* First name field: first_name
* Last name field: last_name
* Email field: email
* Picture URL field: (eg: http(s)//someserver.com/user_picture)


## How it works

On the RS side, we can configure two different results from a successful assertion, providing real time user provisioning or not.
* If user provisioning is enabled, the user will be created and/or updated on each connection. 
* If no provisioning is enabled, the user must exist as the RS side so it can correctly authenticate there.

On provisioning mode, the provisioned data depends on properties provided from the AS.

On a non-provisioning scenario, please consult a CrossKnowledge Integration Engineer for user import options available, whenever needed.

Please see the image below for a summary on that workflow.

![alt text](http://developers.crossknowledge.com/images/oauth2workflow.png)

`Illustration 1: Oauth2 Authentication workflow`

