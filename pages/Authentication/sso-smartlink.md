---
title: Single Sign-on
keywords: ...
last_updated: October 12, 2017
tags:
sidebar: home_sidebar
permalink: sso-smartlink.html
folder: Authentication
---

## The Goal

This document aims to explain you the functionning of CrossKnowledge Single Sign-On link and help you to build your own SSO link in the best way.

## General information

The SSO (Single Sign-On) allows to authenticate automatically a user or learner in the CrossKnowledge Learning Suite. 
Besides, it allows to execute several actions on the authenticated learner as:


* Register to a training Path
* Enroll to a training session
* Redirect to learning course page.


The SSO works both in HTTP and HTTPS. You can write it from 2 ways :


* With pretty url: firstname/John/name/Doe (parameters are not case sensitive, you can write Name, NAME etc)
* With POST parameters: If you want to hide information sent to CKLS instead of send everything by GET values, you can use POST parameters/values. You can also use both POST and GET, and in this case the GET overwrites the POST when the same parameter/value is found.


As described earlier, the SSO link allow to authenticate a learner and execute several actions beside the authentication - You can also build a SSO link without any actions, so your learner will be authenticate and redirect to the CKLS homepage.
The following lines are the important ones. We will explain you the parameters required to build your SSO.


We will consider 3 sections:


* Learner's datas section: datas to provide to identify a leaner for an authentication.
* Actions's datas section: datas to provide to execute an action on the authenticated learner.
* Security's datas section: How to build your hash key to securise your SSO link.


## Learner’s data


You can set a couple of parameters for a learner. Below is an exhaustive list of parameters available for a learner. (they are not case sensitive).


Parameters | Description
--- | ---
`name`| lastname of the learner
`firstname`| firstname of the learner
`login`| login of the learner
`ref_number`| reference number of the learner. It can be specific registration number from the third party system.
`email` | email of the learner.
`languages`| connection language of the learner like fr-FR, en-GB. If not set, the language of the browser is taken.
`activation` | values are D for disabled, a date for the date until the learner is active. Any other values will set the learner to active.
`group_name` | 	the name of the group the learner will be attached to. If the group doesn’t exist, the group will be created.
`group_id` | 	id or GUID of the group. The group must exist or an error will occur.
`guid` | to set values of learner's custom field, format is "guid/value/guid2/othervalue etc...

When Register (action which creates a user if he does not exists) is set to yes, you can set the value @ for Name, Firstname, Email, Language, Guids. 
If the learner is not found, a form will allow the learner to enter the values for the parameters set with an @.

For example if the parameters of the SSO are register/yes/name/@/firstname/@/ref_number/learner1 and if learner1 doesn’t exist, the learner will have to enter his name and firstname manually. 
For languages, a select list will be displayed with the list of locales available in the LMS (like the login page). 
Others parameters are available when asking the learner to complete his data, see the part 6 Loginbox.


### Identity search field


`identity_field` : This mandatory field allows to specify which learner data, into your SSO link, will be used to identify a learner in the Crossknowledge Learning Suite (CKLS).

The fields below can be used as a value for this parameter (key/value format) :

* `login`
* `learner_login`
* `candidate_login`
* `ref_number`
* `email`

`login` and `learner_login` are both alias of `candidate_login` parameter.

Example of use:

`https://my_CKLS_plateform.com/sso/identity_field/login/login/johndoe/email/john.doe@xyz.com/ref_number/14453X/register/yes`

The query above (without the security part) means that we are identifying a learner with his login, therefore, if no learner is found with the specified login value, it will be created, thanks to the parameter register/yes.
But if the learner is found with the specified login value, his datas will be only updated.


## Actions' datas


