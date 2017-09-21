---
title: Training Session Metadata
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: training-session-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`modality` | {{site.data.IO_items.col.modality.desc}}
`title` | {{site.data.IO_items.col.title.desc}}
`description` | {{site.data.IO_items.col.description.desc}}
`startDate` | {{site.data.IO_items.col.startDate.desc}}
`endDate` | {{site.data.IO_items.col.endDate.desc}}
`creationDate` | {{site.data.IO_items.col.creationDate.desc}}
`pathModificationDate` | {{site.data.IO_items.col.pathModificationDate.desc}}
`modificationDate` | {{site.data.IO_items.col.modificationDate.desc}}
`registeredLearners` | {{site.data.IO_items.col.registeredLearners.desc}}
`maxNbLearners` | {{site.data.IO_items.col.maxNbLearners.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`exportAllSessions` | {{site.data.IO_items.param.exportAllSessions.desc}}
`modality` | {{site.data.IO_items.param.modality.desc}}
`trainingGuid` | {{site.data.IO_items.param.trainingGuid.desc}}
`sessionGuid` | {{site.data.IO_items.param.sessionGuid.desc}}
`trainingTitle` | {{site.data.IO_items.param.trainingTitle.desc}}
`sessionTitle` | {{site.data.IO_items.param.sessionTitle.desc}}
`trainingPathCode` | {{site.data.IO_items.param.trainingPathCode.desc}}
`trainingStatus` | {{site.data.IO_items.param.trainingStatus.desc}}
`trainingStatusFormat` | {{site.data.IO_items.param.trainingStatusFormat.desc}}
`catalogVisibility` | {{site.data.IO_items.param.catalogVisibility.desc}}
`dateFormat` | {{site.data.IO_items.param.dateFormat.desc}}
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}

### Examples
```xml
<providers>
    <trainingSessionMetadataProvider>
        <columns>
            <trainingId/>
            <trainingStatus/>
            <sessionId/>
            <sessionGuid/>
            <modality/>
            <title/>
            <description/>
            <startDate/>
            <endDate/>
            <creationDate/>
            <pathModificationDate/>
            <modificationDate/>
            <registeredLearners/>
            <maxNbLearners/>
            <constantValue/>
        </columns>
        <parameters>
            <exportAllSessions>Y</exportAllSessions>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </trainingSessionMetadataProvider>
</providers>
```