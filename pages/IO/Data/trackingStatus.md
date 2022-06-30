---
title: trackingStatus
keywords: ...
last_updated: October 2019
sidebar: home_sidebar
permalink: /data-trackingstatus.html
folder: Data
---

{{site.data.IO_items.col.trackingStatus.desc}}

Configure mapping values for importing the tracking's completion status.

By using the example below, to import `completed` tracking, you will use the value `c` in the csv file. And to import `incomplete` tracking, you will need to use the full value `incomplete` in the csv file, as the mapping for this value has not been specified.

The status `notAttempted` has a specific behaviour, as it will not import any data but on the contrary, it will completely delete/reset the tracking row.

```xml
<parameters>
    <trackingStatus>
        <notAttempted>n</notAttempted>
        <incomplete/>
        <completed>c</completed>
        <passed/>
        <failed/>
        <browsed/>
    </trackingStatus>
</parameters>
```
