---
title: sessionSearchField
keywords: ...
last_updated: October 2019
sidebar: home_sidebar
permalink: /data-sessionsearchfield.html
folder: Data
---

{{site.data.IO_items.param.sessionSearchField.desc}}

Inside a `sessionSearchField` tag, it is possible to set multiple fields at the same time, in which case the sessions will be searched by all these columns jointly:

```xml
<options>
    <sessionSearchField>
        <sessionGuid/>
        <sessionTitle/>
        <sessionId/>
        <sessionStartDate/>
        <sessionEndDate/>
    </sessionSearchField>
</options>
```
