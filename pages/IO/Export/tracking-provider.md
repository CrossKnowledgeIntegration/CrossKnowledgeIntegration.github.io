---
title: Tracking
keywords: tracking, completion, progression
last_updated: 21 August, 2017
tags: 
summary: "This provider generates a data report containing learning object level tracking data. The following columns for each tracking row can be included in this report."
sidebar: home_sidebar
permalink: tracking-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`reportId` | {{site.data.IO_items.col.reportId.desc}}
`reportGuid` | {{site.data.IO_items.col.reportGuid.desc}}
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`candidateTimeZone` | {{site.data.IO_items.col.candidateTimeZone.desc}}
~~`candidateGroupAncestors`~~ |  {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`candidateEntityAncestors` | {{site.data.IO_items.col.candidateEntityAncestors.desc}}
~~`candidateGroupName`~~ | {{site.data.IO_items.col.candidateGroupName.desc}}
`candidateEntityName` | {{site.data.IO_items.col.candidateEntityName.desc}}
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCod.desc}}
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`sessionTitle` | {{site.data.IO_items.col.sessionTitle.desc}}
`sessionStartDate` | {{site.data.IO_items.col.sessionStartDate.desc}}
`sessionEndDate` | {{site.data.IO_items.col.sessionEndDate.desc}}
`registrationGuid` | {{site.data.IO_items.col.registrationGuid.desc}}
`learningObjectGuid` | {{site.data.IO_items.col.learningObjectGuid.desc}}
`contentGuid` | {{site.data.IO_items.col.contentGuid.desc}}
`contentTitle` | {{site.data.IO_items.col.contentTitle.desc}}
`contentRefNumber` | {{site.data.IO_items.col.contentRefNumber.desc}}
`contentLocale` | {{site.data.IO_items.col.contentLocale.desc}}
`learningObjectPublisher` | {{site.data.IO_items.col.learningObjectPublisher.desc}}
`trainingContentFolder` | {{site.data.IO_items.col.trainingContentFolder.desc}}
`trainingContentMandatory` | {{site.data.IO_items.col.trainingContentMandatory.desc}}
`firstLaunchDate` | {{site.data.IO_items.col.firstLaunchDate.desc}}
`completionTime` | {{site.data.IO_items.col.completionTime.desc}}
`firstCompletionDate` | {{site.data.IO_items.col.firstCompletionDate.desc}}
`progression` | {{site.data.IO_items.col.progression.desc}}
`score` | {{site.data.IO_items.col.score.desc}}
`status` | {{site.data.IO_items.col.status.desc}}
`timeGlobal` | {{site.data.IO_items.col.timeGlobal.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`dateFormat` | Date format to be used in the exported data.
`dateTimeFormat` | Date time format to be used in the exported data.
~~`groupIds`~~ | <i class="fa fa-exclamation-circle preference"></i> This parameter is deprecated in the CKLS 14.1 version, please use `entityIds` instead.
`entityIds` | Only export data for the specified entities
`modality`  | Only export tracking data for a specific training modality
`onlyFromImportedRegistrations` | {{site.data.IO_items.param.onlyFromImportedRegistrations.desc}}
`onlyFromImportedSessions` | {{site.data.IO_items.param.onlyFromImportedSessions.desc}}
`onlyFromImportedTraining` | {{site.data.IO_items.param.onlyFromImportedTraining.desc}}
`preferredLocales` | Only export data where `contentLocale` matches locales specified in a comma-separated list
`publishers` | Only export tracking data for a specific content publisher
`reportStatus` | Only export tracking data for a specific completion `status`
`statusFormat` | Allows to specify custom values for completion status
`timeFrames` | Only export tracking data for a specific time span (e.g. last 7 days). Use `timeFramesScale` to specify days, months or years.
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}
[`timeFrameScaleMode`]({{site.data.IO_items.param.timeFrameScaleMode.url}}) | {{site.data.IO_items.param.timeFrameScaleMode.desc}}
[`timeGlobalFormat`]({{site.data.IO_items.param.timeGlobalFormat.url}})| Time format in which the `timeGlobal` column should be exported
`trainingGuid` | Only export tracking data for a specific training path
`trainingPathCode` | Only export tracking data for a specific `trainingPathCode`
`trainingStatus` | {{site.data.IO_items.param.trainingStatus.desc}}
`trainingPublishers` | Only export tracking data for the training courses belonging to the selected publishers (use the publisher's title, separated by commas).
`trainingStatusFormat` | {{site.data.IO_items.param.trainingStatusFormat.desc}}
`trainingModalityFormat` | "Configure what value to display for each modality value."
`sessionTitle` | Only export tracking data for a specific session
`sessionGuid` | Only export tracking data for a specific session
`withoutLaunchTime` | Whether or not to export tracking data that has no launch date
`deltamode` | Only export tracking data that was not included in the previous export
`ancestorsWithCurrent` | {{site.data.IO_items.param.ancestorsWithCurrent.desc}}
`learnersSmartGroups` | Only export the tracking for the learners belonging to the chosen smartgroups.
`catalogVisibility` | {{site.data.IO_items.param.catalogVisibility.desc}}
`templates` | Allow the creation of value template combined with other columns value ([more here](https://techwiki.crossknowledge.com/LMS/HRIS_integration/Data_Export_-_Generic_export_Column_Templating))
`onlyHrisSelectedItems` | Only export HRIS items tagged in the back-office of the CKLS.
`stripHTML` | {{site.data.IO_items.param.stripHTML.desc}}
`maxLength` | {{site.data.IO_items.param.maxLength.desc}}

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
		</columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </trackingProvider>
</providers>
```