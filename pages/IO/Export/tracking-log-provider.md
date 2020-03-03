---
title: Tracking Log
keywords: 
last_updated: 24 August, 2017
tags: 
summary: "This provider generates a data report containing the dailty tracking logs data. "
sidebar: home_sidebar
permalink: training-log-provider.html
folder: Export
dynamic_content: true
note: >
    When using this provider, the <code class="highlighter-rouge">deltaMode</code> option will export all tracking logs for the full days of the delta period. <br/>
    For example, if you run the task 5 times in a row today (and there was no learner activity in the meantime), the 5 generated files will be identical (because the delta period = today, we export all tracking logs from today each time). 
columns: [reportId, reportGuid, candidateId, candidateGuid, candidateName, candidateFirstname, candidateLogin, 
    candidateEmail, candidateRefNumber, candidateCustomFieldGuid, candidateTimeZone, candidateSmartgroups,
    candidateEntityAncestors, candidateEntityName, trainingId, trainingGuid, trainingTitle, 
    trainingPathCode, sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, registrationGuid, 
    learningObjectGuid, contentGuid, contentTitle, contentRefNumber, contentLocale, learningObjectPublisher, learningObjectRealCompletionTime,
    trainingContentFolder, trainingContentMandatory, firstLaunchDate, completionTime, firstCompletionDate, progression, 
    score, status, timeGlobal, constantValue, logDate, templatedValue]
parameters: [dateFormat, dateTimeFormat, entityIds, modality, onlyFromImportedRegistrations, 
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