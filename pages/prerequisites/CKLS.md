---
title: CKLS Technical Prerequisites
keywords: pre-requisites, prerequisites, requirements
last_updated: 9 November, 2017
sidebar: home_sidebar
permalink: CKLS-prerequisites.html
folder: prerequisites
---


## Workstation requirements

CrossKnowledge LMS is a web-based application needing the following environment to run properly:

<table>
    <tbody>
        <tr>
            <td>Sound card</td>
            <td>Activated (headphones are required for most content)</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>2 GB (4GB prefered, depending on the OS)</td>
        </tr>
        <tr>
            <td>Screen resolution</td>
            <td>1024*768</td>
        </tr>
        <tr>
            <td>Windows operating system</td>
            <td>Windows Vista, 7, 8, 10 (Desktop mode only, Tablet mode is not supported for now)</td>
        </tr>
        <tr>
            <td>Apple operating system</td>
            <td>Mac OSX (10.4)</td>
        </tr>
        <tr>
            <td>Internet Explorer</td>
            <td>8, 9, 10, 11, latest version</td>
        </tr>
        <tr>
            <td>Microsoft Edge</td>
            <td>latest version</td>
        </tr>
        <tr>
            <td>Firefox</td>
            <td>latest version</td>
        </tr>
        <tr>
            <td>Chrome</td>
            <td>latest version</td>
        </tr>
        <tr>
            <td>Safari</td>
            <td>latest version</td>
        </tr>
        <tr>
            <td>Opera</td>
            <td>latest version</td>
        </tr>
        <tr>
            <td>Tested email readers</td>
            <td>Outlook 2010, Outlook 2013, Lotus Notes 8.5, Gmail, Outlook 365</td>
        </tr>
        <tr>
            <td>HTTPS</td>
            <td>Only "Medium and High" ciphers are allowed (HIGH:MEDIUM:!ADH). TLSv1.x protocols are supported.</td>
        </tr>
        <tr>
            <td>Popup blocker for your URL</td>
            <td>Disabled</td>
        </tr>
    </tbody>
</table>

We systematically test the latest versions of Chrome, Firefox and Internet Explorer browsers to ensure the best experience for our users. Older versions of these browsers are not systematically tested, but run smoothly in most cases. If, however, there is a problem specific to a particular version of one of these browsers, please contact us.

### Tablet compatibility

CrossKnowledge LMS is compatible with iPad (2, 3, 4 and mini) - additional requirements may be needed for the content hosted on the LMS.

CrossKnowledge LMS is compatible with Android tablets (Chrome browser) - additional requirements may be needed for the content hosted on the LMS. 

### CrossKnowledge content additional requirements

As the contents are played on our LMS, you need the LMS requirements listed above, and the following ones:
 	
<table width="100%">
    <tbody>
        <tr>
            <td width="30%">Adobe Flash Player (CrossKnowledge Sessions)</td>
            <td width="70%">9.0.124 or higher</td>
        </tr>
        <tr>
            <td width="30%">PDF plugin</td>
            <td width="70%">Adobe Acrobat Reader (any version)</td>
        </tr>
    </tbody>
</table>

## Network Information

### Media extensions
The following media extensions should be authorised.<br/>
`.FLV, .mp3, .mp4, .srt, .woff, .vtt, .xhtml`

### Domain white-listing
The following domain names should be whitelisted.
```txt
http(s)://*.crossknowledge.com, http(s)://*.crossknowledge-player.com
```

If wildcards (*) are not allowed, authorise at least the following URLs:<br/>
#### General CKLS cloudfront URLs:

```txt
https://ckls-assets.crossknowledge.com/
https://ckls-api.crossknowledge.com/
https://ckls-cdn-eu.crossknowledge.com/
```

#### External medias (cloudfront URL)
```txt
https://d3d8qnlcu0b7xk.cloudfront.net
https://media-cdn2.crossknowledge.com
```

#### CK-Player URLs (for CrossKnowledge content delivery)

##### For users based in Europe
```txt
http(s)://cdn.crossknowledge.com/*
http(s)://d12yhdsdwe7din.cloudfront.net/* or http(s)://mohivecontents-eu.crossknowledge.com
```

##### For users based in the US:
```txt
rtmp://s11glde2jwx3y7.cloudfront.net/*
http(s)://d2niiguqm1v5wm.cloudfront.net/* or http(s)://ckcontents-na.crossknowledge.com
http(s)://dmi776hgmgo8n.cloudfront.net/* or http(s)://mohivecontents-na.crossknowledge.com
```

##### For users based in Asia:
```txt
http(s)://ckcontents-jp.crossknowledge.com
http(s)://mohivecontents-jp.crossknowledge.com
```

#### CKLM (XKA, Digital Literacy, Leaders...)
```txt
http(s)://d12pbbvc3h54xm.cloudfront.net/*
http(s)://cklm-prod.s3.amazonaws.com/*
https://cdn-cklm-prod.crossknowledge.com/*
https://ckcg.crossknowledge.com/*
```

#### CUSTOMER CONTENT CDN
```txt
https://ckls-cdn-eu.crossknowledge.com/*
https://ckls-cdn-na.crossknowledge.com/*
https://ckls-cdn-sa.crossknowledge.com/*
https://ckls-cdn-jp.crossknowledge.com/*
```

### AWS CloudFront IP Ranges

Part of the content is hosted on Amazon Cloud for a better experience around the globe.

