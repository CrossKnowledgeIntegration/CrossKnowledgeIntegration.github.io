---
title: Create Or Update Training Course Action
keywords: training course, import, data, createOrUpdateTrainingCourseAction
last_updated: 27 March, 2018
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
`trainingSteps` |	See columnsMapping_trainingSteps.| actionColumn |	No

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fullAccess` | This option is used to specify whether the current import process can modify information. out of its scope. If it is set to no, then it will only be able to modify the sessions, learners and registrations that were previously created by itself. | yesNoElement | No
`lovCodes` | This option references the LO's refNumber and is used to specify wich LOs are included in the training course. It's possible to separate LOs by step with double pipe "\|\|" and into the step with comma "," (eg : "REF1,REF2\|\|REF3\|\|REF4"). | xs:string | No
`trainingModality` | This option is used to specify the modality of the created or updated training. Allowed values are: distancelearning,knowledgecommunity,learning_channel and blended. | xs:string | No
`trainingSteps` | This option is used to describe steps that will be added or updated. This option is only used for blended and blendedx modalities. This option is mandatory for blended modality, and mandatory for blendedx on course creation, but not for course update. Steps are separated by double pipe "\|\|" and the separator used to separate step title and step duration is "\|>". A step is described by "StepTitle\|>StepDuration" where StepTitle cannot be empty and duration is optionnal and it's a integer which represents step duration in days (eg : "Intro\|>1\|\|Basics\|>2\|\|Advanced concepts\|>4\|\|Conclusion"). | xs:string | No

### Borderline cases

* Blendedˣ training update

⋅⋅⋅On Blendedˣ update, if some LOs needs to be added, they are added at the end of the last step of the training. Furthermore, it's not possible to remove LOs and remove or update Steps.

⋅⋅⋅On Blendedˣ import, we create Content Milestones with some default values : Path menu title : LO title, Duration : LO duration, Max points : LO duration, Title : LO title, Subtitle : empty, CTA : "Epilang(Next)".

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
			<trainingSteps>
				<mandatory>no</mandatory>
			</trainingSteps>
		</fields>
	</createOrUpdateTrainingCourseAction>
</actions>>
```

### Error Messages

Message | Explanation
---- | ----
`Field [...] is empty.` | A mandatory field was not filled.
`lovCodes error: LOV ref number [...] is more than one LO or doesn't exist.` |	A row from the import file has provided an LOV reference number that references several LOVs, therefore, the application is not able to choose which one to include in the training course.
`The modality must be distancelearning, knowledgecommunity, learning_channel or blended, [...] detected."` | A row from the import file has provided a trainingModality value that is not allowed.
`You can't change the training's modality.` | A rwo from the import tries to modify the modality of an existing training. This action is not allowed.
`The field "trainingSteps" can't be empty when importing a blended training.` | A row from the import sets up a blended training but an empty value was found in the trainingSteps field.
`Step title error at step #[...] : The result of the title's sanitization is empty.` | The title of the step #[...] is empty. A title must be defined for each step.