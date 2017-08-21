---
title: Training Audit Metadata provider
keywords: training metadata, training course, training path
last_updated: 21 August, 2017
tags: 
summary: "This provider exports data about a specified set of training courses."
sidebar: home_sidebar
permalink: training-audit-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingAudience` | {{site.data.IO_items.col.trainingAudience.desc}}
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingBenefits` | {{site.data.IO_items.col.trainingBenefits.desc}}
`trainingBOLink` | {{site.data.IO_items.col.trainingBOLink.desc}}
`trainingChapters` | {{site.data.IO_items.col.trainingChapters.desc}}
`description` | {{site.data.IO_items.col.description.desc}}
`trainingDescription` | {{site.data.IO_items.col.trainingDescription.desc}}
`trainingDigestSettings` | {{site.data.IO_items.col.trainingDigestSettings.desc}}
`trainingDuration` | {{site.data.IO_items.col.trainingDuration.desc}}
`trainingFolderDescription` | {{site.data.IO_items.col.trainingFolderDescription.desc}}
`trainingFurtherInformation` | {{site.data.IO_items.col.trainingFurtherInformation.desc}}
`trainingGoals` | {{site.data.IO_items.col.trainingGoals.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`trainingLearningPath` | {{site.data.IO_items.col.trainingLearningPath.desc}}
`trainingLocale` | {{site.data.IO_items.col.trainingLocale.desc}}
`modality` | {{site.data.IO_items.col.modality.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`trainingPrice` | {{site.data.IO_items.col.trainingPrice.desc}}
`title` | {{site.data.IO_items.col.title.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingWelcomeText` | {{site.data.IO_items.col.trainingWelcomeText.desc}}
`catalogVisibility` | {{site.data.IO_items.col.catalogVisibility.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`catalogVisibility` | {{site.data.IO_items.param.catalogVisibility.desc}}
`trainingIds` | {{site.data.IO_items.param.trainingIds.desc}}
`trainingStatus` | {{site.data.IO_items.param.trainingStatus.desc}}
`trainingStatusFormat` | {{site.data.IO_items.param.trainingStatusFormat.desc}}
`selectedLocales` | {{site.data.IO_items.param.selectedLocales.desc}}


### Examples
```xml
<export>
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
    <actions>
        <fileExportAction>
            <format>CSV</format>
            <encoding>UTF-8</encoding>
            <delimiter>semicolon</delimiter>
            <showHeaders>yes</showHeaders>
        </fileExportAction>
    </actions>
    <consolidators>
        <moveToFolder>
            <fileName>Training_Audit_metadata.csv</fileName>
    </consolidators>
</export>           
```