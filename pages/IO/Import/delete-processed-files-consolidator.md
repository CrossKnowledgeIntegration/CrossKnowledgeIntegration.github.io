---
title: Delete Processed Files Consolidator
keywords: consolidator, import, data, deleteProcessedFiles
last_updated: 08 November, 2017
tags:
summary: "Delete the files that were processed by the import. To be used with caution."
sidebar: home_sidebar
permalink: consolidated-tracking-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---



### Examples

```xml 
<consolidators>
	<deleteProcessedFilesConsolidator/>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`Can not delete file [...].` |	An unexpected error as occured when attempting to delete a file.