---
title: Platform Candidates
keywords: candidates, learners, export, data, report
last_updated: September, 2019
tags:
summary: "Export learners"
sidebar: home_sidebar
permalink: candidates-provider.html
folder: Export
dynamic_content: true
columns: [candidateId, candidateLogin, candidateName, candidateFirstname, candidateEmail, candidateRefNumber, candidateGuid, 
    managerLogin, candidateCustomFieldGuid, candidateTimeZone, 
    candidatePresentation, candidateFollowWeb, candidateFollowTwitter, candidateFollowLinkedin, candidateLocale, 
    candidateLocales, candidateAccountActivated, candidateAccountActivatedFrom, candidateAccountActivatedUntil, 
    lastPlatformAccessDate, creationDate, candidatePoints, candidateBadges, constantValue, candidateEntityName, 
    candidateEntityId, candidateSmartgroups, candidateEntityAncestors]
parameters: [ancestorsWithCurrent, timeFrames, timeFramesScale, entityIds, learnersSmartGroups, templates, stripHTML, 
    maxLength, dateFormat, dateTimeFormat]
---

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
                <candidateCustomFieldGuid label="Department">8345C0A3-B8AB-7F65-0638-39B0E1244AA8</candidateCustomFieldGuid>
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
        </moveToFolder>
    </consolidators>
</export>           
```
