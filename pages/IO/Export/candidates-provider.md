---
title: Platform Candidates
keywords: candidates, learners, export, data, report
last_updated: 22 August, 2017
tags:
summary: ""
sidebar: home_sidebar
permalink: candidates-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`candidateId` | {{site.data.IO_items.col.candidateId.desc}}
`candidateLogin` | {{site.data.IO_items.col.candidateLogin.desc}}
`candidateName` | {{site.data.IO_items.col.candidateName.desc}}
`candidateFirstname` | {{site.data.IO_items.col.candidateFirstname.desc}}
`candidateEmail` | {{site.data.IO_items.col.candidateEmail.desc}}
`candidateRefNumber` | {{site.data.IO_items.col.candidateRefNumber.desc}}
`candidateGuid` | {{site.data.IO_items.col.candidateGuid.desc}}
`managerLogin` | {{site.data.IO_items.col.managerLogin.desc}}
`candidateGroupAncestors` | {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`candidateGroupId` | {{site.data.IO_items.col.candidateGroupId.desc}}
`candidateCustomFieldGuid` | {{site.data.IO_items.col.candidateCustomFieldGuid.desc}}
`candidateTimeZone` | {{site.data.IO_items.col.candidateTimeZone.desc}}
`candidatePresentation` | {{site.data.IO_items.col.candidatePresentation.desc}}
`candidateFollowWeb` | {{site.data.IO_items.col.candidateFollowWeb.desc}}
`candidateFollowTwitter` | {{site.data.IO_items.col.candidateFollowTwitter.desc}}
`candidateFollowLinkedin` | {{site.data.IO_items.col.candidateFollowLinkedin.desc}}
`candidateLocale` | {{site.data.IO_items.col.candidateLocale.desc}}
`candidateLocales` | {{site.data.IO_items.col.candidateLocales.desc}}
`candidateAccountActivated` | {{site.data.IO_items.col.candidateAccountActivated.desc}}
`candidateAccountActivatedFrom` | {{site.data.IO_items.col.candidateAccountActivatedFrom.desc}}
`candidateAccountActivatedUntil` | {{site.data.IO_items.col.candidateAccountActivatedUntil.desc}}
`candidateGroupAncestors` | {{site.data.IO_items.col.candidateGroupAncestors.desc}}
`lastPlatformAccessDate` | {{site.data.IO_items.col.lastPlatformAccessDate.desc}}
`creationDate` | {{site.data.IO_items.col.creationDate.desc}}
`candidatePoints` | {{site.data.IO_items.col.candidatePoints.desc}}
`candidateBadges` | {{site.data.IO_items.col.candidateBadges.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`ancestorsWithCurrent` | {{site.data.IO_items.param.ancestorsWithCurrent.desc}}
`groupIds` | {{site.data.IO_items.param.groupIds.desc}}
`timeFrames` | {{site.data.IO_items.param.timeFrames.desc}}
`timeFramesScale` | {{site.data.IO_items.param.timeFramesScale.desc}}


### Examples
```xml
<export>
    <providers>
        <platformCandidatesProvider>
            <columns>
                <candidateId/>
                <candidateLogin/>
                <candidateName/>
                <candidateFirstname/>
                <candidateEmail/>
                <candidateRefNumber/>
                <candidateGuid/>
                <managerLogin/>
                <candidateGroupAncestors/>
                <candidateGroupId/>
                <candidateCustomFieldGuid/>
                <candidateTimeZone/>
                <candidatePresentation/>
                <candidateFollowWeb/>
                <candidateFollowTwitter/>
                <candidateFollowLinkedin/>
                <candidateLocale/>
                <candidateLocales/>
                <candidateAccountActivated/>
                <candidateAccountActivatedFrom/>
                <candidateAccountActivatedUntil/>
                <candidateGroupAncestors/>
                <lastPlatformAccessDate/>
                <creationDate/>
                <candidatePoints/>
                <candidateBadges/>
            </columns>
        </platformCandidatesProvider>
    </providers>
    <actions>
        <fileExportAction>
            <format>CSV</format>
            <encoding>UTF-8</encoding>
            <delimiter>semicolon</delimiter>
            <showHeaders>yes</showHeaders>
        </fileExportAction>
    </actions>
    <consolidators>
        <moveToFolder>
            <fileName>Platform_Candidates.csv</fileName>
    </consolidators>
</export>           
```