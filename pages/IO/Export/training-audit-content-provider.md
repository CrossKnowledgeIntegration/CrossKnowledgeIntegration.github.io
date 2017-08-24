---
title: Training Audit Content
keywords:
last_updated: 24 August, 2017
tags: 
summary: "This provider exports data about the learning objects included in a given set of training courses."
sidebar: home_sidebar
permalink: training-audit-content-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingGuid` | {{site.data.IO_items.col.trainingGuid.desc}}
`trainingPathCode` | {{site.data.IO_items.col.trainingPathCode.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`modality` | {{site.data.IO_items.col.modality.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingDescription` | {{site.data.IO_items.col.trainingDescription.desc}}
`trainingDigestSettings` | {{site.data.IO_items.col.trainingDigestSettings.desc}}
`trainingDuration` | {{site.data.IO_items.col.trainingDuration.desc}}
`trainingFolderDescription` | {{site.data.IO_items.col.trainingFolderDescription.desc}}
`trainingFurtherInformation` | {{site.data.IO_items.col.trainingFurtherInformation.desc}}
`trainingGoals` | {{site.data.IO_items.col.trainingGoals.desc}}
`trainingLearningPath` | {{site.data.IO_items.col.trainingLearningPath.desc}}
`trainingLocale` | {{site.data.IO_items.col.trainingLocale.desc}}
`trainingPrice` | {{site.data.IO_items.col.trainingPrice.desc}}
`trainingWelcomeText` | {{site.data.IO_items.col.trainingWelcomeText.desc}}
`trainingAudience` | {{site.data.IO_items.col.trainingAudience.desc}}
`trainingBenefits` | {{site.data.IO_items.col.trainingBenefits.desc}}
`trainingBOLink` | {{site.data.IO_items.col.trainingBOLink.desc}}
`trainingChapters` | {{site.data.IO_items.col.trainingChapters.desc}}
`catalogVisibility` | {{site.data.IO_items.col.catalogVisibility.desc}}
`trainingContentGuid` | {{site.data.IO_items.col.trainingContentGuid.desc}}
`trainingContentCode` | {{site.data.IO_items.col.trainingContentCode.desc}}
`trainingContentTitle` | {{site.data.IO_items.col.trainingContentTitle.desc}}
`trainingContentType` | {{site.data.IO_items.col.trainingContentType.desc}}
`trainingContentSubtype` | {{site.data.IO_items.col.trainingContentSubtype.desc}}
`trainingContentRuntime` | {{site.data.IO_items.col.trainingContentRuntime.desc}}
`trainingContentAuthor` | {{site.data.IO_items.col.trainingContentAuthor.desc}}
`trainingContentMandatory` | {{site.data.IO_items.col.trainingContentMandatory.desc}}
`trainingContentCatalog` | {{site.data.IO_items.col.trainingContentCatalog.desc}}
`trainingContentFolder` | {{site.data.IO_items.col.trainingContentFolder.desc}}
`trainingContentOrder` | {{site.data.IO_items.col.trainingContentOrder.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`trainingIds` | {{site.data.IO_items.param.trainingIds.desc}}

### Examples
```xml
<providers>
    <trainingAuditContentProvider>
        <columns>
            <trainingId/>
            <trainingGuid/>
            <trainingPathCode/>
            <trainingStatus/>
            <modality/>
            <trainingTitle/>
            <trainingDescription/>
            <trainingDigestSettings/>
            <trainingDuration/>
            <trainingFolderDescription/>
            <trainingFurtherInformation/>
            <trainingGoals/>
            <trainingLearningPath/>
            <trainingLocale/>
            <trainingPrice/>
            <trainingWelcomeText/>
            <trainingAudience/>
            <trainingBenefits/>
            <trainingBOLink/>
            <trainingChapters/>
            <catalogVisibility/>
            <trainingContentGuid/>
            <trainingContentCode/>
            <trainingContentTitle/>
            <trainingContentType/>
            <trainingContentSubtype/>
            <trainingContentRuntime/>
            <trainingContentAuthor/>
            <trainingContentMandatory/>
            <trainingContentCatalog/>
            <trainingContentFolder/>
            <trainingContentOrder/>
            <constantValue/>
        </columns>
        <parameters>
            <trainingIds>10,11,12</trainingIds>
        </parameters>
    </trainingAuditContentProvider>
</providers>
```