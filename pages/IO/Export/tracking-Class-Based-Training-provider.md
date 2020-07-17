---
title: Tracking - Classroom Activity
keywords: export, CBT, class, based, training, session, classroom, activity, tracking, blendedx, content, content level
last_updated: September, 2019
tags: tracking, export, blendedx, classroom, content, activity, training, session, learner, content level, per classroom, CBT, class based training
summary: "The classroom activity tracking will allow you to have detailed learner tracking information in Classroom activities and events (only available for Blendedx trainings)."
sidebar: home_sidebar
permalink: class-based-training-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is only available for <b>Blendedx trainings</b>. The classroom activity is used when the session/training will have face-to-face events or online classes with pre-defined link and limited number of people.
    <br/><br/>

    If you want to have tracking exports only for learning resources, please take a look at <a href="tracking-provider.html">Tracking export</a>. And only for Blendedx activities, please take a loot at <a href="activity-provider.html">Activity export</a>.
    <br/><br/>

    <u>Example:</u> 
        <i><b>Noah</b> attended a <b>face-to-face event</b> in <b>Paris</b> at "<b>Marseille</b>" room, that occured from "<b>2020-03-05 at 09:00:00 a.m to 06:00:00 p.m</b>" until "<b>2020-03-06 at 01:00:00 p.m to 06:00:00 p.m</b>", with <b>30 seats</b> available. <b>Noah</b> was <b>present</b> on the two days of the event, therefore he gained <b>30 points</b> on "<b>Session 02</b>", which is part of the "<b>First steps</b>" training.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/><br/>

    Can't you understand the differences between tracking exports? <a href="export-glossary.html#what-is-the-difference-between-all-these-tracking-exports">This page</a> can help you!<br/>
columns: [activityDuration, activityID, activityName, activityPoints, candidateCustomFieldGuid, candidateEmail, 
    candidateEntityName, candidateFirstname, candidateGuid, candidateId, candidateLogin, candidateName, candidateRefNumber, 
    eventAllDay, eventEndDate, eventEndTime, eventFacilitator, eventFacilitatorGuid, eventID, eventLocation, eventLocationID, 
    eventRoom, eventRoomGuid, eventStartDate, eventStartTime, eventTimeZone, eventVirtualMeetingURL, foFacilitatorName, 
    foFacilitatorFirstname, foFacilitatorEmail, pointsGained, learningObjectRegistrationDate, learningObjectRegistrationGuid, sessionEndDate, sessionGuid, sessionId, sessionStartDate, sessionTitle, classRoomStatus, contentTimeSpent, trainingChapters, trainingDuration, trainingId, trainingGuid, trainingPathCode, trainingPublisher, trainingTitle, catalogVisibility, constantValue]
parameters: [dateFormat, dateTimeFormat, entityIds, onlyFromImportedRegistrations, onlyFromImportedSessions, onlyFromImportedTraining, contentPreferredLocales, publishers, sessionGuid, trainingGuid, trainingPathCode, facilitatorGuids, foFacilitatorIds, locationIds, roomGuids, attendanceStatus, eventStarted, activityNames, contentTimeFrames, contentTimeFramesScale]
---

## Classroom Activity Tracking

It is only available for **Blendedx trainings**. The classroom activity is used when the session/training will have face-to-face events or online classes with pre-defined link and limited number of people.

If you want to have tracking exports only for learning resources, please take a look at [Tracking export](htttp://localhost:4000/tracking_export-tracking.html). And only for Blendedx activities, please take a loot at [Activity export](tracking_export-activity-tracking.html)

> Example: _**Noah** attended a **face-to-face event** in **Paris**, at "**Marseille**" room, that occured from "**2020-03-05 at 09:00:00 a.m to 06:00:00 p.m**" until "**2020-03-06 at 01:00:00 p.m to 06:00:00 p.m**", with **30 seats** available. **Noah** was **present** on the two days of the event, therefore he gained **30 points** on "**Session 02**", which is part of the "**First steps**" training._

To check an **export sample file**, [click here](https://).

Can't you understand the differences between tracking exports? [This page](http://localhost:4000/export-glossary.html#what-is-the-difference-between-all-these-tracking-exports) can help you!

<!--
### Example

```xml
		<providers>
			<instructorLedTrainingActivityProvider> 
				<columns>		
					<activityID />
					<activityDuration />
					<activityPoints />
					<eventID />
					<eventStartDate />
					<eventEndDate />
					<eventStartTime />
					<eventEndTime />
					<eventTimeZone />
					<eventAllDay />
					<eventFacilitator />
					<eventLocation />
					<eventLocationID />
					<eventVirtualMeetingURL />
					<status />
					<timeSpent />
					<pointsGained />
					<candidateId/>
					<candidateName />
					<candidateFirstname />
					<candidateLogin />
					<candidateEmail />
					<candidateRefNumber />
					<candidateGuid />
					<candidateCustomFieldGuid />
					<registrationDate />
					<registrationGuid />
					<sessionId />
					<sessionTitle />
					<sessionGuid />
					<sessionStartDate  />
					<sessionEndDate />
					<trainingId />
					<trainingTitle />
					<trainingPathCode />
					<trainingGuid />
					<catalogVisibilit  />
					<trainingStatus />
					<trainingModality />
					<trainingPublisher />
					<trainingChapters />
					<trainingDuration />					
				</columns>				
				<parameters>
					<dateTimeFormat></dateTimeFormat>
					<timeGlobalFormat>paddedhh</timeGlobalFormat>
				</parameters>
			</instructorLedTrainingActivityProvider>
		</providers>
```-->
