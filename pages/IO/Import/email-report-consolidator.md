---
title: Email Report Consolidator
keywords: consolidator, import, data, timeLogger
last_updated: 08 November, 2017
tags:
summary: "Send a summary report of all the operations done during the import. If this consolidator is executed after the one for error logging, the user can choose whether or not to include a link to download the error log in the e-mail."
sidebar: home_sidebar
permalink: consolidated-tracking-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`targetEmail` |	The e-mail address to send the summary to. This option may be declared multiple times in order to define several target e-mail addresses.| string |	Yes	
`disabled` | Whether this consolidator is disabled or not.| yesNoElement | No | No
`includeDownloadLink` |	Whether or not to include the download link to the error log file. | yesNoElement |	No |	


### Examples

```xml 
<consolidators>
	<emailReport>
		<targetEmail>admin1@crossknowledge.com</targetEmail>
		<targetEmail>admin2@crossknowledge.com</targetEmail>
		<includeDownloadLink>yes</includeDownloadLink>
	</emailReport>
</consolidators>
```

### Error Messages

Message | Explanation
--- | ---
`The targetEmail parameter is missing.`	 | No target e-mail address was given in the options of the consolidator.
`The targetEmail parameter is an invalid email: [...]` | One of the target e-mail address is invalid.