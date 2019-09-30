---
title: Training Course Metadata
keywords:
last_updated: September, 2019
tags: 
summary: "Export the metadata of training courses."
sidebar: home_sidebar
permalink: training-course-metadata-provider.html
folder: Export
dynamic_content: true
columns: [modality, title, description, creationDate, pathModificationDate, modificationDate, constantValue,
    trainingId, trainingGuid, trainingPathCode, trainingPublisher]
parameters: [modality, trainingPathCode, sessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    timeFrames, timeFramesScale, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

### Example
```xml
<providers>
    <trainingCourseMetadataProvider>
        <columns>
            <modality/>
            <title/>
            <description/>
            <creationDate/>
            <pathModificationDate/>
            <modificationDate/>
            <trainingId/>
            <trainingGuid/>
            <trainingPathCode/>
            <trainingPublisher/>
            <constantValue/>
        </columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </trainingCourseMetadataProvider>
</providers>
```
