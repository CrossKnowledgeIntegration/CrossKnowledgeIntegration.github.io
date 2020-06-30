---
title: trainingSearchField
keywords: ...
last_updated: October 2019
sidebar: home_sidebar
permalink: /data-trainingsearchfield.html
folder: Data
---

{{site.data.IO_items.param.trainingSearchField.desc}}

Inside a `trainingSearchField` tag, it is possible to set multiple fields at the same time, in which case the training courses will be searched by all these columns jointly:

```xml
<options>
    <trainingSearchField>
        <trainingPathCode/>
        <trainingId/>
    </trainingSearchField>
</options>
```
