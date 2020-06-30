---
title: Class Based Training
keywords: export, CBT, class, based, training
last_updated: September, 2019
tags: 
summary: "This provider exports instructor-lead training data from the BlendedX."
sidebar: home_sidebar
permalink: class-based-training-provider.html
folder: Export
dynamic_content: true
columns: [activityDuration, activityID, activityName, activityPoints, candidateCustomFieldGuid, candidateEmail, 
    candidateEntityName, candidateFirstname, candidateGuid, candidateId, candidateLogin, candidateName, candidateRefNumber, 
    eventAllDay, eventEndDate, eventEndTime, eventFacilitator, eventFacilitatorGuid, eventID, eventLocation, eventLocationID, 
    eventRoom, eventRoomGuid, eventStartDate, eventStartTime, eventTimeZone, eventVirtualMeetingURL, foFacilitatorName, 
    foFacilitatorFirstname, foFacilitatorEmail, pointsGained, registrationDate, registrationGuid, sessionEndDate, sessionGuid, 
    sessionId, sessionStartDate, sessionTitle, status, timeSpent, trainingChapters, trainingDuration, trainingId, trainingGuid, 
    trainingPathCode, trainingPublisher, trainingTitle, catalogVisibility, constantValue]
parameters: [dateFormat, dateTimeFormat, entityIds, onlyFromImportedRegistrations, onlyFromImportedSessions, 
    onlyFromImportedTraining, preferredLocales, publishers, sessionGuid, trainingGuid, trainingPathCode, facilitatorGuids, 
    foFacilitatorIds, locationIds, roomGuids, attendanceStatus, eventStarted, activityNames, timeFrames, timeFramesScale]
---

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
```
