---
title: Learning Object Metadata
keywords: learning object, LO, metadata
last_updated: September, 2019
tags: 
summary: "This provider generates a data report containing Learning Object metadata. The following columns for each Learning Object can be included in this report.
    <br/>All the metadata fields specific to a version of a resource (ex: title, code, tags, authors) will return the value of the field for the best version according to the context (version must be active, and can depend on the preferred locales from the export's parameters)."
sidebar: home_sidebar
permalink: lo-metadata-provider.html
folder: Export
dynamic_content: true
columns: [learningObjectAuthorId, learningObjectAuthorFirstName, learningObjectAuthorLastName,
    learningObjectAuthorsIds, learningObjectAuthorsFullNames, learningObjectId, 
    learningObjectCode, learningObjectDuration, learningObjectGuid, learningObjectIncludedInLO, learningObjectLearningPoints, 
    learningObjectLevel, learningObjectLocales, learningObjectPublisher, learningObjectSummary, learningObjectTags, 
    learningObjectTargetAudience, learningObjectTitle, learningObjectThemes, learningObjectThumbnailSmall, 
    learningObjectThumbnailMedium, learningObjectThumbnailLarge, learningObjectType, learningObjectDisplayedType, 
    learningObjectAssignements, learningObjectAverageScore, learningObjectAverageCompletionTime, learningObjectCompletions, 
    learningObjectNbOfComments, learningObjectNbTimesFavorited, learningObjectRatingByLearners, learningObjectRatingDisplayed, 
    learningObjectRatingNbByLearners, learningObjectRatingNbDisplayed, learningObjectTotalTimeSpent, 
    learningObjectViewsByLearners, learningObjectViewsDisplayed, learningObjectCreationDate, learningObjectModificationDate, 
    learningObjectFirstLaunchDate, learningObjectLastLaunchDate]
parameters: [preferredLocales, dateFormat, dateTimeFormat, timeFrames, timeFramesScale, templates, stripHTML, maxLength, 
    onlyHrisSelectedItems]
---

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