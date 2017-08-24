---
title: Learning Object Metadata
keywords: learning object, LO, metadata
last_updated: 23 August, 2017
tags: 
summary: "This provider generates a data report containing Learning Object metadata. The following columns for each Learning Object can be included in this report."
sidebar: home_sidebar
permalink: lo-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`learningObjectAuthorId` | {{site.data.IO_items.col.learningObjectAuthorId.desc}}
`learningObjectAuthorFirstName` | {{site.data.IO_items.col.learningObjectAuthorFirstName.desc}}
`learningObjectAuthorLastName` | {{site.data.IO_items.col.learningObjectAuthorLastName.desc}}
`learningObjectId` | {{site.data.IO_items.col.learningObjectId.desc}}
`learningObjectCode` | {{site.data.IO_items.col.learningObjectCode.desc}}
`learningObjectDuration` | {{site.data.IO_items.col.learningObjectDuration.desc}}
`learningObjectGuid` | {{site.data.IO_items.col.learningObjectGuid.desc}}
`learningObjectIncludedInLO` | {{site.data.IO_items.col.learningObjectIncludedInLO.desc}}
`learningObjectLearningPoints` | {{site.data.IO_items.col.learningObjectLearningPoints.desc}}
`learningObjectLevel` | {{site.data.IO_items.col.learningObjectLevel.desc}}
`learningObjectLocales` | {{site.data.IO_items.col.learningObjectLocales.desc}}
`learningObjectPublisher` | {{site.data.IO_items.col.learningObjectPublisher.desc}}
`learningObjectSummary` | {{site.data.IO_items.col.learningObjectSummary.desc}}
`learningObjectTags` | {{site.data.IO_items.col.learningObjectTags.desc}}
`learningObjecthoTargetAudience` | {{site.data.IO_items.col.learningObjectTargetAudience.desc}}
`learningObjectTitle` | {{site.data.IO_items.col.learningObjectTitle.desc}}
`learningObjectThemes` | {{site.data.IO_items.col.learningObjectThemes.desc}}
`learningObjectThumbnailSmall` | {{site.data.IO_items.col.learningObjectThumbnailSmall.desc}}
`learningObjectThumbnailMedium` | {{site.data.IO_items.col.learningObjectThumbnailMedium.desc}}
`learningObjectThumbnailLarge` | {{site.data.IO_items.col.learningObjectThumbnailLarge.desc}}
`learningObjectType` | {{site.data.IO_items.col.learningObjectType.desc}}
`learningObjectDisplayedType` | {{site.data.IO_items.col.learningObjectDisplayedType.desc}}
`learningObjectAssignements` | {{site.data.IO_items.col.learningObjectAssignements.desc}}
`learningObjectAverageScore` | {{site.data.IO_items.col.learningObjectAverageScore.desc}}
`learningObjectAverageCompletionTime` | {{site.data.IO_items.col.learningObjectAverageCompletionTime.desc}}
`learningObjectCompletions` | {{site.data.IO_items.col.learningObjectCompletions.desc}}
`learningObjectNbOfComments` | {{site.data.IO_items.col.learningObjectNbOfComments.desc}}
`learningObjectNbTimesFavorited` | {{site.data.IO_items.col.learningObjectNbTimesFavorited.desc}}
`learningObjectRatingByLearners` | {{site.data.IO_items.col.learningObjectRatingByLearners.desc}}
`learningObjectRatingDisplayed` | {{site.data.IO_items.col.learningObjectRatingDisplayed.desc}}
`learningObjectRatingNbByLearners` | {{site.data.IO_items.col.learningObjectRatingNbByLearners.desc}}
`learningObjectRatingNbDisplayed` | {{site.data.IO_items.col.learningObjectRatingNbDisplayed.desc}}
`learningObjectTotalTimeSpent` | {{site.data.IO_items.col.learningObjectTotalTimeSpent.desc}}
`learningObjectViewsByLearners` | {{site.data.IO_items.col.learningObjectViewsByLearners.desc}}
`learningObjectViewsDisplayed` | {{site.data.IO_items.col.learningObjectViewsDisplayed.desc}}
`learningObjectCreationDate` | {{site.data.IO_items.col.learningObjectCreationDate.desc}}
`learningObjectModificationDate` | {{site.data.IO_items.col.learningObjectModificationDate.desc}}
`learningObjectFirstLaunchDate` | {{site.data.IO_items.col.learningObjectFirstLaunchDate.desc}}
`learningObjectLastLaunchDate` | {{site.data.IO_items.col.learningObjectLastLaunchDate.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`preferredLocales` | {{site.data.IO_items.param.preferredLocales.desc}}
`dateFormat` | {{site.data.IO_items.param.dateFormat.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}

### Examples
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