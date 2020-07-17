---
title: Audit - Training Audit 
keywords: training, audit, detailed, training data, training specifications
last_updated: September, 2019
tags: 
summary: "The training audit export will allow you to have detailed trainings data, that are not available in the training metadata export."
sidebar: home_sidebar
permalink: training-audit-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>Blendedx and Learning Channel trainings</b>. It can be helpful when you need detailed information about the trainings (as status, publisher, language, goals, descriptions). Those data are defined when the training is being created.
    <br/><br/>

    If you want to have a simpler training export, please take a look at <a href="training-course-metadata-provider.html">Training metadata export</a>.
    <br/><br/>	

    <u>Example:</u> 
        <i>The <b>Blendedx</b> training "<b>Welcome aboard</b>" is <b>published in English</b> and his target audience is <b>all the new joiners</b>.The goal is help the new joiners to <b>understand how the company works</b> and the expected duration is <b>40 minutes</b>.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [trainingAudience, trainingId, trainingBenefits, trainingBOLink, trainingChapters, description, trainingDescription, 
    trainingDuration, trainingFolderDescription, trainingFurtherInformation, trainingGoals, 
    trainingGuid, trainingLearningPath, trainingLocale, modality, trainingPathCode, trainingPrice, title, trainingTitle, 
    trainingWelcomeText, catalogVisibility, trainingStatus, trainingPublisher, constantValue]
parameters: [trainingIds, trainingStatus, trainingStatusFormat, catalogVisibility, trainingSelectedLocales, templates,
    stripHTML, maxLength]
---

## Training Audit

It is available for **Blendedx and Learning Channel trainings**. It can be helpful when you need detailed information about the trainings (as status, publisher, language, goals, descriptions). Those data are defined when the training is being created.

If you want to have a simpler training export, please take a look at [Training metadata export](htttp://localhost:4000/training-course-metadata-provider.html).

> Example: _The **Blendedx** training "**Welcome aboard**" is **published in English** and his target audience is **all the new joiners**.The goal is help the new joiners to **understand how the company works** and the expected duration is **40 minutes**._

To check an **export sample file**, [click here](https://).

<!--### Example
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
-->