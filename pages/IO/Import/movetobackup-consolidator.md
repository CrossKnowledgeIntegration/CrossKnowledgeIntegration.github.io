---
title: Move to Back Up Consolidator
keywords: consolidator, import, data, moveToBackupConsolidator
last_updated: 08 November, 2017
tags:
summary: "Move the processed import file to a specified backup folder."
sidebar: home_sidebar
permalink: consolidated-tracking-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`backupFolder` | Path to the backup folder. The base path is the data folder of the instance DATA path. | string | Yes |	DATA_PATH/imports/backup/
`timestamp` | Whether to prepend the timestamp to the import file when moving it to the backup folder. | yesNoElement |	Yes | No
`disabled` | Whether this consolidator is disabled or not. | string | No | No


### Examples

```xml 
<consolidators>
	<moveToBackupConsolidator>
		<backupFolder>imports/test/backup/</backupFolder>
		<timestamp>yes</timestamp>
	</moveToBackupConsolidator>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`The backup folder [...] does not exists or can not be created.` | The specified backupFolder does not exist and an unexpected error occured during its creation. This is probably a folder rights problem.
`Can not copy the file [...] to [...]` | An unexpected error occured while trying to copy the import file to the backup folder. This is probably a folder rights problem.
`Can not delete the file [...]` | After successfully copying the import file, the process will attempt to delete the original file, but an unexpected error occured while trying to delete it. This is probably a folder/file rights problem.