Parameters | Description
--- | ---
`register`| This parameter allows to create a learner on the plateform, if not existing before the authentication. Values are yes or no. The value is no by default. If set to yes, the learner will be created in the CKLS with the [learner datas] provided, if they are not provided, an error will occur. If set to no, the learner will not be created if not existing on the plateform.
`enroll` | values are yes or no. It will enroll the learner into a session if a session is specified (see below). It can be used to enroll a learner into a blended training when free registrations are allowed.
`individual` | 	values are yes or no. When a training is set in the SSO link, it will create a unique session for each learner.
`singleton` | values are yes or no. When a training is set in the SSO link, it will automatically create a unique session for all the learners using the SSO. If enroll, individual and singleton are set all together, an error will occur.
`training` | values are id or GUID of a training. It will redirect the learner to this training. If only the training is set in the url, the learner will be redirected to his last active session (except if singleton or individual is set). In all other case, the learner is redirected to the homepage.
`session` | values are id or GUID of a session. It will redirect the learner to the session. The learner is automatically registered to the session if Enroll is set to yes. In all other case, the learner is redirected to the homepage.
`content` | values are id or GUID of a content. It will redirect the learner to the learning course page of his last active session. In all other case, the learner is redirected to the homepage.

Training, session and content can all be in the url. 
The SSO system will verify the consistency between those parameters. 
If there is no consistency, for example the session and the training specified are not related, the learner will be redirected to the homepage with an error message. 
More generally, if the SSO can’t calculate the landing page, the learner will be redirected to the homepage with an error message.


## Security

Once you have built your SSO link by providing the required learner's data and the actions's data if needed, you have to build the hash key of your link in order to guarentee:
* The integrity of your datas
* The confidentiality of your datas

To ensure the security of your SSO links, some parameters will allow to validate or not the link.

Parameters | Description
--- | ---
`verify_email`| values are yes or no. If you set verify_mail to yes, you have to set an email before. By clicking on the first SSO link, the learner will receive an email. The learner will have to click on the link sent in the email (second SSO) to be redirected to the CKLS. If the learner can choose his email (email/@/verify_email/yes), he will receive the second SSO at the email address specified. As long as the learner hasn’t click on the link in the email, the first SSO will ask him to enter an email again. As soon as he clicks on the second SSO, he will be redirected to the CKLS. In both cases, the second SSO will be used when activated.
`hash`| the hash key is a mandatory parameter.It allows to handle the security of the SSO link.
`ts` | it’s the timestamp. It allows to set a validity time to the SSO. The date must be in UTC standard. The timestamp must be written this way (ISO 8601 modified) 2007-03-31T13:60:60Z-PT5M. The PT5M means that the link is valid only 5 minutes. Increase this parameter to increase the number of minutes.

### How to build your hash key ?


The hash key guarantees the security of your SSO link. It is built in a simple and specific way. See below for an example.
If we take our last query example, with our learner John doe. We can see that the security part, so the hash key, is missing:

`https://my_CKLS_plateform.com/sso/identity_field/login/login/johndoe/email/john.doe@xyz.com/ref_number/14453X/register/yes`

We will add the hash key in this link by using the parameter hash. 
The hash key is built with the concatenation of the string parameters of your SSO link + the public key. All encrypted with **MD5 algorithm**.

The string parameters in our previous link is:

`identity_field/login/login/johndoe/email/john.doe@xyz.com/ref_number/14453X/register/yes`

The public key is the API Key of your CKLS plateform. 
The API Key a is valid API key set in the configuration of your CKLS

In this example, to build our Hash Key, we will proceed as below:

`md5(API KEY + "identity_field/login/login/johndoe/email/john.doe@xyz.com/ref_number/14453X/register/yes/")`

**The last / at the end of your string parameters is mandatory.**

Finally, our SSO link will looks like this:

`https://my_CKLS_plateform.com/sso/identity_field/login/login/johndoe/email/john.doe@xyz.com/ref_number/14453X/register/yes/hash/defba1320fe55f97330c25e803193ca2`

Note: If a timestamp is set in your SSO link (parameter TS), you must include the timestamp in the hash.