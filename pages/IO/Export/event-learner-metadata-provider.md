---
title: Event Learner Metadata
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: event-learner-metadata-provider.html
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
`candidateEntityId` | {{site.data.IO_items.col.candidateEntityId.desc}}
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
`entityIds` | {{site.data.IO_items.param.entityIds.desc}}

### Examples
```xml
<providers>
    <eventLearnerMetadataProvider>
        <columns>
            <candidateId/>
            <candidateGuid/>
            <candidateRefNumber/>
            <candidateName/>
            <candidateFirstname/>
            <candidateLogin/>
            <candidateEmail/>
            <candidateGroupAncestors/>
            <candidateEntityId/>
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
            <eventDurationAllDay>Y</eventDurationAllDay>
        </parameters>
    </eventLearnerMetadataProvider>
</providers>
```