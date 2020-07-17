---
title: Session Metadata
keywords: training, session, export, detailed
last_updated: September, 2019
tags: 
summary: "The session metadata will contain detailed session data."
sidebar: home_sidebar
permalink: training-session-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It can be helpful when you need detailed information about the sessions (as <b>creation date, descriptions, number of learners, related training</b>). Those data are defined when the session is being created.
    <br/><br/>

    <u>Example:</u> 
        <i>The <b>Module A</b> session was created on <b>2020-06-15</b> in the "<b>Welcome aboard</b>" training. It would start on <b>2020-06-25</b> and up to <b>40</b> learners could enroll to this session.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [modality, title, description, sessionCreationDate, sessionPathModificationDate, sessionModificationDate, constantValue, 
    trainingId, trainingGuid, trainingPathCode, trainingTitle, sessionId, sessionGuid, maxNbLearners, sessionRegisteredLearners, 
    startDate, endDate, trainingStatus] 
parameters: [modality, trainingPathCode, sessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    sessionTimeFrames, sessionTimeFramesScale, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

## Session Metadata

It can be helpful when you need detailed information about the sessions (as creation date, descriptions, number of learners, related training). Those data are defined when the session is being created.

> Example: _The **Module A** session was created at **2020-06-15** in the "**Welcome aboard**" training. It would start at **2020-06-25** and up to **40** learners could enroll to this session._

To check an **export sample file**, [click here](https://).

<!--
### Example
```xml
<providers>
    <trainingSessionMetadataProvider>
        <columns>
            <trainingId/>
            <trainingStatus/>
            <sessionId/>
            <sessionGuid/>
            <modality/>
            <title/>
            <description/>
            <startDate/>
            <endDate/>
            <creationDate/>
            <pathModificationDate/>
            <modificationDate/>
            <registeredLearners/>
            <maxNbLearners/>
            <constantValue/>
        </columns>
        <parameters>
            <exportAllSessions>Y</exportAllSessions>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </trainingSessionMetadataProvider>
</providers>
```
-->