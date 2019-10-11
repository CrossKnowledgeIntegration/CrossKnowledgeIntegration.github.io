---
title: Create Or Update Session Action
keywords: session, import, data, createOrUpdateSessionAction
last_updated: October 2019
tags:
summary: "Create or update a session with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-session-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [sessionAction, trainingPathCode, trainingTitle, sessionTitle, trainingId, sessionId, sessionGuid, 
    sessionStartDate, sessionEndDate, teacherLogin, ignoredColumn]
parameters: [sessionSearchField, fullAccess]
---

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