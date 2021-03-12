---
title: Training Session Metadata
keywords:
last_updated: March, 2021
tags: 
summary: "Export the metadata of training sessions."
sidebar: home_sidebar
permalink: training-session-metadata-provider.html
folder: Export
dynamic_content: true
columns: [modality, title, description, creationDate, pathModificationDate, modificationDate, constantValue, 
    trainingId, trainingGuid, trainingPathCode, trainingTitle, sessionId, sessionGuid, maxNbLearners, registeredLearners, 
    startDate, endDate, trainingStatus, hasClassroomActivity] 
parameters: [modality, trainingPathCode, sessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    timeFrames, timeFramesScale, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

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
            <hasClassroomActivity/>
        </columns>
        <parameters>
            <exportAllSessions>Y</exportAllSessions>
            <dateFormat>MM-DD-YYYY</dateFormat>
            <onlyWithClassroomActivity>Y</onlyWithClassroomActivity>
        </parameters>
    </trainingSessionMetadataProvider>
</providers>