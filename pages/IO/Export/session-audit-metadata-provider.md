---
title: Session Audit Metadata
keywords: session, audit, metadata, provider, export
last_updated: 21 March, 2018
tags: 
summary: ""
sidebar: home_sidebar
permalink: session-audit-metadata-provider.html
folder: Export
---

### Available columns

Name | Description
---|---
`trainingId` | {{site.data.IO_items.col.trainingId.desc}}
`trainingStatus` | {{site.data.IO_items.col.trainingStatus.desc}}
`trainingTitle` | {{site.data.IO_items.col.trainingTitle.desc}}
`trainingDescription` | {{site.data.IO_items.col.trainingDescription.desc}}
`trainingDuration` | {{site.data.IO_items.col.trainingDuration.desc}}
`trainingBenefits` | {{site.data.IO_items.col.trainingBenefits.desc}}
`trainingPublisher` | {{site.data.IO_items.col.trainingPublisher.desc}}
`sessionId` | {{site.data.IO_items.col.sessionId.desc}}
`sessionGuid` | {{site.data.IO_items.col.sessionGuid.desc}}
`sessionLocale` | {{site.data.IO_items.col.sessionLocale.desc}}
`modality` | {{site.data.IO_items.col.modality.desc}}
`title` | {{site.data.IO_items.col.title.desc}}
`description` | {{site.data.IO_items.col.description.desc}}
`startDate` | {{site.data.IO_items.col.startDate.desc}}
`endDate` | {{site.data.IO_items.col.endDate.desc}}
`creationDate` | {{site.data.IO_items.col.creationDate.desc}}
`pathModificationDate` | {{site.data.IO_items.col.pathModificationDate.desc}}
`modificationDate` | {{site.data.IO_items.col.modificationDate.desc}}
`registeredLearners` | {{site.data.IO_items.col.registeredLearners.desc}}
`maxNbLearners` | {{site.data.IO_items.col.maxNbLearners.desc}}
`constantValue` | {{site.data.IO_items.col.constantValue.desc}}

### Filters and parameters

Name | Description
---|---
`selectedLocales` | {{site.data.IO_items.param.selectedLocales.desc}}
`stripHTML` | {{site.data.IO_items.param.stripHTML.desc}}
`maxLength` | {{site.data.IO_items.param.maxLength.desc}}

### Examples
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
