---
title: Consolidated Tracking
keywords: tracking, consolidated, import, data, createOrUpdateConsolidateTrackingAction, migration
last_updated: 03 September, 2018
tags:
summary: "Creates or updates a consolidated tracking row represented by the data row from the import file.\r\n Consolidated Tracking stands for a unique row that summarizes the history of a Learner accessing a Learning Resource inside a Training Session from a Training Course."
sidebar: home_sidebar
permalink: consolidated-tracking-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`candidateLogin` |  | actionColumn | No, but at least one of the fields candidateLogin, candidateRefNumber and candidateEmail must be specified |
`candidateRef Number` | | actionColumn | No, but at least one of the fields candidateLogin, candidateRefNumber and candidateEmail must be specified |
`candidateEmail` | | actionColumn | No, but at least one of the fields candidateLogin, candidateRefNumber and candidateEmail must be specified |
`lovCode` | | actionColumn | No, but at least one of the fields lovCode and lovGuid must be specified |
`lovGuid` | | actionColumn | No, but at least one of the fields lovCode and lovGuid must be specified |
`sessionGuid` | | actionColumn | No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle` or `sessionId` AND `trainingPathCode` or `trainingId` |
`sessionTitle` | | actionColumn | 	No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle` or `sessionId` AND `trainingPathCode` or `trainingId` |
`sessionId` | | actionColumn | No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle` or `sessionId` AND `trainingPathCode` or `trainingId` |
`trainingPathCode` | | actionColumn | No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle` or `sessionId` AND `trainingPathCode` or `trainingId` |
`trainingId` | | actionColumn | No, but at least one of the following fields must be specified:`sessionGuid` Or `sessionTitle` or `sessionId` AND `trainingPathCode` or `trainingId` |
`firstAccessDate` | | actionColumn | No, but the first provided date and time will have it's value reflected here if unset. DateTime values required, or Date completed by defaultTime paramenter | 
`firstCompletionDate` | | actionColumn | No, but it is required for trackingStatus=Completed. DateTime values required, or Date completed by defaultTime paramenter | 
`lastAccessDate` | | actionColumn | No, but the lsst provided date and time will have it's value reflected here if unset. DateTime values required, or Date completed by defaultTime paramenter |
`progression` | | actionColumn | No. Accepted values [0-100] |
`trackingStatus` | | actionColumn | No |
`timeSpent` | | actionColumn | Yes. The provided data must be of integer type and the value must be provided in seconds. E.G.: 60 means one minute | 0
`score` | | actionColumn | No. The provided data must be of integer type. |
`scoreMax` | | actionColumn | No. The provided data must be of integer type. |


### Options

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`defaultScoreMax` | The default value for the maximum achievable score | int | Yes | 100


### Parameters

Parameter | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`defaultTimezone` | The default value for the timezone referenced by the tracking data provided | string | No | UTC
`defaultTime` | The default value for time while importing dates without time from the tracking data provided | string | No | 00:00:00
`dateTimeFormat` | The default value for the datetime values provided by the tracking data provided | string | Yes | YYYY-MM-DD hh:ii:ss


### Error Messages

Message | Explanation
---- | ----
`At least one of these element must be present: learning object version code or GUID.` | A tracking row needs to be associated to a learning object, therefore a reference (lovCode or lovGuid) has to be filled in the import file.
`This learning object is provided by CrossKnowledge, and this report cannot be updated.` | Reports for CrossKnowledge learning objects cannot be modified by the import process.
`This learning object is an EasyQuizz, and this report cannot be updated.`	| Reports for Easyquizz learning objects cannot be modified by the import process.
`At least one of these element must be present: learner login, reference number or email.` | A tracking needs to be associated to a learner, therefore a learner reference (candidateLogin, candidateRefNumber or candidateEmail) has to be filled in the import file.
`At least one of the following to provide a precise context : "session GUID" or the couple "session title" & "training code".'`	| A tracking needs to be associated to a context, therefore a context reference (sessionGuid, or sessionTitle and trainingPathCode) is required.
`No registration found for given parameters.` | Given the learner and session information from the import file, the application failed to identify a registration.
`You cannot set a first completion date if the LO is not completed.` | If during an import, the tracking row is "not completed" and firstCompletionDate is specified, then the row is rejected with the message: "You cannot set a first completion date if the LO is not completed".
`You cannot set a firstCompletionDate previous than firstAccessDate` | If during an import, the tracking row has firstCompletionDate set, that value must equal or after firstAccessDate.
`You cannot set a firstCompletionDate after than lastAccessDate` | If during an import, the tracking row has firstCompletionDate set, that value must equal or before lastAccessDate.
`You cannot set values to firstAccessDate, lastAccessDate and status completed if there isn't the firstCompletionDate value` | If during an import, the tracking row has no firstCompletionDate set but it has firstAccessDate and lastAccessDate, it cannot identify which value to use to the firstCompletionDate. Thi value must be specified in the provided data.
`You cannot set a lastAccessDate previous than firstAccessDate` | If during an import, the tracking row must have lastAccessDate after firstAccessDate.
`You cannot set a firstCompletionDate after than lastAccessDate` | If during an import, the tracking row must have lastAccessDate after firstCompletionDate.
`You cannot set a firstCompletionDate after than now` | If during an import, the firstCompletionDate must not be in the future.
`You cannot set a lastAccessDate after than now` | If during an import, the lastAccessDate must not be in the future.
`Your dateTime information mismatches preset dateTimeFormat` | If during an import, the provided datetime information mismatches the preset valid scope of datetime values.


### Examples

```xml 
<actions>
	<createOrUpdateConsolidatedTrackingAction>
		<options>
			<defaultScoreMax>100</defaultScoreMax>
		</options>
		<fields>
			<candidateLogin/>
			<candidateRefNumber/>
			<candidateEmail/>
			<lovCode/>
			<lovGuid/>
			<sessionTitle/>
			<sessionGuid/>
			<trainingPathCode/>
			<firstAccessDate/>
			<firstCompletionDate/>
			<lastAccessDate/>
			<progress/>
			<timeSpent/>
			<score/>
			<scoreMax/>
			<trackingStatus/>
		</fields>
		<parameters>
			<dateTimeFormat>YYYY-MM-DD HH:II:SS</dateTimeFormat>
			<defaultTime>11:00:00</defaultTime>
			<timeZone>America/Sao_Paulo</timeZone>
		</parameters>
	</createOrUpdateConsolidatedTrackingAction>
</actions>
```
