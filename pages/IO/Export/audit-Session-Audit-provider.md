---
title: Audit - Session Audit
keywords: training, session, audit, metadata, provider, export, detailed, session data
last_updated: September, 2019
tags: 
summary: "The session audit export will contain some training data related to the specified session."
sidebar: home_sidebar
permalink: session-audit-metadata-provider.html
folder: Export
export_content: true
description: >
    <br/>
    It is available for <b>sessions</b> related to <b>Blendedx and Learning Channel trainings</b>. It can be helpful when you need to map which sessions are available in a training. It will contain some informations about the trainings related to the sessions (as title, modality, description).
    <br/><br/>

    If you want to have only the session data, please take a look at <a href="training-session-metadata-provider.html">Session metadata export</a>.
    <br/><br/>

    <u>Example:</u> 
        <li>
        <i> 
            The <b>Module A</b> session created on <b>2020-06-15</b> is available in the <b>"Welcome aboard" Blendedx</b> training.
        </li>
        <li>
            The <b>Module B</b> session created on <b>2020-07-01</b> is also available in the <b>"Welcome aboard" Blendedx</b> training.
        </li>
        </i>
    <br/>

    To check an <b>export sample file</b>, <a href="https://">click here</a>.
    <br/>
columns: [sessionLocale, trainingTitle, trainingDescription, trainingDuration, trainingBenefits, trainingPublisher, modality] 
parameters: [modality, trainingPathCode, completeSessionTitle, trainingTitle, sessionGuid, trainingGuid, dateFormat, dateTimeFormat, 
    lastNMonths, lastNFullMonths, trainingStatus, deltaMode, onlyFromImportedTraining, trainingStatusFormat, exportAllSessions, 
    sessionTimeFrames, sessionTimeFramesScale, sessionSelectedLocales, templates, stripHTML, maxLength, onlyHrisSelectedItems]
---

## Session Audit

It is available for **sessions related to Blendedx and Learning Channel trainings**. It can be helpful when you need to map which sessions are available in a training. It will contain some informations about the trainings related to the sessions (as title, modality, description).

If you want to have only the session data, please take a look at [Session metadata export](htttp://localhost:4000/training-session-metadata-provider.html).

> Example: _The **Module A** session created at **2020-06-15** is available in the **"Welcome aboard" Blendedx** training.
The **Module B** session created at **2020-07-01** is also available in the **"Welcome aboard" Blendedx** training._

To check an **export sample file**, [click here](https://).

<!--
```xml
        <providerss>
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
        </providerss>
```
-->
