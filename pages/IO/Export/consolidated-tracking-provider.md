---
title: Consolidated Tracking
keywords: 
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: consolidated-tracking-provider.html
folder: Export
---


### Available columns

Name | Description
---|---
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`candidateGroupAncestors` | {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`candidateEntityAncestors` | {{site.data.IO_items.col.candidateEntityAncestors.desc}}
`candidateGroupName` | {{site.data.IO_items.col.candidateGroupName.desc}}
`candidateEntityName` | {{site.data.IO_items.col.candidateEntityName.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`lastPlatformAccessDate` | {{site.data.IO_items.col.lastPlatformAccessDate.desc}}
`nbLO` | {{site.data.IO_items.col.nbLO.desc}}
`nbLOStarted` | {{site.data.IO_items.col.nbLOStarted.desc}}
`nbLOFinished` | {{site.data.IO_items.col.nbLOFinished.desc}}
`registrationDate` | {{site.data.IO_items.col.registrationDate.desc}}
`registrationGuid` | {{site.data.IO_items.col.registrationGuid.desc}}
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionTitle` | {{site.data.IO_items.col.sessionTitle.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`sessionStartDate` | {{site.data.IO_items.col.sessionStartDate.desc}}
`sessionEndDate` | {{site.data.IO_items.col.sessionEndDate.desc}}
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`catalogVisibility` | {{site.data.IO_items.col.catalogVisibility.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`trainingModality` | {{site.data.IO_items.col.trainingModality.desc}}
`trainingPublisher` | {{site.data.IO_items.col.trainingPublisher.desc}}
`trainingChapters` | {{site.data.IO_items.col.trainingChapters.desc}}
`trainingDuration` | {{site.data.IO_items.col.trainingDuration.desc}}
`completionTime` | {{site.data.IO_items.col.completionTime.desc}}
`firstLaunchDate` | {{site.data.IO_items.col.firstLaunchDate.desc}}
`progression` | {{site.data.IO_items.col.progression.desc}}
`progressionMandatory` | {{site.data.IO_items.col.progressionMandatory.desc}}
`score` | {{site.data.IO_items.col.score.desc}}
`status` | {{site.data.IO_items.col.status.desc}}
`thresholdReachedDate` | {{site.data.IO_items.col.thresholdReachedDate.desc}}
`firstCompletionDate` | {{site.data.IO_items.col.firstCompletionDate.desc}}
`timeGlobal` | {{site.data.IO_items.col.timeGlobal.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}


### Filters and parameters

Name | Description
---|---
`ancestorsWithCurrent` | {{site.data.IO_items.param.ancestorsWithCurrent.desc}}
`catalogVisibility` | {{site.data.IO_items.param.catalogVisibility.desc}}
`dateFormat` | {{site.data.IO_items.param.dateFormat.desc}}
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`deltaMode` | {{site.data.IO_items.param.deltaMode.desc}}
`groupIds` | {{site.data.IO_items.param.groupIds.desc}}
`entityIds` | {{site.data.IO_items.param.entityIds.desc}}
`modality` | {{site.data.IO_items.param.modality.desc}}
`onlyFromImportedRegistrations` | {{site.data.IO_items.param.onlyFromImportedRegistrations.desc}}
`onlyFromImportedSessions` | {{site.data.IO_items.param.onlyFromImportedSessions.desc}}
`reportStatus` | {{site.data.IO_items.param.reportStatus.desc}}
`sessionGuid` | {{site.data.IO_items.param.sessionGuid.desc}}
`sessionTitle` | {{site.data.IO_items.param.sessionTitle.desc}}
`statusFormat` | {{site.data.IO_items.param.statusFormat.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}
`timeFramesScaleMode` | {{site.data.IO_items.param.timeFramesMode.desc}}
`timeGlobalFormat` | {{site.data.IO_items.param.timeGlobalFormat.desc}}
`trainingGuid` | {{site.data.IO_items.param.trainingGuid.desc}}
`trainingPathCode` | {{site.data.IO_items.param.trainingPathCode.desc}}
`trainingStatus` | {{site.data.IO_items.param.trainingStatus.desc}}
`trainingStatusFormat` | {{site.data.IO_items.param.trainingStatusFormat.desc}}
`preferredLocales` | {{site.data.IO_items.param.preferredLocales.desc}}



### Examples
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
            <candidateGroupAncestors/>
            <candidateEntityAncestors/>
            <candidateGroupName/>
            <candidateEntityName/>
            <candidateCustomFieldGuid/>
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
