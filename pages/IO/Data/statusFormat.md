---
title: statusFormat
keywords: ...
last_updated: June 2019
sidebar: home_sidebar
permalink: /data-statusformat.html
folder: Data
---

By default, the tracking status will be exported using the following values:
 
 * 'completed' for 'completed'
 * 'incomplete' for 'incomplete'
 * 'not attempted' for 'notAttempted'
 
These values can be overriden with custom texts like in this example:

```xml
<statusFormat>
    <incomplete>I</incomplete>
    <notAttempted>N/A</notAttempted>
    <completed>C</completed>
</statusFormat>
```

