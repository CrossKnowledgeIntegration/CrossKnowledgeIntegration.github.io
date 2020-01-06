---
title: Platform Candidates Access
keywords: candidates, learners, export, data, report
last_updated: 22 August, 2017
tags:
summary: "Export the learners connection history"
sidebar: home_sidebar
permalink: candidates-access-provider.html
folder: Export
dynamic_content: true
columns: [candidateId, candidateLogin, candidateName, candidateFirstname, candidateEmail, candidateRefNumber, candidateGuid, 
    candidateTimeZone, candidateEntityName, candidateEntityAncestors, candidateCustomFieldGuid, status, platformAccessDate]
parameters: [dateFormat, dateTimeFormat, ancestorsWithCurrent, timeFrames, timeFramesScale, failedConnections, 
    connectionStatusFormat, entityIds, learnersSmartGroups, templates, stripHTML, maxLength]
---

### Example
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
            <candidateCustomFieldGuid/>
            <candidatePresentation/>
            <platformaccessdate/>
            <status/>
            <constantValue/>
        </columns>
        <parameters>
            <entityIds>1,32</entityIds>
            <dateFormat>MM-DD-YYYY</dateFormat>
            <connectionStatusFormat>
				<success>S</success>
				<failure>F</failure>
			</connectionStatusFormat>
        </parameters>
    </platformCandidatesAccessProvider>
</providers>
```