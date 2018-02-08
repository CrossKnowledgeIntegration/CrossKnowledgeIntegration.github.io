---
title: CAS
keywords: ...
last_updated: February 7, 2018
tags:
sidebar: home_sidebar
permalink: cas.html
folder: Authentication
---

## The Goal

This document aims to explain you the functionning of CAS Single Sign-On.

Note that our LMS relies on SAML to make CAS.

See about SAML [here] (http://developers.crossknowledge.com/saml.html).


## About CAS

The Central Authentication Service (CAS) is a single sign-on protocol for the web. Its purpose is to permit a user to access multiple applications while providing their credentials (such as userid and password) only once. It also allows web applications to authenticate users without gaining access to a user's security credentials, such as a password. The name CAS also refers to a software package that implements this protocol.

The SSO (Single Sign-On) allows to authenticate automatically a user or learner in the CrossKnowledge Learning Suite. Besides, it allows to execute several actions on the authenticated learner as:

* Register to a training Path
* Enroll to a training session
* Redirect to learning course page.


## Set up

Here you will find an example of configuration used by two of our customers :

![alt text](http://developers.crossknowledge.com/images/Cas_config.png)

It is possible to ask the exploitation to enable logs. 
With that you will be able to verify exchange data when you try to connect. Here an example of datas contained in Array :

2015-11-18T12:02:30+01:00 DEBUG LOG_AUTHENTICATION 
Array (
* [uid] => Array ( [0] => B00174424 )

* [username] => Array ( [0] => DUPONT )

* [givenName] => Array ( [0] => Jean )

* [EmailAddress] => Array ( [0] => [B00174424@customer.edu, jean.dupont@customer.edu, jdupont@customer.edu] )
)

## Identity search field

About provisioning parameters you have to match your authentication services response with the database. The main fields are :

* Reference number
* Name
* First name
* E-mail
* Login

## CAS logs

In order to debug a CAS setup, you can open an IT ticket and request them to enable the CAS (authentication) log.

This log will contain an array with the user attributes as sent by the IDP, which can be used to verify if we are binding the correct attributes to our CKLS user fields in the CAS config page in backoffice.

Once the logs are enabled, you can check them at Kibana ("ckls-logs"):

https://ckls-logs.crossknowledge.com

To see the array, you can use the following filter (change <instance_name> to a real instance)

vhost:<instance_name>.lms.crossknowledge.com AND log_type:app_auth AND message:Array

WARNING :: The activation of the logs impacts on the performance of the system. Do not forget to ask the IT to disable the logs after your analysis is concluded!
