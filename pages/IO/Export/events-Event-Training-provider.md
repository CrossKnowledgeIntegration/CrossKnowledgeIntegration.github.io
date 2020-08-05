---
title: Event - Training Events
keywords:
last_updated: September, 2019
tags: 
summary: "The training event export will allow you to identify some training data where the event is registered. It contains basic training and event data."
sidebar: home_sidebar
permalink: event-training-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx trainings that have classroom activities</b>. It is helpful when you need to know more training details for each event or how many events are registered in a training.
    <br/><br/>

    If you want to know which events are registered in a session, please take a look at <a href="event-session-metadata-provider.html">Session Events export</a>.
    <br/><br/>	
    If you want to know which learners are registered in an event, please take a look at <a href="event-learner-metadata-provider.html">Learner Events export</a>.
    <br/><br/>	
    
    <u>Example:</u> 
    <i>The training <b>"Improving your communication"</b> has two events registered:</i>
    <li>
        <i>
            The <b>"How to give honest feedbacks"</b> event that will occur on <b>July, 10th</b> in a <b>virtual</b> classroom. This event is <b>confirmed</b> and has a capacity for <b>100 people</b>.
        </i>
    </li>
    <li>
        <i> The <b>"How to engage your audience"</b> event that will occur on <b>October, 23th</b> in a <b>face-to-face</b> classroom. The event status is <b>confirmed</b> and the expected duration is <b>4 hours</b>.
        </i>
    </li>
    <br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
columns: [trainingId, trainingPathCode, trainingTitle, trainingDescription, trainingDuration, trainingLocale, 
    catalogVisibility, trainingStatus, eventTitle, eventDescription, eventStartDate, eventEndDate, eventDuration, 
    eventAllDay, eventVirtualRoomLink, eventTeacher, eventStatus, eventClassRoomTitle, eventClassRoomDescription, 
    eventClassRoomCapacity, eventClassRoomEquipments, eventClassRoomType]
parameters: [eventClassRoomTypeFilter, eventDurationAllDayFilter, eventStatusFilter, trainingStatus, catalogVisibility, 
    trainingIds, templates, stripHTML, maxLength]
---

<!--### Examples
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
```-->