---
title: Consolidated Gamification Events
keywords:
last_updated: September, 2019
tags: 
summary: ""
sidebar: home_sidebar
permalink: consolidated-gamification-events-provider.html
folder: Export
dynamic_content: true
columns: [candidateId, candidateGuid, candidateName, candidateFirstname, candidateRefNumber, candidateLogin, candidateEmail, 
    candidateEntityName, candidateCustomFieldGuid, gamificationPoints, gamificationActionCode, gamificationAction, 
    gamificationDateTime, locale, constantValue]
parameters: [dateTimeFormat, entityIds, preferredLocales, threshold, deltaMode, learnersSmartGroups, templates, stripHTML, 
    maxLength]
---

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