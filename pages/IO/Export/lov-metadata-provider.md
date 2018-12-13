---
title: Learning Object Version Metadata
keywords: LOV, learning object version, learning object, metadata, report, export
last_updated: 13 December, 2018
tags: 
summary: "This provider generates a data report containing metadata of all versions of Learning Object versions available on the platform"
sidebar: home_sidebar
permalink: lov-metadata-provider.html
folder: Export
---


### Available columns

Name | Description
---|---
`learningObjectVersionLoId` | {{site.data.IO_items.col.learningObjectVersionLoId.desc}}
`learningObjectVersionLoGuid` | {{site.data.IO_items.col.learningObjectVersionLoGuid.desc}}
`learningObjectVersionId` | {{site.data.IO_items.col.learningObjectVersionId.desc}}
`learningObjectVersionGuid` | {{site.data.IO_items.col.learningObjectVersionGuid.desc}}
`learningObjectVersionCode` | {{site.data.IO_items.col.learningObjectVersionCode.desc}}
`learningObjectVersionTitle` | {{site.data.IO_items.col.learningObjectVersionTitle.desc}}
`learningObjectVersionSummary` | {{site.data.IO_items.col.learningObjectVersionSummary.desc}}
`learningObjectVersionPublisher` | {{site.data.IO_items.col.learningObjectVersionPublisher.desc}}
`learningObjectVersionType` | {{site.data.IO_items.col.learningObjectVersionType.desc}}
`learningObjectVersionDisplayedType` | {{site.data.IO_items.col.learningObjectVersionDisplayedType.desc}}
`learningObjectVersionVersion` | {{site.data.IO_items.col.learningObjectVersionVersion.desc}}
`learningObjectVersionAuthorId` | {{site.data.IO_items.col.learningObjectVersionAuthorId.desc}}
`learningObjectVersionAuthorFirstName` | {{site.data.IO_items.col.learningObjectVersionAuthorFirstName.desc}}
`learningObjectVersionAuthorLastName` | {{site.data.IO_items.col.learningObjectVersionAuthorLastName.desc}}
`learningObjectVersionDuration` | {{site.data.IO_items.col.learningObjectVersionDuration.desc}}
`learningObjectVersionIncludedInLO` | {{site.data.IO_items.col.learningObjectVersionIncludedInLO.desc}}
`learningObjectVersionLearningPoints` | {{site.data.IO_items.col.learningObjectVersionLearningPoints.desc}}
`learningObjectVersionLevel` | {{site.data.IO_items.col.learningObjectVersionLevel.desc}}
`learningObjectVersionLocale` | {{site.data.IO_items.col.learningObjectVersionLocale.desc}}
`learningObjectVersionTags` | {{site.data.IO_items.col.learningObjectVersionTags.desc}}
`learningObjectVersionTargetAudience` | {{site.data.IO_items.col.learningObjectVersionTargetAudience.desc}}
`learningObjectVersionThemes` | {{site.data.IO_items.col.learningObjectVersionThemes.desc}}
`learningObjectVersionThumbnailSmall` | {{site.data.IO_items.col.learningObjectVersionThumbnailSmall.desc}}
`learningObjectVersionThumbnailMedium` | {{site.data.IO_items.col.learningObjectVersionThumbnailMedium.desc}}
`learningObjectVersionThumbnailLarge` | {{site.data.IO_items.col.learningObjectVersionThumbnailLarge.desc}}
`learningObjectVersionCreationDate` | {{site.data.IO_items.col.learningObjectVersionCreationDate.desc}}
`learningObjectVersionModificationDate` | {{site.data.IO_items.col.learningObjectVersionModificationDate.desc}}
`learningObjectVersionFirstLaunchDate` | {{site.data.IO_items.col.learningObjectVersionFirstLaunchDate.desc}}
`learningObjectVersionLastLaunchDate` | {{site.data.IO_items.col.learningObjectVersionLastLaunchDate.desc}}
`learningObjectVersionAssignements` | {{site.data.IO_items.col.learningObjectVersionAssignements.desc}}
`learningObjectVersionAverageCompletionTime` | {{site.data.IO_items.col.learningObjectVersionAverageCompletionTime.desc}}
`learningObjectVersionAverageScore` | {{site.data.IO_items.col.learningObjectVersionAverageScore.desc}}
`learningObjectVersionCompletions` | {{site.data.IO_items.col.learningObjectVersionCompletions.desc}}
`learningObjectVersionTotalTimeSpent` | {{site.data.IO_items.col.learningObjectVersionTotalTimeSpent.desc}}
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
