---
title: Consolidated Tracking
keywords: tracking, consolidated, import, data, createOrUpdateConsolidateTrackingAction
last_updated: October 2019
tags:
summary: "Creates or updates a consolidated tracking row with respect to the data row from the import file"
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
`lastAccessDate` | | actionColumn | No |
`progression` | | actionColumn | No |
`trackingStatus` | | actionColumn | No |
`timeSpent` | | actionColumn | Yes |
`score` | | actionColumn | No |
`scoreMax` | | actionColumn | No |
`firstCompletionDate` | | actionColumn | No | 

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`defaultScoreMax` | The default value for the maximum achievable score | int | Yes | 100


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
			<lastAccessDate/>
			<progress/>
			<timeSpent/>
			<score/>
			<scoreMax/>
			<trackingStatus/>
            <firstCompletionDate/>
		</fields>
	</createOrUpdateConsolidatedTrackingAction>
</actions>
```
