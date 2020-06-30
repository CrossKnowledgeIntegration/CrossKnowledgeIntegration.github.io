---
title: Session Audit Metadata
keywords: session, audit, metadata, provider, export
last_updated: September, 2019
tags: 
summary: "Export the metadata of training sessions."
sidebar: home_sidebar
permalink: session-audit-metadata-provider.html
folder: Export
dynamic_content: true
important_note: This provider also allows to use all the columns from the provider <a href="training-session-metadata-provider.html">'Training Session Metadata'</a>
columns: [sessionLocale, trainingTitle, trainingDescription, trainingDuration, trainingBenefits, trainingPublisher, modality] 
parameters: [modality, trainingPathCode, sessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    timeFrames, timeFramesScale, selectedLocales, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

```xml
        <providers>
            <sessionAuditMetadataProvider>
                <columns>
                    <modality/>
                    <title/>
                    <description/>
                    <creationDate/>
                    <pathModificationDate/>
                    <modificationDate/>
                    <sessionId/>
                    <sessionGuid/>
                    <maxNbLearners/>
                    <registeredLearners/>
                    <startDate/>
                    <endDate/>
                    <trainingId/>
                    <trainingStatus/>
                    <sessionLocale/>
                    <trainingTitle/>
                    <trainingDescription/>
                    <trainingDuration/>
                    <trainingBenefits/>
                    <trainingPublisher/>
                    <templatedValue label="URL" templateId="1" />
                </columns>
                <parameters>
                    <selectedLocales>fr-FR,en-GB</selectedLocales>
                    <templates>
                        <template id="1">/sessions/trainingsession_record.php?trainingsession_id={6}</template>
                    </templates>
                    <stripHTML/>
                    <maxLength>10</maxLength>
                </parameters>
            </sessionAuditMetadataProvider>
        </providers>
```
