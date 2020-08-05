---
title: Event - Session Events
keywords:
last_updated: September, 2019
tags: 
summary: "The session event export will allow you to identify which events are registered in a session. It contains basic session and event data."
sidebar: home_sidebar
permalink: event-session-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx trainings that have classroom activities</b>. It is helpful when you need to know for each session what events are available and when they will occur.
    <br/><br/>

    If you want to know which events are registered in a training, please take a look at <a href="event-training-metadata-provider.html">Training Events export</a>.
    <br/><br/>	
    If you want to know which learners are registered in an event, please take a look at <a href="event-learner-metadata-provider.html">Learner Events export</a>.
    <br/><br/>	
    
    <u>Example:</u> 
    <i>The session <b>"Live Events"</b> has two events registered:</i>
    <li>
        <i>
            The <b>"Stress management"</b> event that will occur on <b>August, 20th</b> in a <b>virtual</b> classroom. This event is <b>confirmed</b> and has a capacity for <b>30 people</b>.
        </i>
    </li>
    <li>
        <i> The <b>"Time management"</b> event that will occur on <b>September, 02nd</b> in a <b>face-to-face</b> classroom. The event status is <b>Pending</b> and the expected duration is <b>6 hours</b>.
        </i>
    </li>
    <br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, eventTitle, eventDescription, 
    eventStartDate, eventEndDate, eventDuration, eventAllDay, eventVirtualRoomLink, eventTeacher, eventStatus, 
    eventClassRoomTitle, eventClassRoomDescription, eventClassRoomCapacity, eventClassRoomEquipments, eventClassRoomType]
parameters: [eventClassRoomTypeFilter, eventDurationAllDayFilter, eventStatusFilter, exportAllSessions, templates, 
    stripHTML, maxLength]
---

<!--### Examples
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

```-->