---
title: Activity
keywords: activity, completion, progression
last_updated: September, 2019
tags: 
summary: "This provider generates a data report containing tracking on Blendedx activities. The following columns for each tracking row can be included in this report."
sidebar: home_sidebar
permalink: activity-provider.html
folder: Export
dynamic_content: true
columns: [activityDuration, activityFirstAccessDate, activityId, activityLastAccessDate, activityName, activityPoints, 
    activityType, candidateCustomFieldGuid, candidateEmail, candidateEntityId, candidateEntityName, candidateFirstname, 
    candidateGuid, candidateId, candidateLogin, candidateName, candidateRefNumber, learningObjectVersionCode, 
    learningObjectVersionTitle, learningObjectVersionPublisher, learningObjectVersionLocale, learningObjectVersionDisplayedType, 
    learningObjectVersionGuid, learningObjectVersionId, learningObjectVersionType, learningObjectId, learningObjectGuid, 
    sessionEndDate, sessionGuid, sessionId, sessionStartDate, sessionTitle, trainingChapters, trainingDuration, trainingGuid, 
    trainingId, trainingPathCode, trainingTitle, trainingPublisher, attendanceStatus, catalogVisibility, feedbackDate, 
    likes, pointsGained, progressStatus, progression, registrationDate, registrationGuid, score, scoreNPS, submissionDate, 
    timeSpent, reportId, reportGuid]
parameters: [activityType, dateFormat, dateTimeFormat, entityIds, onlyFromImportedRegistrations, onlyFromImportedSessions, 
    onlyFromImportedTraining, preferredLocales, learningObjectPublishersName, trainingPublishers, sessionGuid, sessionTitle, 
    trainingGuid, trainingPathCode, timeFramesScale, timeFrames, catalogVisibility, deltaMode, reportStatus, 
    timeGlobalFormat]
---

### Example

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
```