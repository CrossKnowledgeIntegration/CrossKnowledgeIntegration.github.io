---
title: connectionStatusFormat
keywords: ...
last_updated: June 2019
sidebar: home_sidebar
permalink: /data-connectionstatusformat.html
folder: Data
---

By default, the connection status will be exported using the following values:
 
 * 1 for 'success'
 * 0 for 'failure'
 
These values can be overriden with custom texts like in this example:

```xml
<connectionStatusFormat>
    <success>S</success>
    <failure>F</failure>
</connectionStatusFormat>
```

