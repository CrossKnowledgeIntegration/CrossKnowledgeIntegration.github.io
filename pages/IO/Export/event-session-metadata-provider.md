---
title: Event Session Metadata
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: event-session-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`sessionTitle` | {{site.data.IO_items.col.sessionTitle.desc}}
`sessionStartDate` | {{site.data.IO_items.col.sessionStartDate.desc}}
`sessionEndDate` | {{site.data.IO_items.col.sessionEndDate.desc}}
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
`exportAllSessions` | {{site.data.IO_items.param.exportAllSessions.desc}}
`eventClassRoomTypeFilter` | {{site.data.IO_items.param.eventClassRoomTypeFilter.desc}}
`eventDurationAllDay` | {{site.data.IO_items.param.eventDurationAllDay.desc}}
`eventStatusFilter` | {{site.data.IO_items.param.eventStatusFilter.desc}}

### Examples
```xml

<providers>
    <eventSessionMetadataProvider>
        <columns>
            <sessionId/>
            <sessionGuid/>
            <sessionTitle/>
            <sessionStartDate/>
            <sessionEndDate/>
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
            <exportAllSessions>Y</exportAllSessions>
        </parameters>
    </eventSessionMetadataProvide>
</providers>

```