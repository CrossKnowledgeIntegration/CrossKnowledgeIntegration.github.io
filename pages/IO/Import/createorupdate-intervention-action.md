---
title: Create Or Update Intervention Action
keywords: tracking, consolidated, import, data, createOrUpdateInterventionAction
last_updated: October 2019
tags:
summary: "Create or update an intervention with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-intervention-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [interventionGuid, trainingGuid, trainingPathCode, sessionGuid, sessionTitle, interventionDate, interventionDuration, 
    roomGuid, roomLabel, roomCapacity, teacherLogin, interventionStatus, ignoredColumn]
parameters: []
---

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
			<interventionStatus/>
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