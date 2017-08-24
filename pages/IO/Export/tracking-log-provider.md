---
title: Tracking Log
keywords: 
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: training-log-provider.html
folder: Export
---


### Available columns

Name | Description
---|---
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateGroupAncestors` | {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`candidateGroupName` | {{site.data.IO_items.col.candidateGroupName.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`candidatePresentation` | {{site.data.IO_items.col.candidatePresentation.desc}}
`candidateTimeZone` | {{site.data.IO_items.col.candidateTimeZone.desc}}
`contentGuid` | {{site.data.IO_items.col.contentGuid.desc}}
`learningObjectGuid` | {{site.data.IO_items.col.learningObjectGuid.desc}}
`contentRefNumber` | {{site.data.IO_items.col.contentRefNumber.desc}}
`contentTitle` | {{site.data.IO_items.col.contentTitle.desc}}
`contentLocale` | {{site.data.IO_items.col.contentLocale.desc}}
`learningObjectPublisher` | {{site.data.IO_items.col.learningObjectPublisher.desc}}
`registrationGuid` | {{site.data.IO_items.col.registrationGuid.desc}}
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionTitle` | {{site.data.IO_items.col.sessionTitle.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`sessionStartDate` | {{site.data.IO_items.col.sessionStartDate.desc}}
`sessionEndDate` | {{site.data.IO_items.col.sessionEndDate.desc}}
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingContentFolder` | {{site.data.IO_items.col.trainingContentFolder.desc}}
`trainingContentMandatory` | {{site.data.IO_items.col.trainingContentMandatory.desc}}
`firstLaunchDate` | {{site.data.IO_items.col.firstLaunchDate.desc}}
`completionTime` | {{site.data.IO_items.col.completionTime.desc}}
`firstCompletionDate` | {{site.data.IO_items.col.firstCompletionDate.desc}}
`progression` | {{site.data.IO_items.col.progression.desc}}
`score` | {{site.data.IO_items.col.score.desc}}
`status` | {{site.data.IO_items.col.status.desc}}
`timeGlobal` | {{site.data.IO_items.col.timeGlobal.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}
`logDate` | {{site.data.IO_items.col.logDate.desc}}
`trainingModality` | {{site.data.IO_items.col.trainingModality.desc}}
`trainingPublisher` | {{site.data.IO_items.col.trainingPublisher.desc}}

### Filters and parameters

Name | Description
---|---
`groupIds` | {{site.data.IO_items.param.groupIds.desc}}
`entityIds` | {{site.data.IO_items.param.entityIds.desc}}
`publishers` | {{site.data.IO_items.param.publishers.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}

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