---
title: Learning Object Version Metadata
keywords: LOV, learning object version, learning object, metadata, report, export
last_updated: September, 2019
tags: 
summary: "This provider generates metadadata export report containing one line per Learning Object's localization, having the latest version of that LO for each language available on the platform"
sidebar: home_sidebar
permalink: lov-metadata-provider.html
folder: Export
dynamic_content: true
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
parameters: [dateFormat, dateTimeFormat, timeFrames, timeFramesScale, excludeDeactivatedContents, templates, durationFormat, 
    stripHTML, maxLength, onlyHrisSelectedItems, preferredLocales]
---

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
