---
title: Audit - Content Audit
keywords: content, resource, object, audit, metadata, provider, export, detailed, content data, lo, learning resource audit, learning object
last_updated: September, 2019
tags: 
summary: "The content audit export will have detailed learning object data related to the trainings."
sidebar: home_sidebar
permalink: training-audit-content-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It can be helpful when you need to map which learning objects are available in a training. It will contain detailed informations about the contents in the training (e.g: if it is mandatory, who is the author and what is the content type).
    <br/><br/>

    <u>Example:</u> 
        <i>The <b>Focus and Productivity video</b> content is available in the <b>"Welcome aboard" Blendedx</b> training. It is a <b>mandatory</b> learning object and the author is <b>John Doe</b>.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [catalogVisibility, constantValue, trainingDescription, modality, title, trainingAudience, trainingBOLink, trainingBenefits, trainingChapters, trainingContentAuthor, trainingContentCatalog, trainingContentCode, trainingContentFolder, trainingContentGuid, trainingContentId, trainingContentMandatory, trainingContentOrder, trainingContentRuntime, trainingContentTitle, trainingContentType, trainingContentSubtype, trainingId, description, trainingDuration, trainingFolderDescription, trainingFurtherInformation, trainingGoals, trainingGuid, trainingLearningPath, trainingLocale, trainingPathCode, trainingPrice, trainingTitle, trainingWelcomeText, trainingStatus, trainingPublisher]
parameters: [trainingIds, templates, stripHTML, maxLength]
---

## Content Audit

It can be helpful when you need to map which learning objects are available in a training. It will contain detailed informations about the contents in the training (as if it is mandatory, who is the author and what is the content type).

> Example: _The **Focus and Productivity video** content is available in the **"Welcome aboard" Blendedx** training. It is a mandatory learning object and the author is **John Doe**._

To check an **export sample file**, [click here](https://).

<!--
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
            <trainingContentId/>
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
-->