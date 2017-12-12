---
title: Delete Empty Session Consolidator
keywords: consolidator, import, data, deleteEmptySession
last_updated: 08 November, 2017
tags:
summary: "Delete sessions which have no enrolled learners."
sidebar: home_sidebar
permalink: delete-empty-sessions-consolidator.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fullAccess` | This option is used to specify whether the current import process can modify information out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself. | yesNoElement |	No


### Examples

```xml 
<consolidators>
	<deleteEmptySessions>
		<fullAccess>yes</fullAccess>
	</deleteEmptySessions>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
