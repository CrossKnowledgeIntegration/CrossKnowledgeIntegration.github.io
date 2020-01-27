---
title: Create Or Update Training Course Action
keywords: training course, import, data, createOrUpdateTrainingCourseAction
last_updated: October 2019
tags:
summary: "Create or update a training course with respect to the data row from the import file. It is possible to update existing training courses by matching the `trainingPathCode` columns."
sidebar: home_sidebar
permalink: createorupdate-trainingcourse-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [trainingAction, trainingPathCode, trainingLocale, trainingTitle, trainingModality, lovCodes, trainingDescription, 
    trainingCost, trainingDuration, trainingWhatYouWillLearn, trainingOverview, trainingOutcomes, trainingAudience, 
    trainingFurtherInformation, trainingWelcomeText, trainingSteps, ignoredColumn]
parameters: [fullAccess]
# The options trainingScoreSuccessThreshold, trainingScoresVisibleByLearners are willingly removed as they are legacy and furthermore depend on a very specific configuration variable that very few clients have.
---

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
			<trainingAction/><!-- Training Action and PathCode Mandatory -->
			<trainingPathCode/>
			<trainingLocale/>
			<trainingTitle/>
			<trainingModality/>
			<lovCodes/>
			<trainingDescription/>
			<trainingCost/>
			<trainingDuration/>			
			<trainingWhatYouWillLearn/>
			<trainingOverview/>
			<trainingOutcomes/>
			<trainingAudience/>
			<trainingFurtherInformation/>
			<trainingWelcomeText/>
			<trainingScoreSuccessThreshold/>
			<trainingScoresVisibleByLearners/>
			<trainingSteps/>
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
