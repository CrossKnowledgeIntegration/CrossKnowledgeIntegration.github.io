---
title: Consolidated Gamification Badges
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: consolidated-gamification-badges-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateEntityName` | {{site.data.IO_items.col.candidateEntityName.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`badgeCode` | {{site.data.IO_items.col.badgeCode.desc}}
`badge` | {{site.data.IO_items.col.badge.desc}}
`badgeCategory` | {{site.data.IO_items.col.badgeCategory.desc}}
`badgeDateTime` | {{site.data.IO_items.col.badgeDateTime.desc}}
`locale` | {{site.data.IO_items.col.locale.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`entityIds` | {{site.data.IO_items.param.entityIds.desc}}
`preferredLocales` | {{site.data.IO_items.param.preferredLocales.desc}}
`badgeCategory` | {{site.data.IO_items.param.badgeCategory.desc}}
`deltaMode` | {{site.data.IO_items.param.deltaMode.desc}}


### Examples
```xml
<providers>
    <consolidatedGamificationBadgesProvider>
        <columns>
            <candidateId/>
            <candidateGuid/>
            <candidateName/>
            <candidateFirstname/>
            <candidateRefNumber/>
            <candidateLogin/>
            <candidateEmail/>
            <candidateEntityName/>
            <candidateCustomFieldGuid/>
            <badgeCode/>
            <badge/>
            <badgeCategory/>
            <badgeDateTime/>
            <locale/>
            <constantValue/>
        </columns>
        <parameters>
            <dateTimeFormat>YYYY-MM-DD hh:ii:ss</dateTimeFormat>
        </parameters>
    </consolidatedGamificationBadgesProvider>
</providers>
```