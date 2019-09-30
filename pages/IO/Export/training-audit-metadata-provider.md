---
title: Training Audit Metadata
keywords: training metadata, training course, training path
last_updated: September, 2019
tags: 
summary: "This provider exports data about a specified set of training courses."
sidebar: home_sidebar
permalink: training-audit-metadata-provider.html
folder: Export
dynamic_content: true
columns: [trainingAudience, trainingId, trainingBenefits, trainingBOLink, trainingChapters, description, trainingDescription, 
    trainingDuration, trainingFolderDescription, trainingFurtherInformation, trainingGoals, 
    trainingGuid, trainingLearningPath, trainingLocale, modality, trainingPathCode, trainingPrice, title, trainingTitle, 
    trainingWelcomeText, catalogVisibility, trainingStatus, trainingPublisher, constantValue]
parameters: [trainingIds, trainingStatus, trainingStatusFormat, catalogVisibility, selectedLocales, templates,
    stripHTML, maxLength]
---

### Example
```xml
<providers>
	<trainingAuditMetadataProvider>
		<columns>
			<trainingAudience/>
			<trainingId/>
			<trainingBenefits/>
			<trainingBOLink/>
			<trainingChapters/>
			<description/>
			<trainingDescription/>
			<trainingDigestSettings/>
			<trainingDuration/>
			<trainingFolderDescription/>
			<trainingFurtherInformation/>
			<trainingGoals/>
			<trainingGuid/>
			<trainingLearningPath/>
			<trainingLocale/>
			<modality/>
			<trainingPathCode/>
			<trainingPrice/>
			<title/>
			<trainingTitle/>
			<trainingWelcomeText/>
			<catalogVisibility/>
			<trainingStatus/>
			<constantValue/>
		</columns>
		<parameters>
			<trainingStatus>P</trainingStatus>
		</parameters>
	</trainingAuditMetadataProvider>
</providers> 
```