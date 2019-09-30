---
title: Consolidated Gamification Badges
keywords:
last_updated: September, 2019
tags: 
summary: "Export gamification badges received by learners."
sidebar: home_sidebar
permalink: consolidated-gamification-badges-provider.html
folder: Export
dynamic_content: true
columns: [candidateId, candidateGuid, candidateName, candidateFirstname, candidateRefNumber, candidateLogin, candidateEmail, 
    candidateEntityName, candidateCustomFieldGuid, badgeCode, badge, badgeCategory, badgeDateTime, locale, constantValue]
parameters: [dateTimeFormat, entityIds, preferredLocales, badgeCategory, deltaMode, learnersSmartGroups, templates, 
    stripHTML, maxLength]
---

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