---
title: Learning Object metadata
keywords: learning object, LO, metadata, learning, object, resource, content
last_updated: September, 2019
tags: 
summary: "The learning object metadata will allow you to have detailed learning object information. It is not related to a specific training or session."
sidebar: home_sidebar
permalink: lo-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is important to have a learning object overview. This report allows you to have a <b>detailed</b> learning object data, but it also have informations about the <b>use of the content</b> in all the trainings that it is associated.
    <br/><br/>

    A learning object is the content that is added to the CrossKnowledge platform and will <b>help to improve</b> the learning (as <b>videos, interative contents, audios, images, PDF</b>). Native activities are not included (poll, classroom, end of course survey, etc).
    <br/><br/>

    If you want to have the content data related to a specific training, please take a look at <a href="training-audit-content-provider.html">Content Audit export</a>.
    <br/><br/>	

    <u>Example:</u> 
        <i>The <b>Managing your time</b> interactive content was launched on <b>2020-03-15</b> and is already completed by <b>30 learners</b> in the platform. The learners spent <b>around 20 minutes</b> in this content and <b>10</b> learners favorited it. This content is available in <b>French and English</b>, it is level <b>2</b> and the target audience is <b>all the employees</b>.</i>
    <br/><br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [learningObjectAuthorId, learningObjectAuthorFirstName, learningObjectAuthorLastName, learningObjectId, 
    learningObjectCode, learningObjectDuration, learningObjectGuid, learningObjectIncludedInLO, learningObjectLearningPoints, 
    learningObjectLevel, learningObjectLocales, learningObjectPublisher, learningObjectSummary, learningObjectTags, 
    learningObjectTargetAudience, learningObjectTitle, learningObjectThemes, learningObjectThumbnailSmall, 
    learningObjectThumbnailMedium, learningObjectThumbnailLarge, learningObjectType, learningObjectDisplayedType, 
    learningObjectAssignements, learningObjectAverageScore, learningObjectAverageCompletionTime, learningObjectCompletions, 
    learningObjectNbOfComments, learningObjectNbTimesFavorited, learningObjectRatingByLearners, learningObjectRatingDisplayed, 
    learningObjectRatingNbByLearners, learningObjectRatingNbDisplayed, learningObjectTotalTimeSpent, 
    learningObjectViewsByLearners, learningObjectViewsDisplayed, learningObjectCreationDate, learningObjectModificationDate, 
    learningObjectFirstLaunchDate, learningObjectLastLaunchDate]
parameters: [contentPreferredLocales, dateFormat, dateTimeFormat, contentTimeFrames, contentTimeFramesScale, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

## Learning Object metadata

It is important to have a learning object overview. This report allows to have a **detailed** learning object data, but it also have informations on the **use of the content** in all the trainings that it is associated.

A learning object are the contents that are added to the CrossKnowledge platform and will help to improve the learning (as videos, interative contents, audios, images, PDF). Native activities are not included (poll, classroom, end of course survey, etc).

If you want to have the content data related to a specific training, please take a look at [Content Audit export](htttp://localhost:4000/training-audit-content-provider.html).

> Example: _The **Managing your time** interative resource was launched at **2020-03-15** and is already completed by **30 learners** in the platform. The learners spend **about 20 minutes** in this content and **10** learners favorited it. This content is available in **French and English**, it is level **2** and the target audience is **all the employees**._

To check an **export sample file**, [click here](https://).

<!--
### Example
```xml
    <providers>
        <learningObjectMetadataProvider>
            <columns>
                <learningObjectAuthorId/>
                <learningObjectAuthorFirstName/>
                <learningObjectAuthorLastName/>
                <learningObjectId/>
                <learningObjectCode/>
                <learningObjectDuration/>
                <learningObjectGuid/>
                <learningObjectIncludedInLO/>
                <learningObjectLearningPoints/>
                <learningObjectLevel/>
                <learningObjectLocales/>
                <learningObjectPublisher/>
                <learningObjectSummary/>
                <learningObjectTags/>
                <learningObjectTargetAudience/>
                <learningObjectTitle/>
                <learningObjectThemes/>
                <learningObjectThumbnailSmall/>
                <learningObjectThumbnailMedium/>
                <learningObjectThumbnailLarge/>
                <learningObjectType/>
                <learningObjectDisplayedType/>
                <learningObjectAssignements/>
                <learningObjectAverageScore/>
                <learningObjectAverageCompletionTime/>
                <learningObjectCompletions/>
                <learningObjectNbOfComments/>
                <learningObjectNbTimesFavorited/>
                <learningObjectRatingByLearners/>
                <learningObjectRatingDisplayed/>
                <learningObjectRatingNbByLearners/>
                <learningObjectRatingNbDisplayed/>
                <learningObjectTotalTimeSpent/>
                <learningObjectViewsByLearners/>
                <learningObjectViewsDisplayed/>
                <learningObjectCreationDate/>
                <learningObjectModificationDate/>
                <learningObjectFirstLaunchDate/>
                <learningObjectLastLaunchDate/>
                <constantValue/>
            </columns>
            <parameters>
                <dateFormat>YYYY-MM-DD</dateFormat>
            </parameters>
        </learningObjectMetadataProvider>
    </providers>
```
-->