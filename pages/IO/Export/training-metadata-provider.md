---
title: Training Metadata
keywords: training, export, training date, date
last_updated: September, 2019
tags: 
summary: "The training metadata will allow you to have some important training data (as dates, description and modality)."
sidebar: home_sidebar
permalink: training-course-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx and Learning Channel trainings</b>. It will provide basic and important training data (as when the training was created and when the last update happened).
    <br/><br/>

    <u>Example:</u> 
        <i>The <b>Learning Channel</b> training "<b>Your role in the organization</b>" was created on <b>2020-05-20</b> and the last update was on <b>2020-06-28</b>.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [modality, title, description, trainingCreationDate, trainingPathModificationDate, trainingModificationDate, constantValue,trainingId, trainingGuid, trainingPathCode, trainingPublisher]
parameters: [modality, trainingPathCode, sessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    sessionTimeFrames, sessionTimeFramesScale, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

## Training Metadata

It is available for **Blendedx and Learning Channel trainings**. It will provide basic and important training data (as when the training was created and when the last update happened).

> Example: _The **Learning Channel** training "**Your role in the organization**" was created at **2020-05-20** and the last update was at **2020-06-28**._

To check an **export sample file**, [click here](https://).

<!--
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
-->
