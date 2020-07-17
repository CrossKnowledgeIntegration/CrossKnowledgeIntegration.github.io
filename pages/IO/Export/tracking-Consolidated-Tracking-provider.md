---
title: Tracking - Consolidated Tracking
keywords: consolidated, tracking, export, session, activity, learning resource, content, training, session level
last_updated: October, 2019
tags: tracking, export, consolidated, blendedx, learning channel, training, session, learner, session level, consolidated tracking, per session, summary
summary: "The consolidated tracking report will allow you to have the learner's tracking summarized per session."
sidebar: home_sidebar
permalink: consolidated-tracking-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx and Learning Channel trainings</b>. It will return the data related to the learner's sessions.
    <br/><br/>

    If you want to have tracking exports by content instead of by session, please take a look at <a href="tracking-provider.html">Tracking export</a>, <a href="activity-provider.html">Activity export</a> and <a href="class-based-training-provider.html">Classroom Activity export</a>.
    <br/><br/>

    <u>Example:</u> 
        Example: <i><b>Laurie</b> finished the session "<b>Session 01</b>" in "<b>First steps</b>" training. It started at "<b>2020-02-20 at 10:30:00 a.m</b>"  and finished at "<b>2020-04-20 at 06:00:00 p.m</b>". She earned "<b>80 points</b>"  and the training status is "<b>Completed</b>".</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/><br/>

    Can't you understand the differences between tracking exports? <a href="export-glossary.html#what-is-the-difference-between-all-these-tracking-exports">This page</a> can help you!<br/>
columns: [candidateId, candidateName, candidateFirstname, candidateLogin, candidateEmail, candidateRefNumber, candidateGuid, 
    candidateEntityAncestors, candidateEntityName, candidateCustomFieldGuid, candidateSmartgroups,
    lastPlatformAccessDate, nbLO, nbLOStarted, nbLOFinished, sessionRegistrationDate, sessionRegistrationGuid, sessionId, sessionTitle, 
    sessionGuid, sessionStartDate, sessionEndDate, trainingId, trainingTitle, trainingPathCode, trainingGuid, 
    catalogVisibility, trainingStatus, trainingModality, trainingPublisher, trainingChapters, trainingDuration, 
    sessionCompletionTime, sessionFirstLaunchDate, sessionProgression, progressionMandatory, sessionScore, scoreNPS, sessionStatus, thresholdReachedDate, sessionFirstCompletionDate, sessionTimeGlobal, timeSpentCBT, timeSpentDigital, sessionTimeSpent, constantValue]
parameters: [modality, trainingPathCode, completeSessionTitle, sessionGuid, trainingGuid, activityType, dateFormat, 
    dateTimeFormat, statusFormat, sessionReportStatus, withoutLaunchTime, deltaMode, sessionTimeGlobalFormat, ancestorsWithCurrent, 
    sessionTimeFrames, sessionTimeFramesScale, onlyFromImportedRegistrations, onlyFromImportedSessions, onlyFromImportedTraining, 
    publishers, sessionPreferredLocales, entityIds, learnersSmartGroups, trainingStatus, trainingPublishers, trainingStatusFormat, 
    catalogVisibility, trainingModalityFormat, sessionTimeFrameScaleMode, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

## Consolidated Tracking

It is available for **Blendedx and Learning Channel trainings**.

> Example: _**Laurie** finished the session "**Session 01**" in "**First steps**" training. It started at "**2020-02-20 at 10:30:00 a.m**"  and finished at "**2020-04-20 at 06:00:00 p.m**". She earned "**80 points**"  and the training status is "**Completed**"_.

To check an **export sample file**, [click here](https://).

Can't you understand the differences between tracking exports? [This page](http://localhost:4000/export-glossary.html#what-is-the-difference-between-all-these-tracking-exports) can help you!

<!--
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
-->
