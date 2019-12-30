---
title: Create or Update Consolidated Tracking
keywords: tracking, consolidated, import, data, createOrUpdateConsolidateTrackingAction
last_updated: October 2019
tags:
summary: "Import or update of tracking done by a learner on a learning resource. Consolidated tracking stands for a unique row that summarizes the history of a learner accessing a learning resource inside a training session from a training course."
sidebar: home_sidebar
permalink: createorupdate-consolidated-tracking-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
important_note: >
    Unlike the other import providers, the settings for this provider need to be split in two blocks: <code class="highlighter-rouge">options</code> and <code class="highlighter-rouge">parameters</code>. 
    Please see the example below for more details.
columns: [candidateLogin, candidateRefNumber, candidateEmail, lovCode, lovGuid, sessionGuid, trainingPathCode, trainingId, 
    sessionTitle, sessionId, firstAccessDate, lastAccessDate, firstCompletionDate, progression, trackingStatus, timeSpent, 
    score, scoreMax, ignoredColumn]
parameters: [defaultScoreMax, dateTimeFormat, timeZone, defaultTime]
---

### Examples

```xml 
<actions>
	<createOrUpdateConsolidatedTrackingAction>
		<options>
			<defaultScoreMax>100</defaultScoreMax>
		</options>
		<fields>
			<candidateEmail/>
			<candidateLogin/>
			<candidateRefNumber/>
			<firstAccessDate/>
			<firstCompletionDate/>
			<lastAccessDate/>
			<lovCode/> <!-- use Code or Guid -->
			<lovGuid/>
			<progression/>
			<score/>
			<scoreMax/>
			<sessionTitle/><!-- Use Title, Guid, Or Id -->
			<sessionGuid/>
			<sessionId/>
			<timeSpent/>
			<trackingStatus/>
			<trainingPathCode/><!-- Use PathCode or Id -->
			<trainingId/>
		</fields>
        <parameters>
            <timeZone>America/Sao_Paulo</timeZone>
            <dateTimeFormat>YYYY-MM-DD HH:II:SS</dateTimeFormat>
            <defaultTime>00:00:00</defaultTime>
        </parameters>
	</createOrUpdateConsolidatedTrackingAction>
</actions>
```

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
