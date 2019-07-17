---
title: templates
keywords: ...
last_updated: July 2019
sidebar: home_sidebar
permalink: /data-templates.html
folder: Data
---

{{site.data.IO_items.param.templates.desc}}

This option requires the combined use of a column 'templatedValue' and a 'template' parameter.  The attribute 'templateId' of a 'templatedValue' must match the attribute 'id' of a 'template', as in the example below.

### Full example

```xml
<providers>
    <trackingProvider>
		<columns>
			<candidateId/>
			<candidateName/>
			<candidateFirstname/>
			<trainingId/>
			<sessionId/>
			<contentGuid/>
			<firstLaunchDate/>
			<completionTime/>
			<score/>
			<timeGlobal/>
			<progression/>
			<status/>
            <templatedValue label="URL" templateId="1" />
            <templatedValue label="Learner fullname" templateId="2" />
		</columns>
        <parameters>
            <dateFormat>MM-DD-YYYY</dateFormat>
            <templates>
                <template id="1">https://instanceurl.ck.com/sso/content/{5}/</template>
                <template id="2">{2} {1}</template>
            </templates>
        </parameters>
    </trackingProvider>
</providers>
```

