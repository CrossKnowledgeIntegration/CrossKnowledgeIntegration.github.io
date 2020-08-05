---
title: Event - Learner Events
keywords:
last_updated: September, 2019
tags: 
summary: "The learner event export will allow you to identify which events a learner is registered. It contains basic learner and event data."
sidebar: home_sidebar
permalink: event-learner-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx trainings that have classroom activities</b>. It is helpful when you need to know in each event a learner is registered or when you want to have a list of learners registered in an event.
    <br/><br/>

    If you want to know which events are registered in a session, please take a look at <a href="event-session-metadata-provider.html">Session Events export</a>.
    <br/><br/>	

    <u>Example:</u> 
        <i><b>John Doe</b> is registered in the <b>"Stress management"</b> event that will occur on <b>August, 20th</b> in a <b>virtual</b> classroom. This event is <b>confirmed</b> and has a capacity for <b>30 people</b>.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [candidateId, candidateGuid, candidateRefNumber, candidateName, candidateFirstname, candidateLogin, candidateEmail, 
    candidateEntityAncestors, candidateEntityId, eventTitle, eventDescription, eventStartDate, eventEndDate, eventDuration, 
    eventAllDay, eventVirtualRoomLink, eventTeacher, eventStatus, eventClassRoomTitle, eventClassRoomDescription, 
    eventClassRoomCapacity, eventClassRoomEquipments, eventClassRoomType]
parameters: [eventClassRoomTypeFilter, eventDurationAllDayFilter, eventStatusFilter, entityIds, dateFormat, 
    dateTimeFormat, templates, stripHTML, maxLength]
---

<!--### Examples
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
            <candidateEntityAncestors/>
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
```-->