---
title: Learning Object Version metadata
keywords: LOV, learning object version, learning object, metadata, report, export
last_updated: September, 2019
tags: 
summary: "The learning object version metadata will allow you to have detailed data about versions of the learning object. It is not related to a specific training or session."
sidebar: home_sidebar
permalink: lov-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It allows you to have detailed information about the versions of the learning objects. Each row in the export will be related to the latest learning object version for each available language.
    <br/><br/>

    If you want to have the content data related to a specific training, please take a look at <a href="training-audit-content-provider.html">Content Audit export</a>.
    <br/><br/>	

    <u>Example:</u> 
    <br/>
        <i>
            The <b>Managing your time</b> interactive content is available in <b>English</b> and <b>French</b>. The English version had more updates than the French version:
        <li>
            The <u>Managing your time in English</u> is on the <b> 3rd version </b>. The latest version was launched on <b>2020-06-20</b> and it was accessed by <b>15 learners</b> in the platform. The learners spent <b>around 5 minutes</b> in this content and the content duration is <b>3 minutes</b>. The target audience is <b>all the employees</b>.
        </li>
        <li>
            The <u>Managing your time in French</u> is on the <b> 1st version </b>. The latest version was launched on <b>2020-03-30</b> and it was accessed by <b>25 learners</b> in the platform. The learners spent <b>around 8 minutes</b> in this content and the content duration is <b>5 minutes</b>. The target audience is <b>all the French employees</b>.
        </li>
        </i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [learningObjectVersionLoId, learningObjectVersionLoGuid, learningObjectVersionId, learningObjectVersionGuid, 
    learningObjectVersionCode, learningObjectVersionTitle, learningObjectVersionSummary, learningObjectVersionPublisher, 
    learningObjectVersionType, learningObjectVersionDisplayedType, learningObjectVersionVersion, learningObjectVersionAuthorId, 
    learningObjectVersionAuthorFirstName, learningObjectVersionAuthorLastName, learningObjectVersionDuration, 
    learningObjectVersionIncludedInLO, learningObjectVersionLearningPoints, learningObjectVersionLevel, 
    learningObjectVersionLocale, learningObjectVersionTags, learningObjectVersionTargetAudience, learningObjectVersionThemes, 
    learningObjectVersionThumbnailSmall, learningObjectVersionThumbnailMedium, learningObjectVersionThumbnailLarge, 
    learningObjectVersionCreationDate, learningObjectVersionModificationDate, learningObjectVersionFirstLaunchDate, 
    learningObjectVersionLastLaunchDate, learningObjectVersionAssignements, learningObjectVersionAverageCompletionTime, 
    learningObjectVersionAverageScore, learningObjectVersionCompletions, learningObjectVersionTotalTimeSpent, 
    learningObjectVersionIsMobile, learningObjectVersionStatus]
parameters: [dateFormat, dateTimeFormat, contentTimeFrames, contentTimeFramesScale, excludeDeactivatedContents, templates, durationFormat, stripHTML, maxLength, onlyHrisSelectedItems, contentPreferredLocales]
---

## Learning Object Version metadata

It allows you to have an overview about the versions of the learning objects. Each row in the export will
This report allows to have a **detailed** learning object data, but it also have informations on the **use of the content** in all the trainings that it is associated.

A learning object are the contents that are added to the CrossKnowledge platform and will help to improve the learning (as videos, interative contents, audios, images, PDF). Native activities are not included (poll, classroom, end of course survey, etc).

If you want to have the content data related to a specific training, please take a look at [Content Audit export](htttp://localhost:4000/training-audit-content-provider.html).

> Example: _The **Managing your time** interative resource was launched at **2020-03-15** and is already completed by **30 learners** in the platform. The learners spend **about 20 minutes** in this content and **10** learners favorited it. This content is available in **French and English**, it is level **2** and the target audience is **all the employees**._

To check an **export sample file**, [click here](https://).

<!--
### Example
```xml
<providers>
    <learningObjectVersionMetadataProvider>
        <columns>
            <learningObjectVersionLoId/>
            <learningObjectVersionLoGuid/>
            <learningObjectVersionId/>
            <learningObjectVersionGuid/>
            <learningObjectVersionCode/>
            <learningObjectVersionTitle/>
            <learningObjectVersionSummary/>
            <learningObjectVersionPublisher/>
            <learningObjectVersionType/>
            <learningObjectVersionDisplayedType/>
            <learningObjectVersionVersion/>
            <learningObjectVersionAuthorId/>
            <learningObjectVersionAuthorFirstName/>
            <learningObjectVersionAuthorLastName/>
            <learningObjectVersionDuration/>
            <learningObjectVersionIncludedInLO/>
            <learningObjectVersionLearningPoints/>
            <learningObjectVersionLevel/>
            <learningObjectVersionLocale/>
            <learningObjectVersionTags/>
            <learningObjectVersionTargetAudience/>
            <learningObjectVersionThemes/>
            <learningObjectVersionThumbnailSmall/>
            <learningObjectVersionThumbnailMedium/>
            <learningObjectVersionThumbnailLarge/>
            <learningObjectVersionCreationDate/>
            <learningObjectVersionModificationDate/>
            <learningObjectVersionFirstLaunchDate/>
            <learningObjectVersionLastLaunchDate/>
            <learningObjectVersionAssignements/>
            <learningObjectVersionAverageCompletionTime/>
            <learningObjectVersionAverageScore/>
            <learningObjectVersionCompletions/>
            <learningObjectVersionTotalTimeSpent/>
        </columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </learningObjectVersionMetadataProvider>
</providers>     
```
-->
