---
title: Tracking Log
keywords: 
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: training-log-provider.html
folder: Export
dynamic_content: true
columns: [reportId, reportGuid, candidateId, candidateGuid, candidateName, candidateFirstname, candidateLogin, 
    candidateEmail, candidateRefNumber, candidateCustomFieldGuid, candidateTimeZone, candidateGroupAncestors, candidateSmartgroups,
    candidateEntityAncestors, candidateGroupName, candidateEntityName, trainingId, trainingGuid, trainingTitle, 
    trainingPathCode, sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, registrationGuid, 
    learningObjectGuid, contentGuid, contentTitle, contentRefNumber, contentLocale, learningObjectPublisher, learningObjectRealCompletionTime,
    trainingContentFolder, trainingContentMandatory, firstLaunchDate, completionTime, firstCompletionDate, progression, 
    score, status, timeGlobal, constantValue, logDate, templatedValue]
parameters: [dateFormat, dateTimeFormat, groupIds, entityIds, modality, onlyFromImportedRegistrations, 
    onlyFromImportedSessions, onlyFromImportedTraining, preferredLocales, publishers, reportStatus, statusFormat, 
    timeFrames, timeFramesScale, timeFrameScaleMode, timeGlobalFormat, trainingGuid, trainingPathCode, trainingStatus, 
    trainingPublishers, trainingStatusFormat, trainingModalityFormat, sessionTitle, sessionGuid, withoutLaunchTime, 
    deltaMode, ancestorsWithCurrent, learnersSmartGroups, catalogVisibility, templates, onlyHrisSelectedItems, stripHTML, 
    maxLength]
---

### Examples
```xml
<providers>
    <trackingLogProvider>
        <columns>
            <candidateId/>
            <candidateGuid/>
            <candidateRefNumber/>
            <candidateName/>
            <candidateFirstname/>
            <candidateLogin/>
            <candidateEmail/>
            <candidateGroupAncestors/>
            <candidateGroupName/>
            <candidateCustomFieldGuid/>
            <candidatePresentation/>
            <candidateTimeZone/>
            <contentGuid/>
            <learningObjectGuid/>
            <contentRefNumber/>
            <contentTitle/>
            <contentLocale/>
            <learningObjectPublisher/>
            <registrationGuid/>
            <sessionId/>
            <sessionTitle/>
            <sessionGuid/>
            <sessionStartDate/>
            <sessionEndDate/>
            <trainingId/>
            <trainingGuid/>
            <trainingPathCode/>
            <trainingTitle/>
            <trainingContentFolder/>
            <trainingContentMandatory/>
            <firstLaunchDate/>
            <completionTime/>
            <firstCompletionDate/>
            <progression/>
            <score/>
            <status/>
            <timeGlobal/>
            <constantValue/>
            <logDate/>
            <trainingModality/>
            <trainingPublisher/>
        </columns>
        <parameters>
            <dateTimeFormat>YYYY-MM-DD hh:ii:ss</dateTimeFormat>
        </parameters>
    </trackingLogProvider>
</providers>
```