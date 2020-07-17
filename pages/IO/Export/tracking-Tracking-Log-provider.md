---
title: Tracking - Tracking Log
keywords: tracking, log, export, detailed, blendedx, learning channel, activity, learning resource, content, training, session, actions, action level
last_updated: 24 August, 2017
tags: tracking, log, export, blendedx, learning channel, learning resource, content, training, session, learner, log level, per content
summary: "The tracking log will allow you to have the record of each learner's action per content. It's our most detailed level for tracking export."
tip: >
    A tracking log represents the daily details of a tracking (<b>a content, a date, a progression, a status and some time spent</b>). <br/>
    For example, if the learner accessed a content yesterday, spent 20 minutes on it and didn't complete it. But today, he launched the resource again, spent 10 minutes and completed it, you will have:<br/>
    <ul>
        <li>One content tracking with <i>launch date</i> = yesterday, <i>last access date</i> = today, <i>time spent</i> = 30 minutes, <i>progression</i> = completed</li>
        <li>Two tracking logs: <br/>
            <ul>
                <li style="list-style-type: decimal;">One with <i>launch date</i> = yesterday, <i>time spent</i> = 20 minutes, <i>progression</i> = incomplete</li>
                <li style="list-style-type: decimal;">The second one with <i>launch date</i> = today, <i>time spent</i> = 10 minutes, <i>progression</i> = completed</li>
            </ul>
        </li>
    </ul>
note: >
    When using this export, the <b>deltaMode</b> option will export all tracking logs for the full days of the delta period. <br/>
    For example: If you run the task 5 times in a row today (and there was no learner activity in the meantime), the 5 generated files will be identical (because the delta period = today will export all tracking logs from today each time). 
sidebar: home_sidebar
permalink: tracking-log-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Learning Channel and Blendedx trainings</b>. The same learner can have several actions in the same content at different times.
    <br/><br/>
    
    If you want to have tracking exports by content instead of by actions, please take a look at <a href="tracking-provider.html">Tracking export</a>, <a href="activity-provider.html">Activity export</a> and <a href="class-based-training-provider.html">Classroom Activity export</a>.
    <br/><br/>

    <u>Example:</u> 
    <li>
        <i>
            <b>Laurie</b> accessed "<b>Welcome to our team</b>" video in session "<b>Session 01</b>" in "<b>First steps</b>" training and spent <b>00:03:00 minutes</b> on it. It started on <b>2020-02-10 at 10:30:00 a.m</b> and it is <b>not finished</b> yet. She <b>didn't earn points</b> and the content status is "<b>Incomplete</b>".
    </li>
    <li>
            Also, <b>Laurie</b> accessed "<b>Welcome to our team</b>" video in session "<b>Session 01</b>" in "<b>First steps</b>" training and spent more <b>00:01:00 minute</b> on it. It was on <b>2020-02-10 at 06:00:00 p.m</b> and it was <b>finished</b> on <b>2020-02-10 at 06:01:00 p.m</b>. She earned <b>4 points</b> and the content status is "<b>Completed</b>".
        </i>
    </li>
    <br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/><br/>

    Can't you understand the differences between tracking exports? <a href="export-glossary.html#what-is-the-difference-between-all-these-tracking-exports">This page</a> can help you!<br/>
columns: [reportId, reportGuid, candidateId, candidateGuid, candidateName, candidateFirstname, candidateLogin, 
    candidateEmail, candidateRefNumber, candidateCustomFieldGuid, candidateTimeZone, candidateSmartgroups,
    candidateEntityAncestors, candidateEntityName, trainingId, trainingGuid, trainingTitle, 
    trainingPathCode, sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, learningObjectRegistrationGuid, 
    learningObjectGuid, contentGuid, contentTitle, contentRefNumber, contentLocale, learningObjectPublisher, learningObjectRealCompletionTime,
    trainingContentFolder, trainingContentMandatory, contentFirstLaunchDate, contentCompletionTime, contentFirstCompletionDate, learningObjectProgression, 
    learningObjectScore, learningObjectStatus, trackingLogTimeGlobal, constantValue, logDate, templatedValue]
parameters: [dateFormat, dateTimeFormat, entityIds, modality, onlyFromImportedRegistrations, 
    onlyFromImportedSessions, onlyFromImportedTraining, contentPreferredLocales, publishers, contentReportStatus, statusFormat, 
    contentTimeFrames, contentTimeFramesScale, contentTimeFrameScaleMode, contentTimeGlobalFormat, trainingGuid, trainingPathCode, trainingStatus, 
    trainingPublishers, trainingStatusFormat, trainingModalityFormat, completeSessionTitle, sessionGuid, withoutLaunchTime, 
    deltaMode, ancestorsWithCurrent, learnersSmartGroups, catalogVisibility, templates, onlyHrisSelectedItems, stripHTML, 
    maxLength]
---

## Tracking Log

It is available for **Learning Channel and Blendedx trainings**. The same learner can have several actions in the same content at different times.

If you want to have tracking exports by content instead of by action, please take a look at [Tracking export](htttp://localhost:4000/tracking-provider.html) and [Activity export](htttp://localhost:4000/activity-provider.html).

> Example: _**Laurie** accessed "**Welcome to our team**" video in session "**Session 01**" in "**First steps**" training and spent **00:03:00 minutes** on it. It started on **2020-02-10 at 10:30:00 a.m** and it is **not finished** yet. She **didn't earn points** and the content status is "**Incomplete**"._

_Also, **Laurie** accessed "**Welcome to our team**" video in session "**Session 01**" in "**First steps**" training and spent more **00:01:00 minute** on it. It was on **2020-02-10 at 06:00:00 p.m** and it was **finished** on **2020-02-10 at 06:01:00 p.m**. She earned **4 points** and the content status is "**Completed**"._

To check an **export sample file**, [click here](https://).

Can't you understand the differences between tracking exports? [This page](http://localhost:4000/export-glossary.html#what-is-the-difference-between-all-these-tracking-exports) can help you!


<!--
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
-->