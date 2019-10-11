---
title: Create Or Update Register Learner Action
keywords: register, learner, import, data, createOrUpdateLearnerAction
last_updated: October 2019
tags:
summary: "Register a learner to a session with respect to the data row from the import file."
sidebar: home_sidebar
permalink: registerlearner-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [candidateLogin, candidateRefNumber, candidateEmail, trainingPathCode, trainingId, sessionTitle, sessionId, 
    sessionStartDate, sessionEndDate, registrationGuid, registerFlag, ignoredColumn, registrationDate]
parameters: [traineeSearchField, trainingSearchField, sessionSearchField, dontUpdateExistingSessions, fullAccess]
---

### Examples

```xml 
<actions>
	<registerLearnerAction>
		<options>
			<traineeSearchField>
				<candidateRefNumber/>
			</traineeSearchField>
			<trainingSearchField hasResults="yes">
				<trainingPathCode/>
			</trainingSearchField>
			<sessionSearchField>
				<sessionTitle/>
				<sessionStartDate/>
			</sessionSearchField>
		</options>
		<fields>
			<candidateRefNumber/>
			<trainingPathCode/>
			<sessionTitle/>
			<sessionStartDate/>
			<sessionEndDate/>
			<registerFlag>
				<keepSession>Y</keepSession>
			</registerFlag>
			<registrationGuid/>
                        </registrationDate>
		</fields>
	</registerLearnerAction>
</actions>
```

### Error Messages

Message | Explanation
---- | ----
`Field [...] is empty.` |	A mandatory field was not filled.
`The training could not be found and it is mandatory.` |	The filters provided by a row from the import file failed to refer to any existing training course.
`Start date [...] not valid.` |	A row from the import file has provided an invalid sessionStartDate, with respect to the dateFormat defined above.
`End date [...] not valid.` |	A row from the import file has provided an invalid sessionEndDate, with respect to the dateFormat defined above.
`Register flag has invalid value [...], [...] or [...] expected.` |	A row from the import file has provided a flag that is different from those defined in the registerFlag field.
`The session can not be found and it's mandatory.` |	The filters provided by a row from the import file failed to refer to any existing session.
`No search field was provided to find the candidate.` |	All the columns containing information about the learner were empty on a specific row;or the traineeSearchField was empty.
`The candidate was not found.` |	A row from the import file has provided learner information that does not refer to any existing learner.
`The candidate was not detected as a input data, object of type [...] provided.` |	
`Cannot create a session without valid training course.` |	The filters provided by a row from the import file failed to refer to any existing training course.
`The session could not be created or retrieved from the database.` |	An unexpected error occured during the retrieval or the creation of the session.
`The learner is already registered to this training session.` |	The learner is already registered to the given training course session.
`The candidate is not registered to this training.` |	A row from the import file is attempting to unenroll a learner from a training course session, but they were not enrolled there in the first place.