```txt
CLoudFront IPs could be from any of the IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "CLOUDFRONT"
```
<br/>
### CKLS portal IPs addresses

##### Europe CKLS created since September 2017 https://*.eu.crossknowledge.com: 
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the eu-central-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp-aws.eu.crossknowledge.com (52.58.183.197)
```
<br/>

##### Europe CKLS created before September 2017 https://*.eu.crossknowledge.com or https://*.lms.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) Could be hitting any IPs within the ranges 78.153.226.128/27 and 78.153.234.128/26
sftp server : sftp.crossknowledge.com (78.153.226.149)
sftp server : sftp.eu.crossknowledge.com (78.153.234.131)
```
<br/>
##### USA https://*.na.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the us-east-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.na.crossknowledge.com (54.221.219.193)
```
<br/>
##### South America: https://*.sa.crossknowledge.com
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the sa-east-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.sa.crossknowledge.com (54.232.80.112)
```
<br/>
##### Asia: https://*.asia.crossknowledge.com
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the ap-northeast-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.asia.crossknowledge.com (54.65.104.30)
```
<br/>
##### IPs addresses and URLs for CK-Hub https://ck-hub.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the eu-west-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2".
(also ck-hub-preprod.crossknowledge.com for UAT)
```

### Email servers requirements

<table border="1" cellpadding="10" cellspacing="0">

<tbody><tr>
<td>All emails are sent by Amazon SES service from crossknowledge.com domain
</td>
<td>CKLS sends emails using a FROM address that belongs to crossknowledge.com domain only. (default and preferred solution)<br>
<p>The client's email address is kept in the REPLYTO field <br>
E.g&nbsp;: user john.doe@client.com sends an email to someone, the received email will have the following attributes <br>
</p>
<pre>FROM:noreply@crossknowledge.com
REPLYTO:john.doe@client.com
</pre>
</td></tr>
<tr>
<td>All emails are sent by Amazon SES service using a FROM adresse that belongs to the client's domain (or crossknowledge.com domain)
</td>
<td>
<p>This setup requires some extra IT configuration tasks for both CrossKnowledge and client's IT Teams&nbsp;: DKIM entries to be added in client's DNS zone&nbsp;: client.com. <br>
E.g mail can be sent from noreply@client.com or any other @client.com addresses. <br>
In case an email having a FROM attribute not belonging to either client.com or crossknowledge.com domain, the FROM attribute is automatically replaced by noreply@client.com or any other generic address chosen by the client during the setup phase.
</p>
</td></tr>
<tr>
<td>All emails are sent directly by the client's SMTP relay
</td>
<td>
<p>CKLS application is then authorised to directly pass emails flow to a remote client's relay.<br>
CrossKnowledge will not provide any IP ranges (autoscalling CKLS servers may have various IPs changing regularly) however SMTP session can be secured by a TLS login and password (to be provided by Client's Email team).
</p>
</td></tr></tbody></table>

Maximum message size (including attachments) is limited to 10 MB per message (after base64 encoding).

## Sharepoint pre-requisites

### Sharepoint 2010
from IE7 to IE9, Firefox, Chrome
### Sharepoint 2013 
from IE8 to IE10, Firefox, Chrome<br/>

{% include note.html content="This plugin is not supported on the latest version of Office 365 (SharePoint 2016)." %}

## URL of CKLS platform
### Supported formats

* `https://customername.(eu lms na sa).crossknowledge.com`, with `http://customername.(eu-lms-na-sa).crossknowledge.com` being redirected to HTTPS (default setting).
* `http://customername.customerdomain.com` being redirected to HTTPS CrossKnowledge urls, as soon as customer domain has a valid DNS entry pointing to crossknowledge load balancer. e.g : http://customername.customerdomain.com with automatic rediction to https://customername.eu.crossknowledge.com


### Unsupported formats
* `https://customername.customerdomain.com` - Crossknowledge only support HTTPS protocol with its own urls.

## My Learning App
My Learning is compatible with the following devices:

* Apple iOS: any device with iOS 10 and above (iPhone 5 and up, iPod 6 and up, iPad mini 2 or iPad 4 and up)
* Android: any device with Android KitKat 4.4 (API 19) - a non contractual list can be found (here)[http://www.theandroidcop.com/list-of-android-smartphones-and-tablets-getting-android-4-4-kitkat-update/]

## Learn App

Learn is an application for iPad and iPhone working on iOS 8 and up. An Android application also exists (Android 4.2+). 

### Learning objects compatibility online and offline mode

Find below the list of learning objects with their compatibility status with Learn application (this list is subject to change).


Learning object type | Online mode | Offline mode
---- | ---- | ----
Custom SCORM | yes (monosco) | yes
Mohive| yes | yes
Easyquizz | no | no
Image | no | no
Audio mp3 | yes | yes
Video | yes | yes
Pdf | yes | yes
PPT | no | no
Text page | no | no
Zip file | no | no
YouTube | no | no
Slideshare | no | no
Brightcove | no | no
URL | no | no
Digital Literacy | yes | yes
Leaders Videocast | yes | yes
Business Digest | yes | soon
CrossKnowledge Essentials | yes | yes
CrossKnowledge Action Tips | yes | yes
CrossKnowledge Sessions V3 & The team | yes | yes 

## Update

These technical requirements may be modified according to technical developments of CrossKnowledge solutions
