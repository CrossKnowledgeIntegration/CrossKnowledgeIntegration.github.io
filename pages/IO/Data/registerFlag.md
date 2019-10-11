---
title: registerFlag
keywords: ...
last_updated: 9th November, 2017
sidebar: home_sidebar
permalink: /data-registerflag.html
folder: Data
---

{{site.data.IO_items.columns.registerFlag.desc}}

The default behaviour (when this column is not specified in the import data) is to register the learner to the session.

The default values for the `registerValue` and `unregisterValue` flags are respectively `Y` and `N`.
But it is possible to customize these values like in the example below where the `registerValue` flag is now `R`.

There is also an additional option `keepSession` (`Y`/`N`). The default behaviour of this provider, when using the `unregisterValue`, is that if the last registration is deleted in any session, then the provider will delete the session. This behaviour can be discarded by setting the option `keepSession` to `Y`.

```xml
<fields>
    <registerFlag>
        <registerValue>R</registerValue>
        <unregisterValue/>
        <keepSession>Y</keepSession>
    </registerFlag>
</fields>
```
