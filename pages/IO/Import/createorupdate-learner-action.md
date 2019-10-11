---
title: Create Or Update Learner Action
keywords: tracking, consolidated, import, data, createOrUpdateLearnerAction
last_updated: October 2019
tags:
summary: "Create or update a learner with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-learner-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [candidateName, candidateFirstname, candidateLogin, managerLogin, managerRefNumber, candidateEmail, entityGuid, 
    entityId, candidateRefNumber, custom, presentation, candidateValidity, candidateLanguages, candidateTimeZone, 
    entityName, ignoredColumn, enabledFrom, enabledUntil]
parameters: [defaultEntityId, defaultLangCode, traineeSearchField, fullAccess, enableAllLearners, disableImportFlag]
---

### Examples

```xml 
<actions>
	<createOrUpdateLearnerAction>
		<options>
			<traineeSearchField>
				<candidateRefNumber/>
			</traineeSearchField>
			<defaultEntityId>1</defaultEntityId>
			<defaultLangCode>en-GB</defaultLangCode>
		</options>
		<fields>
			<candidateRefNumber/>
			<candidateName/>
			<candidateFirstname/>
			<candidateLogin/>
			<candidateEmail/>
			<candidateValidity/>
			<custom>
				<guid>FF09BDE8-1CB4-4DDB-519C-9BC9AB6B65B2</guid>
				<mandatory>yes</mandatory>
			</custom>
			<custom>
				<guid>75ACD042-50C9-3F8E-C854-2988590BC501</guid>
				<mandatory>yes</mandatory>
			</custom>
			<entityGuid>
				<mandatory>no</mandatory>
			</entityGuid>
			<candidateLanguages>
				<mandatory>no</mandatory>
			</candidateLanguages>
			<managerLogin>
				<mandatory>no</mandatory>
			</managerLogin>
		</fields>
	</createOrUpdateLearnerAction>
</actions>
```

### Error Messages

Message | Explanation
---- | ----
`Field […] is empty.` |	A mandatory field was not filled.
`Training with guid […] is not found.` | A row from the import file has provided a training GUID that does not refer to any existing training course.
`Training with path code […] is not found.` | A row from the import file has provided a training path code that does not refer to any existing training course.
`Session with guid […] is not found for this training.` | A row from the import file has provided a session GUID that does not refer to any existing session for this training course.
`Session with title […] is not found for this training.` | A row from the import file has provided a session title that does not refer to any existing session for this training course.
`Date […] not valid.` |	A row from the import file has provided an invalid intervention date, with respect to the ISO 8601 date format.
`Teacher with login […] is not found.` | A row from the import file has provided a teacher login that does not refer to any existing teacher.
`Status has invalid value […], […] or […] expected.` | A row from the import file has provided an intervention status that is different from those defined in the intervention status field.
