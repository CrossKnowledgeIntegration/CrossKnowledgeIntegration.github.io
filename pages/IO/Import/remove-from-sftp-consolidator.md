---
title: Remove From SFTP Consolidator
keywords: consolidator, import, data, deleteProcessedFiles
last_updated: 08 November, 2017
tags:
summary: "Remove the import file from the distant machine it was imported from via SftpFileImportAction."
sidebar: home_sidebar
permalink: remove-from-sftp-consolidator.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`sftpHost` | Address of the sFTP server. | string | Yes	
`sftpLogin`	| Login to be used for the sFTP connection. | string | Yes	
`sftpPassword` | Password to be used for the sFTP connection. |	string | Yes	
`sftpFolder` | Path to the folder to fetch the file from. The path begins at the root folder of the supplied sFTP user. The parameter must begin with a '/'. |
string | Yes |	The root folder of the sFTP user on the distant server.
`sftpFileName` | Name of the file to remove. Wildcard characters such as "*" are supported. | string | Yes	


### Examples

The following consolidator will remove all CSV files starting with "data_" from the imports/ folder from 10.145.23.15 as user user.

```xml 
<consolidators>
	<removeFromSFTP>
		<sftpHost>10.145.23.15</sftpHost>
		<sftpLogin>user</sftpLogin>
		<sftpPassword>p4ssword</sftpPassword>
		<sftpFolder>/imports/</sftpFolder>
		<sftpFile>data_*.csv</sftpFile>
	</removeFromSFTP>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`The [...] parameter is missing.` |	One of the five mandatory options is missing.
`Unable to remove the file from the SFTP server: error [...]` |	An unexpected error has occured while trying to remove the distant files.