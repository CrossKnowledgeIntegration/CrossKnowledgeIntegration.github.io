---
title: Create Or Update Learner Action
keywords: tracking, consolidated, import, data, createOrUpdateLearnerAction
last_updated: 08 November, 2017
tags:
summary: "Create or update a learner with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-learner-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`candidateEmail` | See columnsMapping_candidateEmail. |	actionColumn |	Yes |	
`candidateFirstname` | See columnsMapping_candidateFirstname. |	actionColumn | Yes |
`candidateLanguages` |	See columnsMapping_candidateLanguages. | actionColumn |	No |
`candidateLogin` | See columnsMapping_candidateLogin. |	actionColumn | Yes |
`candidateName`	| See columnsMapping_candidateName. | actionColumn | Yes |	
`candidateRefNumber` | See columnsMapping_candidateRefNumber. |	actionColumn | No |	
`candidateValidity`	| See columnsMapping_candidateValidity.	| actionColumn | No |	
`custom` | See columnsMapping_custom. | customColumn | No |	
`presentation` | See columns_presentation. | actionColumn | Yes |		
`entityGuid` | See columnsMapping_entityGuid. |	actionColumn | No |	
`entityName` | See columnsMapping_entityName. |	actionColumn | No |
`entityId` | See columnsMapping_entityId. |	actionColumn | No |
`ignoredColumn` | See columnsMapping_ignoredColumn. |	actionColumn | No |	
`managerLogin` | See columnsMapping_managerLogin. |	actionColumn | Yes |	
`managerRefNumber` | See columnsMapping_managerRefNumber. |	actionColumn | Yes |

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`defaultEntityId (from CKLS 14.1 onwards)` | The default value for the entity id (if empty in the given row). |	int  No	
`defaultLangCode` |	Default learner locale (if empty in the given row). | string | No	
`traineeSearchField` |	This option is used to specify the columns that will be used as filters to find the learner. | traineeSearchField | No	
`fullAccess` |	This option is used to specify whether the current import process can modify information
out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself.| yesNoElement |	No	
`enableAllLearners`	Whether or not to automatically enable all the imported learners (this option overrides the "candidateValidity" in the imported files).	| yesNoElement	| No |


### Examples

```xml 
<actions>
	<createOrUpdateConsolidatedTrackingAction>
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
	</createOrUpdateConsolidatedTrackingAction>
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