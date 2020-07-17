---
title: Tracking - Learning resource
keywords: tracking, export, blendedx, learning channel, learning resource, content, training, session, per content, content level
last_updated: June, 2019
tags: tracking, export, blendedx, learning channel, learning resource, content, training, session, learner, content level, per content
summary: "This tracking report will allow you to have detailed learner tracking information in Learning Resources (videos, interactive contents, PDF, etc)."
sidebar: home_sidebar
permalink: tracking-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Learning resources</b> in <b>Learning Channel and Blendedx trainings</b>. For Blendedx, only Learning resources will be available, it means that Blendedx specific activities will not be exported.
    <br/><br/>

    If you want to have Blendedx activities export, please take a look at <a href="activity-provider.html">Activity export</a>.
    <br/><br/>

    <u>Example:</u> 
        <i><b>Noah</b> did "<b>How to manage your time?</b>" learning resource in session "<b>Session 02</b>" in "<b>First steps</b>" training. It started on "<b>2020-01-10 at 03:15:00 p.m</b>" and it is <b>not finished</b> yet. He earned "<b>5 points</b>" and the training status is "<b>Incomplete</b>".</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/><br/>

    Can't you understand the differences between tracking exports? <a href="export-glossary.html#what-is-the-difference-between-all-these-tracking-exports">This page</a> can help you!<br/>
columns: [reportId, reportGuid, candidateId, candidateGuid, candidateName, candidateFirstname, candidateLogin, 
    candidateEmail, candidateRefNumber, candidateCustomFieldGuid, candidateTimeZone, candidateSmartgroups,
    candidateEntityAncestors, candidateEntityName, trainingId, trainingGuid, trainingTitle, 
    trainingPathCode, sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, learningObjectRegistrationGuid, 
    learningObjectGuid, contentGuid, contentTitle, contentRefNumber, contentLocale, learningObjectPublisher, learningObjectRealCompletionTime,
    trainingContentFolder, trainingContentMandatory, contentFirstLaunchDate, contentCompletionTime, contentFirstCompletionDate, learningObjectProgression, 
    learningObjectScore, learningObjectStatus, contentTimeGlobal, constantValue, templatedValue]
parameters: [dateFormat, dateTimeFormat, entityIds, modality, onlyFromImportedRegistrations, 
    onlyFromImportedSessions, onlyFromImportedTraining, contentPreferredLocales, publishers, contentReportStatus, statusFormat, 
    contentTimeFrames, contentTimeFramesScale, contentTimeFrameScaleMode, contentTimeGlobalFormat, trainingGuid, trainingPathCode, trainingStatus, 
    trainingPublishers, trainingStatusFormat, trainingModalityFormat, completeSessionTitle, sessionGuid, withoutLaunchTime, 
    deltaMode, ancestorsWithCurrent, learnersSmartGroups, catalogVisibility, templates, onlyHrisSelectedItems, stripHTML, 
    maxLength]
---

## Tracking

It is available for **Learning resources** in **Learning Channel and Blendedx trainings**. For Blendedx, only Learning resources will be available, it means that Blendedx specific activities will not be exported.

If you want to have Blendedx activities export, please take a look at [this site](htttp://localhost:4000/activity-provider.html).

> Example: _**Noah** did "**How to manage your time?**" learning resource in session "**Session 02**" in "**First steps**" training. It started on "**2020-01-10 at 03:15:00 p.m**" and it is **not finished** yet. He earned "**5 points**" and the training status is "**Incomplete**"._

To check an **export sample file**, [click here](https://).

Can't you understand the differences between tracking exports? [This page](http://localhost:4000/export-glossary.html#what-is-the-difference-between-all-these-tracking-exports) can help you!

<!--
### Example

```xml
<providers>
    <trackingProvider>
		<columns>
			<candidateId/>
			<candidateName/>
			<candidateFirstname/>
			<candidateLogin/>
			<candidateEmail/>
			<candidateRefNumber/>
			<candidateGuid/>
			<candidateEntityName/>
			<candidateCustomFieldGuid label="Department">8345C0A3-B8AB-7F65-0638-39B0E1244AA8</candidateCustomFieldGuid>
			<trainingId/>
			<trainingTitle/>
			<trainingPathCode/>
			<trainingGuid/>
			<sessionId/>
			<sessionTitle/>
			<sessionGuid/>
			<sessionStartDate/>
			<sessionEndDate/>
			<contentGuid/>
			<contentRefNumber/>
			<contentTitle/>
			<contentLocale/>
			<firstLaunchDate/>
			<completionTime/>
			<score/>
			<timeGlobal/>
			<progression/>
			<status/>
            <templatedValue label="URL" templateId="1" />
		</columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
            <templates>
                <template id="1">https://instanceurl.ck.com/sso/content/{19}/Language/{21}</template>
            </templates>
        </parameters>
    </trackingProvider>
</providers>
```
-->