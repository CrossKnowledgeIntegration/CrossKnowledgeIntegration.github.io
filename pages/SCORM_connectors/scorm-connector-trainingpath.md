---
title: Training Path SCORM connectors
keywords: ...
last_updated: February 5, 2018
tags:
sidebar: home_sidebar
permalink: scorm-connector-trainingpath.html
folder: SCORM_connectors
---

## Pre-requisites

As our content delivery solution through Scorm is in SaaS, the first obvious prerequisite is to have an internet connection enabled on the testing workstation. 
PC / Workstation requirements are listed [here](http://developers.crossknowledge.com/CKLS-prerequisites)

## Basic scheme

![alt text](http://developers.crossknowledge.com/images/scorm_trainingpath.PNG)


## Scorm 1.2 connectors

We will deliver our Scorm packages based on the 1.2 standard. Our platform is certified by ADL.

## Tracking information

The SCORM packages send back the following data:

* Time spent
* Progression within the content (saved in the score.raw field)
* Status (incomplete/completed type)

The bookmarking (suspend_data) is saved on our side for each trainee as all the other information, so we don't need to send back this information to the third party LMS through the Scorm API.


## Delivery

We deliver one SCORM package per content item, per language. This allows us to propagate different localised metadata elements (title, description) to the client LMS. Learners have the possibility of switching from one language to another one in our content player depending on the content locales (and license).

## Manifest and metadatas

The title and description of the content is in the manifest file. Through the import of the Scorm package, those datas will be filled automatically in client LMS. If the client wants additional metadatas, these can be sent in a separate CSV file for the whole library (author, program)

