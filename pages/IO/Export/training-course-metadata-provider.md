---
title: Training Course Metadata
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: training-course-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`title` | {{site.data.IO_items.col.title.desc}}
`description` | {{site.data.IO_items.col.description.desc}}
`modality` | {{site.data.IO_items.col.modality.desc}}
`trainingPublisher` | {{site.data.IO_items.col.trainingPublisher.desc}}
`creationDate` | {{site.data.IO_items.col.creationDate.desc}}
`pathModificationDate` | {{site.data.IO_items.col.pathModificationDate.desc}}
`modificationDate` | {{site.data.IO_items.col.modificationDate.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}


### Filters and parameters

Name | Description
---|---
`modality` | {{site.data.IO_items.param.modality.desc}}
`trainingPathCode` | {{site.data.IO_items.param.trainingPathCode.desc}}
`trainingTitle` | {{site.data.IO_items.param.trainingTitle.desc}}
`trainingGuid` | {{site.data.IO_items.param.trainingGuid.desc}}
`dateFormat` | {{site.data.IO_items.param.dateFormat.desc}}
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}

### Examples
```xml
<providers>
    <trainingCourseMetadataProvider>
        <columns>
            <modality/>
            <title/>
            <description/>
            <creationDate/>
            <pathModificationDate/>
            <modificationDate/>
            <trainingId/>
            <trainingGuid/>
            <trainingPathCode/>
            <trainingPublisher/>
            <constantValue/>
        </columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </trainingCourseMetadataProvider>
</providers>
```
