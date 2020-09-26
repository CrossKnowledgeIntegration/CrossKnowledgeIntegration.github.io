---
title: Tracking Log
keywords: 
last_updated: 24 August, 2017
tags: 
summary: >
    This provider generates a data report containing the dailty tracking logs data. 
tip: >
    A tracking log represents the daily details of a tracking (a date, a progression, and some time spent). <br/>
    For example, if a learner launched a resource yesterday at 8:42AM, spent 20 minutes on it, but didn't complete it; launched the resource again today at 2:10PM, spent 10 minutes, and completed it, you will have:<br/>
    <ul>
        <li>one tracking row with first launch date = yesterday 8:42AM, last access date = today 2:20PM, time spent = 30 minutes, progression = completed</li>
        <li>two tracking logs: <br/>
            <ul>
                <li style="list-style-type: decimal;">one with log date = yesterday, time spent = 20 minutes, progression = incomplete</li>
                <li style="list-style-type: decimal;">the second with log date = today, time spent = 10 minutes, progression = completed</li>
            </ul>
        </li>
    </ul>
sidebar: home_sidebar
permalink: tracking-log-provider.html
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