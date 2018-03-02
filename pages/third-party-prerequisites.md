---
title: Third Party Content Prerequisites
keywords: pre-requisites, prerequisites, requirements
last_updated: 9 November, 2017
sidebar: home_sidebar
permalink: third-party-prerequisites.html
folder: prerequisites
---


## Introduction

### Purpose of this article

This article presents a set of prerequisites and constraints to respect when creating a new training content. It will ensure a proper implementation of CrossKnowledge technology.

It also offers a set of best practices to minimize problems during integration phases.

### Glossary

LMS | Learning Management System. Software to administrate and provide trainings and training contents. Also referred to as elearning platform.
SCORM 1.2 and 2004 | Sharable Content Object Reference Model. This is the standard regarding content creation model. SCORM defines the structure of all interfaces: how the LMS launches the content, how information are sent back to the LMS, content description...
AICC | Acronym for Aviation Industry CBT Committee. 
SCO | Shareable Content Object. SCO is the SCORM term for a unit activity. It's the most precise hierarchical level of content files in a Scorm package.

## Prerequisites and constraints

### Workstation minimum requirements

Please ensure yourself to have the minimum CKLS Prerequisites requirement to run the contents smoothly

Any new content creation from a third party provider should not override those workstation constraints of the CKLS.

Beware of Flash Player versions, newest contents are often developed on recent technologies which are not fully compatible with "older" user workstations.

Here is the list of file types the Crossknowledge LMS forbids for the creation of learning objects : htaccess, php* (php, php1, php4, php564...), phps, phtm, .phtml, pl, py, cgi, exe, sh.

### File extensions not allowed in your contents 

For security reasons, any SCORM packages to be integrated in the platform must not contain files with following extensions :

-'htaccess'
-'php'
-'phps'
-'phtm'
-'phtml'
-'pl'
-'py'
-'cgi'
-'exe'
-'sh'

Basically all the code that is server-side code extensions

### Network constraints

To ensure good fluidity while playing contents, contents should meet the following constraints:

Maximum size of content: 50 MB
Resolution, encoding and quality of the videos must be compatible with Web standards. In other words, the content should not require installation of plugin to be played.

### Delivery and format constraints

CrossKnowledge LMS is compliant with the following standards:

- SCORM 1.2
- SCORM 2004
- AICC

And CrossKnowledge Learning Suite is able to upload those kind of documents:

- SCORM 1.2 (zip)
- SCORM 2004 (zip)
- AICC (zip)
- Video format (FLV, MP4)
- Url format (Youtube, Slideshare...)
- Downloadable PDF Documents
- Downloadable Office Documents
- Downloadable Image format (JPG, GIF)
- Downloadable Sound format (MP3)

The product is certified by ADL on Scorm 1.2 compliance. We strongly recommend to use mono-SCO and Scorm 1.2 as a delivery format. The delivery format is a zip archive, please be careful to have the manifest files (Scorm) or crs (AICC) properly to the root of those archives.

Any content delivery should be delivered with an appendix document containing the following metadata of content:

- Title
- Author
- Description
- Theoretical duration
- Level of difficulty (1/2/3)
- Learning goals for the content
- Picture + resolution 640 x 360 px

Each delivery will be tested on a dedicated test platform before being uploaded on the production platform. In terms of tracking, the content will have to sent back the following information to Crossknowledge LMS:

- Score
- Time spent
- Status (incomplete/completed)
- Location (bookmarking of the learner back of the slide on which he stopped)

For multilingual content, one package per language will be issued. The Crossknowledge "Training On Demand" solution is managing localization and content versioning.

### Scorm 1.2 and Scorm 2004

In Scorm 1.2, progress does not exist, so the score field is often diverted from its original design to save the progress of the learner within the content. You will have something like this while advancing through slides (13%, 22%, 75%...).

When creating a Scorm 1.2 content, you will have the choice to save a quizz score or progress in the score field. This should be defined with your content provider as soon as possible. In the Crossknowledge LMS, the visual progress bar moves relative to the status of learner regarding the content.

- 0% => Not attempted
- 50% => Incomplete
- 100% => Completed
If you want to convert the score to a progress in order to have a precise progress bar for the learner (13%, 22%, 75% as CrossKnowledge contents), CrossKnowledge has developed a feature to permit it in Training on Demand.

In Scorm 2004, the progress notion is introduced in addition to the score one. A content created on this format will be able to sent back score and progress through the cmi.progress_measure field for the LMS hosting it.

Moreover, our LMS does not interprete with Scorm 2004 navigation and sequencing commands (adl.nav.request). This will create an error. For a multi-chapter (multisco) content, a menu will appear on the left of the content to navigate between chapters. This chapters (sco) needs to be well defined in the imsmanifest.xml.

### Good practices

The content duration must not exceed half an hour.

If the course is longer, it should be divided into several zip packages (mono-SCO).

As the contents will be imported in a Crossknowledge learning path , this is not an issue.

CrossKnowledge recommends to develop training contents or modules in SCORM 1.2, this standard is supported by the majority of elearning content creation tools and all the LMS.

CrossKnowledge recommends to ask the content provider to call the function LMS.Commit("") after each slide or action in the learning content. This action will regularly back up datas in the LMS and will prevent any unsaved datas if the learner has a connection loss.

CrossKnowledge recommends to use JavaScript function onbeforeunload and unonload to terminate and LMS.Finish("") the communication with our Scorm API.

Finally on screen resolutions, Crossknowledge recommends resolutions contained less than 858x575 px with a full screen button in the content.

### Content mass upload

It is possible too to upload your scorm / aicc / url / mp4 packages in bulk through the SFTP access of your platform.
To do so :
- File name will need to be a code that will be used in your metadata file. eg. VODE100.zip, TMEL318.mp4, XEIL678.pdf
- For multilingual content, one package per language will be issued. Each content will be inside a folder named with the language.

### Metadata format

Content delivery should be linked with metadata file described below. The format should be a CSV flat file with comma delimeter encoded in UTF-8 w-out BOM. Column name is required.

Column name | Description
--- | ---
`courseid` | Content code
`locale` | Content language (eg. fr-FR, en-GB, pt-BR)
`title` | Content title
`description` | Content description
`duration` | Content duration
`authorid` | Content author id - Author needs to be created first in client LMS
`keywords` | Content tags or keywords separated by pipe (eg. Word "Pipe" Management)
`level` | Content difficulty (1, 2 or 3)
`objectives` | Content purpose/objective (text)
`detailedcontent` | Content description details
`targetaudience` | Content target audience
`thumbnail` | 	Content url to thumbnails (Max. 200.0 MB, Size: 640x360px)
`url` | 	Content url, if content is weblink
`runtime` | Content runtime (eg.youtube_learning_object_guid,aicc_learning_object_guid,automatic_text,E,file_lo_guid,zip_lo_guid,flash_learning_object_guid,
link_lo_guid,SCORM,slideshare_lo_guid,telelangue_learning_object_guid,video_learning_object_guid)
`type` | Content type (eg. Video, Interactive, Reading, Questionnaire, Website, Audio, work to Submit, in Class assessment, Picture, Doc to download)
`scoreisprogress` | Content scorm option to save progress score variable (value = Y)
`themes` | Content themes (eg. Theme1>Subtheme1 "Pipe" Theme2)

### Testing your Scorm packages

Please contact your system integration consultant to open you a sandbox in order to test your contents
