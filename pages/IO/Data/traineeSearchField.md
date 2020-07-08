---
title: traineeSearchField
keywords: ...
last_updated: October 2019
sidebar: home_sidebar
permalink: /data-traineesearchfield.html
folder: Data
---

{{site.data.IO_items.param.traineeSearchField.desc}}
<br/>
{% include note.html content="If several learner accounts match the chosen traineeSearchField, the oldest account will be updated." %}
<br/>
Inside a `traineeSearchField` tag, it is possible to set multiple fields at the same time, in which case the learners will be searched by all these columns jointly:

```xml
<options>
    <traineeSearchField>
        <candidateRefNumber/>
        <candidateEmail/>
        <candidateLogin/>
        <custom>SOME_GUID</custom>
    </traineeSearchField>
</options>
```
