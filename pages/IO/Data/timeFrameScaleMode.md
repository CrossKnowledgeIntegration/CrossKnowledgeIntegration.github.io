---
title: timeFrameScaleMode
keywords: ...
last_updated: 9th November, 2017
sidebar: home_sidebar
permalink: /data-timeframescalemode.html
folder: Data
---


{{site.data.IO_items.param.timeFrameScaleMode.desc}}

* `timeSpent` will only report on time the learner has spent learning within the specified time frame.
* `lastActivity` will report the total time the learner has spent learning if the last access date is within the specified time frame.



{% include callout.html content="**Example** when used for [Tracking provider](/tracking-provider.html)<br/><br/>
1. Hugo watched C1 in T1 on January 2<sup>nd</sup> 2015, spent 50 sec and has status = incomplete.<br/>
2. Hugo watched C1 in T1 on February 25<sup>th</sup> 2015, spent 300 sec and has status = completed.<br/>
3. Hugo watched C1 in T1 on April 5<sup>th</sup> 2015, spent 50 sec and has status = completed.<br/><br/>

The tracking report has been generated on 28<sup>th</sup> May. `timeFramesScale` was set to `n_full_months`<br/><br/>
**Scenario 1:** `timeFrames` = 1. Reporting time frame is 1<sup>st</sup> to 28<sup>th</sup> May.<br/>
Whether `lastActivity` or `timeSpent` mode is used, no data row in the report will included, because Hugo did not access the content during the reported time frame.<br/><br/>
**Scenario 2:** `timeFrames` = 2. Reporting time frame is 1<sup>st</sup> April to 28<sup>th</sup> May.<br/>
If `lastActivity` mode is used, the data in the report will show `Hugo; T1; C1; 400 sec; 100%; Completed`, because he accessed it within the specified time frame and the total time spent of the content is included.<br/>
If `timeSpent` mode is used, the data will show `Hugo; T1; C1; 50 sec; 100%; Completed`, because Hugo only spent 50 sec on the content within the specified time frame<br/><br/>
**Scenario 3:** `timeFrames` = 4. Reporting time frame is 1<sup>st</sup> February to 28<sup>th</sup> May.<br/>
If `lastActivity` mode is used, the data in the report will show `Hugo; T1; C1; 400 sec; 100%; Completed`, because same as in scenario 2 he accessed it within the specified time frame and the total time spent of the content is included.<br/>
If `timeSpent` mode is used, the data will show `Hugo; T1; C1; 350 sec; 100%; Completed`, because out of total 400 sec Hugo spent on the content, the 50 sec spent on January 2<sup>nd</sup> are outside of the specified time frame.<br/>
" type="info" %} 


```xml
<parameters>
    <timeFrames>2</timeFrames>
    <timeFramesScale>less_than_n_full_months</timeFramesScale>
	<timeFrameScaleMode>timeSpent</timeFrameScaleMode>
</parameters>
```

