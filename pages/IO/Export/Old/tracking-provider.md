---
title: Tracking
keywords: tracking, completion, progression
last_updated: June, 2019
tags: 
summary: "This provider generates a data report containing learning object level tracking data. The following columns for each tracking row can be included in this report."
sidebar: home_sidebar
permalink: tracking-provider.html
folder: Export
dynamic_content: true
columns: [reportId, reportGuid, candidateId, candidateGuid, candidateName, candidateFirstname, candidateLogin, 
    candidateEmail, candidateRefNumber, candidateCustomFieldGuid, candidateTimeZone, candidateSmartgroups,
    candidateEntityAncestors, candidateEntityName, trainingId, trainingGuid, trainingTitle, 
    trainingPathCode, sessionId, sessionGuid, sessionTitle, sessionStartDate, sessionEndDate, registrationGuid, 
    learningObjectGuid, contentGuid, contentTitle, contentRefNumber, contentLocale, learningObjectPublisher, learningObjectRealCompletionTime,
    trainingContentFolder, trainingContentMandatory, firstLaunchDate, completionTime, firstCompletionDate, progression, 
    score, status, timeGlobal, constantValue, templatedValue]
parameters: [dateFormat, dateTimeFormat, entityIds, modality, onlyFromImportedRegistrations, 
    onlyFromImportedSessions, onlyFromImportedTraining, preferredLocales, publishers, reportStatus, statusFormat, 
    timeFrames, timeFramesScale, timeFrameScaleMode, timeGlobalFormat, trainingGuid, trainingPathCode, trainingStatus, 
    trainingPublishers, trainingStatusFormat, trainingModalityFormat, sessionTitle, sessionGuid, withoutLaunchTime, 
    deltaMode, ancestorsWithCurrent, learnersSmartGroups, catalogVisibility, templates, onlyHrisSelectedItems, stripHTML, 
    maxLength]
---

### Example

```xml
<providers>
    <trackingProvider>
		<columns>
			<candidateId/>
			<candidateName/>
			<candidateFirstname/>
			<candidateLogin/>
			<candidateEmail/>
			<candidateRefNumber/>
			<candidateGuid/>
			<candidateEntityName/>
			<candidateCustomFieldGuid label="Department">8345C0A3-B8AB-7F65-0638-39B0E1244AA8</candidateCustomFieldGuid>
			<trainingId/>
			<trainingTitle/>
			<trainingPathCode/>
			<trainingGuid/>
			<sessionId/>
			<sessionTitle/>
			<sessionGuid/>
			<sessionStartDate/>
			<sessionEndDate/>
			<contentGuid/>
			<contentRefNumber/>
			<contentTitle/>
			<contentLocale/>
			<firstLaunchDate/>
			<completionTime/>
			<score/>
			<timeGlobal/>
			<progression/>
			<status/>
            <templatedValue label="URL" templateId="1" />
		</columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
            <templates>
                <template id="1">https://instanceurl.ck.com/sso/content/{19}/Language/{21}</template>
            </templates>
        </parameters>
    </trackingProvider>
</providers>
```