---
title: Candidates Access
keywords: candidates, learners, export, data, report
last_updated: 22 August, 2017
tags:
summary: ""
sidebar: home_sidebar
permalink: candidates-access-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`candidateTimeZone` | {{site.data.IO_items.col.candidateTimeZone.desc}}
`candidateGroupAncestors` | {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`candidateGroupName` | {{site.data.IO_items.col.candidateGroupName.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`candidatePresentation` | {{site.data.IO_items.col.candidatePresentation.desc}}
`platformaccessdate` | {{site.data.IO_items.col.platformaccessdate.desc}}
`status` | {{site.data.IO_items.col.status.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}


### Filters and parameters

Name | Description
---|---
`dateFormat` | {{site.data.IO_items.param.dateFormat.desc}}
`dateTimeFormat` | {{site.data.IO_items.param.dateTimeFormat.desc}}
`groupIds` | {{site.data.IO_items.param.groupIds.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}
`failedConnections` | {{site.data.IO_items.param.failedConnections.desc}}
`connectionStatusFormat` | {{site.data.IO_items.param.connectionStatusFormat.desc}}



### Examples
```xml
<providers>
    <platformCandidatesAccessProvider>
        <columns>
            <candidateId/>
            <candidateName/>
            <candidateFirstname/>
            <candidateLogin/>
            <candidateEmail/>
            <candidateRefNumber/>
            <candidateGuid/>
            <candidateTimeZone/>
            <candidateGroupAncestors/>
            <candidateGroupName/>
            <candidateCustomFieldGuid/>
            <candidatePresentation/>
            <platformaccessdate/>
            <status/>
            <constantValue/>
        </columns>
        <parameters>
            <groupIds>1,32</groupIds>
            <dateFormat>MM-DD-YYYY</dateFormat>
        </parameters>
    </platformCandidatesAccessProvider>
</providers>
```