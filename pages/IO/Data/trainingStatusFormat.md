---
title: trainingStatusFormat
keywords: ...
last_updated: June 2019
sidebar: home_sidebar
permalink: /data-trainingstatusformat.html
folder: Data
---

By default, the training status will be exported using the following values:
 
 * C for 'under construction'
 * P for 'published'
 * A for 'archived'
 
These values can be overriden with custom texts like in this example:

```xml
<trainingStatusFormat>
    <archived>Disabled</archived>
    <published>Published</published>
    <underConstruction>Pending validation</underConstruction>
</trainingStatusFormat>
```

