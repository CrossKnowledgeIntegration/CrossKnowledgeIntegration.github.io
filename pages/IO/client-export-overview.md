---
title: Export glossary
keywords: ...
last_updated: March 11, 2020
tags:
sidebar: home_sidebar
permalink: export-glossary.html
folder: IO
---

## Our exports

In this page you will have an overview about all export files available on our platform. And in each menu item you will be redirect to the specific export page, with detailed information and sample files.

If you have any doubts, please send an email to: [integration@crossknowledge.com](mailto:integration@crossknowledge.com) and we will answer you as soon as possible 😄

### Available exports

 - **Tracking exports**
	- [Consolidated tracking](https://developers.crossknowledge.com/consolidated-tracking-provider.html) - Learners tracking summarized by session
    - [Activity](https://developers.crossknowledge.com/activity-provider.html) - Detailed learner tracking data in Blendedx activities and Blendedx learning resources
    - [Tracking](https://developers.crossknowledge.com/tracking-provider.html) - Detailed learner tracking data only in learning resources
    - [Class Based Training (CBT)](https://developers.crossknowledge.com/class-based-training-provider.html) - Detailed learner tracking data only in classroom activities
    - [Tracking log](https://developers.crossknowledge.com/training-log-provider.html)​​​​​​​ - Each learner's action per content. Available for Blendedx and Learning Channel training types
-   **Audit exports**
    - [Training audit](https://developers.crossknowledge.com/training-audit-metadata-provider.html) - Detailed training data
    - [Session audit](https://developers.crossknowledge.com/session-audit-metadata-provider.html) - Training data related to the specified session
    - [Content audit](https://developers.crossknowledge.com/training-audit-content-provider.html) - Content data related to the specified training
-   **Training and session exports**
    - [Training metadata](https://developers.crossknowledge.com/training-course-metadata-provider.html) - Important training data
    - [Session metadata](https://developers.crossknowledge.com/training-session-metadata-provider.html) - Detailed session data
-   **Learning object exports**
    - [Learning Object](https://developers.crossknowledge.com/lo-metadata-provider.html) - Detailed learning object data
    - [Learning Object Version (LOV)](https://developers.crossknowledge.com/lov-metadata-provider.html) - Detailed learning object version data
-   **Learners exports**
    - [Learner metadata](https://developers.crossknowledge.com/candidates-provider.html) - 
    - [Learner connection history](https://developers.crossknowledge.com/candidates-access-provider.html) - 
-   **Events exports**
    - [Learners in classroom events](https://developers.crossknowledge.com/event-learner-metadata-provider.html) - 
    - [Blendedx sessions classroom events](https://developers.crossknowledge.com/event-session-metadata-provider.html) - 
    - [Blendedx training classroom events](https://developers.crossknowledge.com/event-training-metadata-provider.html) - 
-   **Gamification exports**
    - [Gamification badges](https://developers.crossknowledge.com/consolidated-gamification-badges-provider.html) - 
    - [Gamification events (Learner's points)](https://developers.crossknowledge.com/consolidated-gamification-events-provider.html) - 

## What is the difference between all these tracking exports?

It is normal to misunderstood the differences between the tracking exports. If it is your case, we hope this section can help you!

A good way to think in these exports is in a pyramid form. As if the Tracking Log was the most detailed ("low level") and the Consolidated Tracking the most consolidated ("high level") export.

![Pyramid of tracking export](/images/Charts.png "Pyramid of tracking exports")

### Ok, but what does it mean?

All data you can have with Activity, Tracking, Class Based Training and Consolidated Tracking can be obtained with Tracking Log. Tracking log will be the most detailed information. And, if you want to group this informations for each learner in different levels, you can obtain the same result that you will have with others Tracking exports. Like a puzzle game!

But if you won't do that, we can provide you different visions of that data with our other Tracking exports. Sounds good? 😉

<!-- Partindo da base da pirâmide, os relatórios que vem acima irão utilizar os dados do relatório abaixo como base para formar a visualização desses dados em diferentes níveis (mais consolidados). Ou seja, os dados apresentados no Tracking log, serão consolidados para apresentar a visão de tracking de conteúdo nos relatórios acima (Tracking, Class Based Training, Activity). Os dados de Activity serão formados pelos dados consolidados do Tracking log e os dados que você obtiver em Tracking e CBT também estarão presentes em Activity. E por fim o Consolidated Tracking será formado pelos dados dos relatórios abaixo dele, porém consolidado para uma visão de nível de sessão. -->

* **Tracking log** will have each action that the learner did in a content. It is most used in audit situations, when a really detailed level is required. It is available for **Self-directed learning** training (as Learning Channel) and **Guided learning** training (as Blendedx). 
> Example: *"**Julie** accessed the Content A in Session 01 in Training 02 at 2020-15-03 and spent 00:00:30 seconds on it. She gained 0 points and the status is Incomplete on this registration. 
Also, **Julie** accessed the Content A in Session 01 in Training 02 at 2020-22-03 and spent 00:15:20 minutes on it. She gained 10 points and the status is Completed on this registration."*

* **Tracking** will consolidate only data related to Learning Resources in a content level. It is available for **Self-directed learning** training (as Learning Channel) and **Guided learning** training (as Blendedx). 
> Example: *"**Julie** accessed the Content A in Session 01 in Training 02 for the first time at 2020-15-03 and the last time at 2020-22-03. She spent 00:15:50 minutes on it. She gained 10 points and the Content status is Completed."*

* **Class Based Training (CBT)** will consolidate only data related to Classroom activity in a content level. It is available only for **Blendedx** training. It is most used when the client needs to have the report of face-to-face events registered at the platform. 
> Example: *"**Michael** has been attended the event Class ABC, registered in Session 02 in Training 02, that started at 2020-18-03 at 12:30:00 p.m and finished at 2020-19-03 at 06:00:00 p.m. He gained 30 points on this activity. This event occurred at London office, in Blue room, and the facilitator was Sophie Durand."*

* **Activity** will consolidate only data related to Blendedx activities (including Classroom activity) and some Learning Resources in a content level. It is most used when the client has **Blendedx** trainings and wants to know how each learner are doing. So, this report will have the same data that CBT report has and also some data (only when it is related to Blendedx training) that Tracking report has. On this report is possible to have the **NPS** rate that each learner assigned to the session.
> Example: *"**Julie** accessed the Content A in Session 01 in Training 02 for the first time at 2020-15-03 and last time at 2020-22-03. She spent 00:15:50 minutes on it. She gained 10 points and the Content status is Completed. She gave the score 07 to this session.
Also, **Michael** has been attended the event Class ABC, which started at 2020-18-03 and finished at 2020-19-03. He spent 11:30:00 hours on it. He gained 30 points and the Activity status is Completed. He gave the score 10 to this session."* 

* **Consolidated tracking** will consolidate all Activities and Learning Resouces in a session level. It is available for **Self-directed learning** training (as Learning Channel) and **Guided learning** training (as Blendedx). It is most used when the client wants to know how is the learner progress in some session/training. It is a high-level data (not so detailed as the other reports).
> Example: *"**Julie** did Session 01 in Training 02. Her first access was 2020-15-03 and the last access was at 2020-22-03. This session is incompleted yet. For now she spent 00:15:50 minutes on it and gained 10 points.
Also **Michael** did the Session 02 in Training 02. His first access was 2020-16-03 and the last access was 2020-22-03. This session is completed and he gained 50 points. He spent 15:00:00 hours on it.
"*


 

