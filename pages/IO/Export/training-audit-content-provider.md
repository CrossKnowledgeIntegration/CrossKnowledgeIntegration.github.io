---
title: Training Audit Content
keywords:
last_updated: September, 2019
tags: 
summary: "This provider exports data about the learning objects included in a given set of training courses."
sidebar: home_sidebar
permalink: training-audit-content-provider.html
folder: Export
dynamic_content: true
important_note: This provider also allows to use all the columns from the provider <a href="training-audit-metadata-provider.html">'Training Audit Metadata'</a>
columns: [trainingContentGuid, trainingContentCode, trainingContentTitle, trainingContentType, trainingContentRuntime,
    trainingContentAuthor, trainingContentCatalog, trainingContentSubtype, trainingContentOrder, trainingContentFolder,
    trainingContentMandatory]
parameters: [trainingIds, templates, stripHTML, maxLength]
---

### Example
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