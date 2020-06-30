---
title: Consolidated Tracking
keywords: 
last_updated: October, 2019
tags: 
summary: "This provider generates a data report containing tracking data at the session level (= registration)."
sidebar: home_sidebar
permalink: consolidated-tracking-provider.html
folder: Export
dynamic_content: true
columns: [candidateId, candidateName, candidateFirstname, candidateLogin, candidateEmail, candidateRefNumber, candidateGuid, 
    candidateEntityAncestors, candidateEntityName, candidateCustomFieldGuid, candidateSmartgroups,
    lastPlatformAccessDate, nbLO, nbLOStarted, nbLOFinished, registrationDate, registrationGuid, sessionId, sessionTitle, 
    sessionGuid, sessionStartDate, sessionEndDate, trainingId, trainingTitle, trainingPathCode, trainingGuid, 
    catalogVisibility, trainingStatus, trainingModality, trainingPublisher, trainingChapters, trainingDuration, 
    completionTime, firstLaunchDate, progression, progressionMandatory, score, scoreNPS, status, thresholdReachedDate, 
    firstCompletionDate, timeGlobal, timeSpentCBT, timeSpentDigital, timeSpent, constantValue]
parameters: [modality, trainingPathCode, sessionTitle, sessionGuid, trainingGuid, activityType, dateFormat, 
    dateTimeFormat, statusFormat, reportStatus, withoutLaunchTime, deltaMode, timeGlobalFormat, ancestorsWithCurrent, 
    timeFrames, timeFramesScale, onlyFromImportedRegistrations, onlyFromImportedSessions, onlyFromImportedTraining, 
    publishers, preferredLocales, entityIds, learnersSmartGroups, trainingStatus, trainingPublishers, trainingStatusFormat, 
    catalogVisibility, trainingModalityFormat, timeFrameScaleMode, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

### Example
```xml
<providers>
    <consolidatedTrackingProvider>
        <columns>
            <candidateId/>
            <candidateName/>
            <candidateFirstname/>
            <candidateLogin/>
            <candidateEmail/>
            <candidateRefNumber/>
            <candidateGuid/>
            <candidateEntityAncestors/>
            <candidateEntityName/>
            <candidateCustomFieldGuid label="Department">8345C0A3-B8AB-7F65-0638-39B0E1244AA8</candidateCustomFieldGuid>
            <lastPlatformAccessDate/>
            <nbLO/>
            <nbLOStarted/>
            <nbLOFinished/>
            <registrationDate/>
            <registrationGuid/>
            <sessionId/>
            <sessionTitle/>
            <sessionGuid/>
            <sessionStartDate/>
            <sessionEndDate/>
            <trainingId/>
            <trainingTitle/>
            <trainingPathCode/>
            <trainingGuid/>
            <catalogVisibility/>
            <trainingStatus/>
            <trainingModality/>
            <trainingPublisher/>
            <trainingChapters/>
            <trainingDuration/>
            <completionTime/>
            <firstLaunchDate/>
            <progression/>
            <progressionMandatory/>
            <score/>
            <status/>
            <thresholdReachedDate/>
            <firstCompletionDate/>
            <timeGlobal/>
            <constantValue/>
            <scoreNPS/>
            <timeSpentCB/>
            <timeSpentDigital/>
            <timeSpent/>
        </columns>
        <parameters>
            <dateTimeFormat>YYYY-MM-DD hh:ii:ss</dateTimeFormat>
            <timeFrames>3</timeFrames>
            <timeFramesScale>less_than_n_days</timeFramesScale>
            <timeFrameScaleMode>lastActivity,timeSpent</timeFrameScaleMode>
        </parameters>
    </consolidatedTrackingProvider>
</providers>
```
