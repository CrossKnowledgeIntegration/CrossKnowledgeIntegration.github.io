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
			<candidateRefNumber/><!-- Use at least the candidate RefNumber, Login, Email -->
			<candidateLogin/>
			<candidateEmail/>
			<candidateName/>
			<candidateFirstname/>
			<candidateValidity/>
			<candidateTimeZone/>
			<enabledFrom/>
			<enabledUntil/>
			<entityGuid/>
			<entityId/>
			<entityName/>
			<candidateLanguages/>
			<presentation/>
			<managerLogin/><!-- Manager Login or Refnumber enables My Team -->
			<managerRefNumber/>
			<custom> <!--custom example format -->
				<guid>FF09BDE8-1CB4-4DDB-519C-9BC9AB6B65B2</guid>
				<mandatory>yes</mandatory>
			</custom>
			<custom>
				<guid>75ACD042-50C9-3F8E-C854-2988590BC501</guid>
				<mandatory>yes</mandatory>
			</custom>
		</fields>
	</createOrUpdateLearnerAction>
</actions>
```

### Error Messages

Message | Error level | Explanation
---- | ----
`Field […] is empty.` |	ERROR | A mandatory field was not filled.
`The "validity" field value […] is not allowed.` | ERROR | A row from the import file has provided an invalid "candidateValidity" value.
`The login: […] already exists. The user name will be: […]` | WARNING | A row from the import file tries to update a learner and assign them a login already taken.
`Date format is not valid` | ERROR | Custom date format option "dateFormat" is invalid or could not be parsed.
`enabledUntil is inferior to enabledFrom or vice versa` | ERROR | Attempting to assign a row where the field "enabled from" is set after the field "enabled to".
