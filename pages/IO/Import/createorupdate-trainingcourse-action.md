---
title: Create Or Update Training Course Action
keywords: training course, import, data, createOrUpdateTrainingCourseAction
last_updated: 08 November, 2017
tags:
summary: "Create or update a training course with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-trainingcourse-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`lovCodes` | See columnsMapping_lovCodes.|	actionColumn | No	
`trainingAction` | See columnsMapping_trainingAction.|	actionColumn | Yes	
`trainingAudience` | See columnsMapping_trainingAudience.|	actionColumn | No	
`trainingCost` | See columnsMapping_trainingCost.|	actionColumn | No	
`trainingDescription` |	See columnsMapping_trainingDescription.| actionColumn |	No	
`trainingDuration` | See columnsMapping_trainingDuration.|	actionColumn | No	
`trainingFurtherInformation` |	See columnsMapping_trainingFurtherInformation.|	actionColumn | No	
`trainingLocale` |	See columnsMapping_trainingLocale.|	actionColumn | No	
`trainingModality` | See columnsMapping_trainingModality.|	actionColumn | No	
`trainingOutcomes` | See columnsMapping_trainingOutcomes.|	actionColumn | No	
`trainingOverview` | See columnsMapping_trainingOverview.|	actionColumn | No	
`trainingPathCode` | See columnsMapping_trainingPathCode.|	actionColumn | Yes	
`trainingScoreSuccessThreshold` | See columnsMapping_trainingScoreSuccessThreshold.| actionColumn |	No	
`trainingScoresVisibleByLearners` |	See columnsMapping_trainingScoresVisibleByLearners.| actionColumn |	No	
`trainingTitle` | See columnsMapping_trainingTitle.| actionColumn |	No	
`trainingWhatYouWillLearn` | See columnsMapping_trainingWhatYouWillLearn.|	actionColumn | No	
`trainingWelcomeText` |	See columnsMapping_trainingWelcomeText.| actionColumn |	No

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fullAccess` | This option is used to specify whether the current import process can modify information
out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself. | yesNoElement | No


### Examples

```xml 
<actions>
	<createOrUpdateTrainingCourseAction>
		<options>
			<fullAccess>yes</fullAccess>
		</options>
		<fields>
			<trainingAction/>
			<trainingTitle>
				<mandatory>no</mandatory>
			</trainingTitle>
			<trainingPathCode/>
			<trainingLocale>
				<mandatory>no</mandatory>
			</trainingLocale>
			<trainingModality>
				<mandatory>no</mandatory>
			</trainingModality>
			<lovCodes>
				<mandatory>no</mandatory>
			</lovCodes>
			<trainingDescription>
				<mandatory>no</mandatory>
			</trainingDescription>
			<trainingCost>
				<mandatory>no</mandatory>
			</trainingCost>
			<trainingDuration>
				<mandatory>no</mandatory>
			</trainingDuration>
			<trainingWhatYouWillLearn>
				<mandatory>no</mandatory>
			</trainingWhatYouWillLearn>
			<trainingOverview>
				<mandatory>no</mandatory>
			</trainingOverview>
			<trainingOutcomes>
				<mandatory>no</mandatory>
			</trainingOutcomes>
			<trainingAudience>
				<mandatory>no</mandatory>
			</trainingAudience>
			<trainingFurtherInformation>
				<mandatory>no</mandatory>
			</trainingFurtherInformation>
			<trainingWelcomeText>
				<mandatory>no</mandatory>
			</trainingWelcomeText>
			<trainingScoreSuccessThreshold>
				<mandatory>no</mandatory>
			</trainingScoreSuccessThreshold>
			<trainingScoresVisibleByLearners>
				<mandatory>no</mandatory>
			</trainingScoresVisibleByLearners>
		</fields>
	</createOrUpdateTrainingCourseAction>
</actions>>
```

### Error Messages

Message | Explanation
---- | ----
`Field [...] is empty.` | A mandatory field was not filled.
`lovCodes error: LOV ref number [...] is more than one LO or doesn't exist.` |	A row from the import file has provided an LOV reference number that references several LOVs, therefore, the application is not able to choose which one to include in the training course.
`The modality must be "distancelearning" or "knowledgecommunity", [...] detected."` | A row from the import file has provided a trainingModality value that is not allowed.