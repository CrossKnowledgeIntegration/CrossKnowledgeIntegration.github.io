---
title: Clean Folder Consolidator
keywords:  consolidated, import, data, cleanFolder
last_updated: 08 November, 2017
tags:
summary: "Clean the data in the specified folder, as well as log files (in DATA_PATH/imports/logs) if needed. It is possible to specify a number of days beyond which the data is considered obsolete and thus will be removed."
sidebar: home_sidebar
permalink: clean-folder-consolidator.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`dataFolderPath` | Path to the folder containing the data to be cleaned. The base path is DATA_PATH (the data folder of the instance). | string | No	
`cleanLogs` | Whether or not to clean the log folder, which is DATA_PATH/imports/logs |	yesNoElement | No | No
`cleanOlderThan` | If specified, only clean data that is older than the number of days given in this option. | int | No | 30



### Examples

```xml 
<consolidators>
	<cleanFolder>
		<dataFolderPath>imports/data</dataFolderPath>
		<cleanLogs>yes</cleanLogs>
		<cleanOlderThan>14</cleanOlderThan>
	</cleanFolder>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`Folder : [...] doesn't exist or isn't a directory.` | The folder specified in dataFolderPath is not a folder or does not exist.