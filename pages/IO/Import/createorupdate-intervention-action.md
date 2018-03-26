---
title: Create Or Update Intervention Action
keywords: tracking, consolidated, import, data, createOrUpdateInterventionAction
last_updated: 08 November, 2017
tags:
summary: "Create or update an intervention with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-intervention-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`interventionGuid` | See columnsMapping_interventionGuid. | actionColumn | Yes |
`trainingGuid` | See columnsMapping_trainingGuid. | actionColumn | No, but at least one of the following fields must be specified: `trainingGuid` or `trainingPathCode`|
`trainingPathCode` | See columnsMapping_trainingPathCode. | actionColumn | No, but at least one of the following fields must be specified: `trainingGuid` or `trainingPathCode` |
`sessionGuid` | See columnsMapping_trainingPathCode. | actionColumn | No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle`|
`sessionTitle` | | actionColumn | 	No, but at least one of the following fields must be specified: `sessionGuid` Or `sessionTitle` |
`interventionDate`	| See columnsMapping_interventionDate. | actionColumn |	Yes |	
`interventionDuration`|	See columnsMapping_interventionDuration. | actionColumn	| Yes |	
`roomGuid` | See columnsMapping_roomGuid. | actionColumn | Yes |	
`roomLabel` | See columnsMapping_roomLabel. | actionColumn	| Yes |	
`roomCapacity` | See columnsMapping_roomCapacity. |	actionColumn | No |	
`teacherLogin` | See columnsMapping_teacherLogin. | actionColumn | Yes |	
`interventionStatus` |	See columnsMapping_interventionStatus. | actionColumn | Yes |

### Filters and parameters


### Examples

```xml 
<actions>
	<createOrUpdateInterventionAction>
		<fields>
			<interventionGuid/>
			<trainingGuid/>
			<trainingPathCode/>
			<sessionGuid/>
			<sessionTitle/>
			<interventionDate/>
			<interventionDuration/>
			<roomGuid/>
			<roomLabel/>
			<roomCapacity/>
			<teacherLogin/>
			<interventionStatus>
				<active>A</active>
				<cancelled>C</cancelled>
			</interventionStatus>
		</fields>
	</createOrUpdateInterventionAction>
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