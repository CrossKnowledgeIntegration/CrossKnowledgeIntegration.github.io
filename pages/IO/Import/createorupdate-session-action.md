---
title: Create Or Update Session Action
keywords: session, import, data, createOrUpdateSessionAction
last_updated: 08 November, 2017
tags:
summary: "Create or update a session with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-session-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`sessionAction` | See columnsMapping_sessionAction. | actionColumn | Yes	
`sessionStatus` | See columnsMapping_sessionStatus. | actionColumn | No	
`sessionGuid` |	See columnsMapping_sessionGuid. | actionColumn | No	
`sessionStartDate` | See columnsMapping_sessionStartDate. |	actionColumn | No	
`sessionEndDate` | See columnsMapping_sessionEndDate. |	actionColumn | No | Set NULL to recet it
`sessionTitle` | See columnsMapping_sessionTitle. |	actionColumn | Yes	
`sessionId` | See columnsMapping_sessionId.  | actionColumn | Yes	
`teacherLogin` | See columnsMapping_teacherLogin. |	actionColumn | Yes	
`trainingPathCode` | See columnsMapping_trainingPathCode. |	actionColumn | Yes	
`trainingId` | See columnsMapping_trainingId. |	actionColumn | Yes	
`trainingTitle` | See columnsMapping_trainingTitle. | actionColumn | Yes	

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`sessionSearchField` |	This option is used to specify the columns that will be used as filters to find the learner. | sessionSearchField |	Yes	
`fullAccess` | This option is used to specify whether the current import process can modify information
out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself. | yesNoElement | No


### Examples

```xml 
<actions>
	<createOrUpdateSessionAction>
		<options>
			<sessionSearchField>
				<sessionTitle/>
			</sessionSearchField>
			<fullAccess>yes</fullAccess>
		</options>
		<fields>
			<sessionAction/>
			<trainingPathCode/>
			<trainingTitle/>
			<sessionTitle/>
			<sessionStatus/>
			<sessionGuid>
				<mandatory>no</mandatory>
			</sessionGuid>
			<sessionStartDate/>
			<sessionEndDate/>
			<teacherLogin>
				<mandatory>no</mandatory>
			</teacherLogin>
		</fields>
	</createOrUpdateSessionAction>
</actions>
```

### Error Messages

Message | Explanation
---- | ----
`Field [...] is empty.` | A mandatory field was not filled.
`Training with training path code [...] is not found.` | A row from the import file has provided a training path code that does not refer to any existing training course.
`Field trainingPathCode is empty.` | A row from the import file has provided an empty trainingPathCode.
`Group with name [...] is duplicated.` | A row from the import file has provided a group name that does not refer to a duplicated group. Please consider using the GUID to identify the group.
`Invalid sessionAction value: [...]` | A row from the import file has provided a value that is different from the allowed values in the sessionAction field.