---
title: Time Stamped File Error Logger Consolidator
keywords: consolidator, import, data, timeStampedFileErrorLogger
last_updated: 08 November, 2017
tags:
summary: "Log the import errors to a timestamped log file in the specified folder."
sidebar: home_sidebar
permalink: timestamped-file-error-logger-consolidator.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`location` | Path to the folder that will contain the log files. The base path is the data folder of the instance.|	string | Yes	
`disabled` | Whether or not this consolidator is disabled.|	string | No | No


### Examples

```xml 
<consolidators>
	<timeStampedFileErrorLogger>
		<location>imports/logs</location>
	</timeStampedFileErrorLogger>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`The location parameter is missing.` | The location parameter is empty.
`The [...] directory can not be found nor created.` | The specified location folder does not exist and an unexpected error occured during its creation. This is probably a folder rights problem.
`Could not open the file [...] for writing.` | An unexpected error occured while trying to open a log file inside the location folder. This is probably a folder rights problem.