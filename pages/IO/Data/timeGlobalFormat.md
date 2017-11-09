---
title: timeGlobalFormat
keywords: ...
last_updated: 16 June, 2017
tags: 
sidebar: home_sidebar
permalink: /data-timeglobalformat.html
folder: Data
---


This parameter determines the format of the in which the "total time spent" on a specific learning object should be exported by the provider. It accepts the following values (example shows how 1 hour 25 minutes 15 seconds would be shown):

Type | Example | Description
--- | --- | ---
`iso-8601`|`PT1H25M15S`| More information can be found [here](https://en.wikipedia.org/wiki/ISO_8601) 
`rawSeconds`|`5115`|Represents the "total time spent" in seconds. This will be used by **default** if no format is specified.
`rawMinutes`|`85.25`|Represents the "total time spent" in minutes, with 2 digits after the decimal point.
`padded`|`001:25`|Represents the "total time spent" in the hhh:ii (hhh = hours, padded to the left with 0's until it has 3 digits, ii = minutes, padded to the left with 0's until it has 2 digits) format.
`paddedhh`|`01:25`|Represents the "total time spent" in the hh:ii (hhh = hours, padded to the left with 0's until it has 2 digits, ii = minutes, padded to the left with 0's until it has 2 digits) format.

```xml
<parameters>
	<timeGlobalFormat>rawSeconds</timeGlobalFormat>
</parameters>
```