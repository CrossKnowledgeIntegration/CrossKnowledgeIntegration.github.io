---
title: Event Training Metadata
keywords:
last_updated: September, 2019
tags: 
summary: "This provider exports data related to Blendedx training courses classroom events."
sidebar: home_sidebar
permalink: event-training-metadata-provider.html
folder: Export
export_content: true
columns: [trainingId, trainingPathCode, trainingTitle, trainingDescription, trainingDuration, trainingLocale, 
    catalogVisibility, trainingStatus, eventTitle, eventDescription, eventStartDate, eventEndDate, eventDuration, 
    eventAllDay, eventVirtualRoomLink, eventTeacher, eventStatus, eventClassRoomTitle, eventClassRoomDescription, 
    eventClassRoomCapacity, eventClassRoomEquipments, eventClassRoomType]
parameters: [eventClassRoomTypeFilter, eventDurationAllDayFilter, eventStatusFilter, trainingStatus, catalogVisibility, 
    trainingIds, templates, stripHTML, maxLength]
---

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