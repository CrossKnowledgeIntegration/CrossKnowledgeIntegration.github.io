---
title: Mass Disable Learners Consolidator
keywords: consolidator, import, data, massDisableLearners
last_updated: 08 November, 2017
tags:
summary: "Disable a set of learners, chosen by the specified options. Whereas other consolidators can only appear once, this consolidator can be specified twice. The three options noInscriptions, inscriptionsWithExpiredSession and oldLearners are exclusive, however you can combine one of them with fullAccess."
sidebar: home_sidebar
permalink: mass-disable-learners-consolidator.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fullAccess` |	This option is used to specify whether the current import process can modify information out of its scope. If it is set to no, then it will only be able to modify the learners that were previously created by itself. | yesNoElement | No | No
`noInscriptions` |	If this option is specified, learners that are not enrolled to any training courses will be disabled.| string | No	
`inscriptionsWithExpiredSession` |	If this option is specified, learners that are enrolled to sessions that have expired will be disabled.| string | |No	
`oldLearners`| If this option is specified, all the learners will be disabled, except those that have just been imported.| string |	No	


### Examples

```xml 
<consolidators>
	<massDisableLearners>
		<fullAccess>yes</fullAccess>
	</massDisableLearners>
	<massDisableLearners>
		<noInscriptions/>
	</massDisableLearners>
</consolidators>
```

### Error Messages

Message | Explanation
---- | ----
`This consolidation was cancelled because only one of these options can be used at the same time (noInscriptions, inscriptionsWithExpiredSession or oldLearners).`	The three options listed here are exclusive.