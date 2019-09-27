---
title: Event Session Metadata
keywords:
last_updated: September, 2019
tags: 
summary: "This provider exports data related to Blendedx sessions classroom events."
sidebar: home_sidebar
permalink: event-session-metadata-provider.html
folder: Export
dynamic_content: true
columns: [sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, eventTitle, eventDescription, 
    eventStartDate, eventEndDate, eventDuration, eventAllDay, eventVirtualRoomLink, eventTeacher, eventStatus, 
    eventClassRoomTitle, eventClassRoomDescription, eventClassRoomCapacity, eventClassRoomEquipments, eventClassRoomType]
parameters: [eventClassRoomTypeFilter, eventDurationAllDayFilter, eventStatusFilter, exportAllSessions, templates, 
    stripHTML, maxLength]
---

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