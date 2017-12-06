---
title: Delete Old Registrations Consolidator
keywords: consolidator, import, data, deleteOldSessions, Registrations
last_updated: 08 November, 2017
tags:
summary: "Delete registrations that were not part of the imported file."
sidebar: home_sidebar
permalink: consolidated-tracking-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fullAccess` | This option is used to specify whether the current import process can modify information out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself. | yesNoElement |	No


### Examples

```xml 
<consolidators>
	<deleteOldSessions>
		<fullAccess>yes</fullAccess>
	</deleteOldSessions>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
