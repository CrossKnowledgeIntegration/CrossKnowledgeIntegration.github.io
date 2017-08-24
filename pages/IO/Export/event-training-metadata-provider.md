---
title: Event Training Metadata
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: event-training-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingDescription` | {{site.data.IO_items.col.trainingDescription.desc}}
`trainingDuration` | {{site.data.IO_items.col.trainingDuration.desc}}
`trainingLocale` | {{site.data.IO_items.col.trainingLocale.desc}}
`catalogVisibility` | {{site.data.IO_items.col.catalogVisibility.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`eventTitle` | {{site.data.IO_items.col.eventTitle.desc}}
`eventDescription` | {{site.data.IO_items.col.eventDescription.desc}}
`eventStartDate` | {{site.data.IO_items.col.eventStartDate.desc}}
`eventEndDate` | {{site.data.IO_items.col.eventEndDate.desc}}
`eventDuration` | {{site.data.IO_items.col.eventDuration.desc}}
`eventAllDay` | {{site.data.IO_items.col.eventAllDay.desc}}
`eventVirtualRoomLink` | {{site.data.IO_items.col.eventVirtualRoomLink.desc}}
`eventTeacher` | {{site.data.IO_items.col.eventTeacher.desc}}
`eventStatus` | {{site.data.IO_items.col.eventStatus.desc}}
`eventClassRoomTitle` | {{site.data.IO_items.col.eventClassRoomTitle.desc}}
`eventClassRoomDescription` | {{site.data.IO_items.col.eventClassRoomDescription.desc}}
`eventClassRoomCapacity` | {{site.data.IO_items.col.eventClassRoomCapacity.desc}}
`eventClassRoomEquipments` | {{site.data.IO_items.col.eventClassRoomEquipments.desc}}
`eventClassRoomType` | {{site.data.IO_items.col.eventClassRoomType.desc}}


### Filters and parameters

Name | Description
---|---
`eventClassRoomTypeFilter` | {{site.data.IO_items.param.eventClassRoomTypeFilter.desc}}
`eventDurationAllDay` | {{site.data.IO_items.param.eventDurationAllDay.desc}}
`eventStatusFilter` | {{site.data.IO_items.param.eventStatusFilter.desc}}
`trainingStatus` | {{site.data.IO_items.param.trainingStatus.desc}}
`catalogVisibility` | {{site.data.IO_items.param.catalogVisibility.desc}}
`trainingIds` | {{site.data.IO_items.param.trainingIds.desc}}

### Examples
```xml
<providers>
    <eventTrainingMetadataProvider>
        <columns>
            <trainingId/>
            <trainingPathCode/>
            <trainingTitle/>
            <trainingDescription/>
            <trainingDuration/>
            <trainingLocale/>
            <catalogVisibility/>
            <trainingStatus/>
            <eventTitle/>
            <eventDescription/>
            <eventStartDate/>
            <eventEndDate/>
            <eventDuration/>
            <eventAllDay/>
            <eventVirtualRoomLink/>
            <eventTeacher/>
            <eventStatus/>
            <eventClassRoomTitle/>
            <eventClassRoomDescription/>
            <eventClassRoomCapacity/>
            <eventClassRoomEquipments/>
            <eventClassRoomType/>
        </columns>
        <parameters>
            <trainingStatus>P</trainingStatus>
        </parameters>
    </eventTrainingMetadataProvider>
</providers>
```