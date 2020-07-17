---
title: Tracking - Activity
keywords: tracking, export, blendedx, activity, learning resource, content, training, session, per content, content level
last_updated: September, 2019
tags: tracking, export, blendedx, learning resource, content, activity, training, session, learner, content level, per content
summary: "The activity tracking will allow you to have detailed learner tracking information in Blendedx activities (poll, quiz, end-of-course survey, etc) and Blendedx learning resources."
sidebar: home_sidebar
permalink: activity-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is only available for <b>Blendedx trainings</b>. Only activities and learning resources in Blendedx trainings will be exported. If there is a Learning Channel with learning resources, the tracking for those Learning Channel contents will not be exported.
    <br/><br/>
    
    If you want to have tracking exports only for learning resources, please take a look at <a href="tracking-provider.html">Tracking export</a>.
    <br/><br/>

    <u>Example:</u> 
        <i><b>Laurie</b> did "<b>Welcome to our team!</b>" content in session "<b>Session 01</b>" in "<b>First steps</b>" training. It started on "<b>2020-02-20</b>" and finished on "<b>2020-03-30</b>". She earned "<b>30 points</b>" and the training status is "<b>Completed</b>".</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/><br/>

    Can't you understand the differences between tracking exports? <a href="export-glossary.html#what-is-the-difference-between-all-these-tracking-exports">This page</a> can help you!<br/>
columns: [activityDuration, activityFirstAccessDate, activityId, activityLastAccessDate, activityName, activityPoints, 
    activityType, candidateCustomFieldGuid, candidateEmail, candidateEntityId, candidateEntityName, candidateFirstname, 
    candidateGuid, candidateId, candidateLogin, candidateName, candidateRefNumber, learningObjectVersionCode, 
    learningObjectVersionTitle, learningObjectVersionPublisher, learningObjectVersionLocale, learningObjectVersionDisplayedType, 
    learningObjectVersionGuid, learningObjectVersionId, learningObjectVersionType, learningObjectId, learningObjectGuid, 
    sessionEndDate, sessionGuid, sessionId, sessionStartDate, sessionTitle, trainingChapters, trainingDuration, trainingGuid, 
    trainingId, trainingPathCode, trainingTitle, trainingPublisher, attendanceStatus, catalogVisibility, feedbackDate, 
    likes, pointsGained, progressStatus, progression, learningObjectRegistrationDate, learningObjectRegistrationGuid, learningObjectScore, scoreNPS, submissionDate, 
    contentTimeSpent, reportId, reportGuid]
parameters: [activityType, dateFormat, dateTimeFormat, entityIds, onlyFromImportedRegistrations, onlyFromImportedSessions, 
    onlyFromImportedTraining, contentPreferredLocales, learningObjectPublishersName, trainingPublishers, sessionGuid, completeSessionTitle, 
    trainingGuid, trainingPathCode, contentTimeFramesScale, contentTimeFrames, catalogVisibility, deltaMode, contentReportStatus, 
    contentTimeGlobalFormat]
---
## Activity Tracking

It is only available for **Blendedx trainings**. Only activities and learning resources in Blendedx trainings will be exported. If there is a Learning Channel with learning resources, the tracking for those Learning Channel contents will not be exported.

If you want to have tracking exports only for learning resources, please take a look at [Tracking export](htttp://localhost:4000/tracking-provider.html).

> Example: _**Laurie** did "**Welcome to our team!**" content in session "**Session 01**" in "**First steps**" training. It started on "**2020-02-20**" and finished on "**2020-03-30**". She earned "**30 points**" and the training status is "**Completed**"._

To check an **export sample file**, [click here](https://).

Can't you understand the differences between tracking exports? [This page](http://localhost:4000/export-glossary.html#what-is-the-difference-between-all-these-tracking-exports) can help you!

<!--### Example

```xml
<providers>
    <activityProvider>
        <columns>
            <candidateName label="Nom"/>
            <candidateFirstname label="Prenom"/>
            <candidateLogin label="Login"/>
            <activityID label="CodeActivite"/>
            <activityName label="TitreActivite"/>
            <constantValue label="Langue" value=""/>
            <trainingId label="IdParcours"/>
            <trainingTitle label="TitreParcours"/>
            <trainingPathCode label="CodeFormation"/>
            <activityFirstAccessDate label="PremiereConnexion"/>
            <activityLastAccessDate label="DerniereConnexion"/>
            <activityLastAccessDate label="logDate"/>
            <progressStatus label="progressStatus"/>
            <attendanceStatus label="attendanceStatus"/>
            <progression label="Progression"/>
            <score label="Score"/>
            <timeSpent label="Temps"/>							
        </columns>
        <parameters>
            <activityType>1,2,3,4,5,6,7,8,9,10</activityType>
            <reportStatus>
                <completed/>
                <incomplete/>
            </reportStatus>
            <entityIds>57</entityIds>
            <dateTimeFormat>YYYY-MM-DDThh:ii:ss</dateTimeFormat>
            <timeGlobalFormat>rawSeconds</timeGlobalFormat>	
            <timeFramesScale>less_than_n_months</timeFramesScale>
            <timeFrames>1</timeFrames>					
        </parameters>
    </activityProvider>
</providers>
```-->