---
title: Consolidated Gamification Events
keywords:
last_updated: 24 August, 2017
tags: 
summary: ""
sidebar: home_sidebar
permalink: consolidated-gamification-events-provider.html
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
`gamificationPoints` | {{site.data.IO_items.col.gamificationPoints.desc}}
`gamificationActionCode` | {{site.data.IO_items.col.gamificationActionCode.desc}}
`gamificationAction` | {{site.data.IO_items.col.gamificationAction.desc}}
`gamificationDateTime` | {{site.data.IO_items.col.gamificationDateTime.desc}}
`locale` | {{site.data.IO_items.col.locale.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}


### Filters and parameters

Name | Description
---|---
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`preferredLocales` | {{site.data.IO_items.param.preferredLocales.desc}}
`threshold` | {{site.data.IO_items.param.threshold.desc}}
`deltaMode` | {{site.data.IO_items.param.deltaMode.desc}}
`entityIds` | {{site.data.IO_items.param.entityIds.desc}}


### Examples
```xml
<providers>
    <consolidatedGamificationEventsProvider>
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
            <gamificationPoints/>
            <gamificationActionCode/>
            <gamificationAction/>
            <gamificationDateTime/>
            <locale/>
            <constantValue/>
        </columns>
        <parameters>
            <dateTimeFormat>YYYY-MM-DD hh:ii:ss</dateTimeFormat>
        </parameters>
    </consolidatedGamificationEventsProvider>
</providers>
```