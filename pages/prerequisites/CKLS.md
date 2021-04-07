---
title: CKLS Technical Prerequisites
keywords: pre-requisites, prerequisites, requirements
last_updated: 30 June, 2020
sidebar: home_sidebar
permalink: CKLS-prerequisites
folder: prerequisites
---


## Workstation requirements

CrossKnowledge Learning Suite is a web-based application needing the following environment to run properly:

Screen resolution|1024*768
Sound card|Recommended (speakers/headphones are required for most content)
RAM|2 GB (4GB preferred, depending on the OS)
Operating system|Microsoft Windows 8.1 (Desktop mode only) or 10, Apple macOS (10.13+)
Web browser|Microsoft Edge (latest version), Apple Safari (latest version), Google Chrome (latest version), Mozilla Firefox (latest version), *Internet Explorer 11 (latest version)* **¹**
Email clients|Standard email readers are supported to deliver CK standard emails. Email content is HTML.
Popup blocker|Disabled
Cookies|Enabled
JavaScript|Enabled
HTTPS|SSL Protocol: TLSv1.2<br>SSL Ciphers:<br>- ECDHE-ECDSA-AES128-GCM-SHA256<br>- ECDHE-RSA-AES128-GCM-SHA256<br>- ECDHE-ECDSA-AES128-SHA256<br>- ECDHE-RSA-AES128-SHA256<br>- ECDHE-ECDSA-AES128-SHA<br>- ECDHE-RSA-AES128-SHA<br>- ECDHE-ECDSA-AES256-GCM-SHA384<br>- ECDHE-RSA-AES256-GCM-SHA384<br>- ECDHE-ECDSA-AES256-SHA384<br>- ECDHE-RSA-AES256-SHA384<br>- ECDHE-RSA-AES256-SHA<br>- ECDHE-ECDSA-AES256-SHA<br>- AES128-GCM-SHA256<br>- AES128-SHA256<br>- AES128-SHA<br>- AES256-GCM-SHA384<br>- AES256-SHA256<br>- AES256-SHA<br>

**¹** *Please note that [Microsoft started to lower the support](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666) on this web browser. The usage of Microsoft Edge is highly recommended instead.*

<br>
We systematically test the latest versions of Chrome, Firefox and Internet Explorer browsers to ensure the best experience for our users. Older versions of these browsers are not systematically tested, but run smoothly in most cases. If, however, there is a problem specific to a particular version of one of these browsers, please contact us.

These technical requirements may be modified according to technical developments of CrossKnowledge solutions.
In addition to those, specific requirements apply to:
- Blendedˣ Embedded Web Resource Activity and Embedded BI tool in Analyze workspace: these features are used to integrate a 3rd party content from the web. CrossKnowledge can not guaranty the compatibility of the integrated content

In order to ensure a good user experience for Blendedˣ Embedded Content Activity, please ensure that SCORM contents are built to be responsive. For example, no Flash should be included in the SCORM content.


### Tablet compatibility

CrossKnowledge Learning Suite is compatible with iPad (2, 3, 4 and mini) - additional requirements may be needed for the content hosted on the Learning Suite.

CrossKnowledge Learning Suite is compatible with Android tablets (Chrome browser) - additional requirements may be needed for the content hosted on the Learning Suite. 

Please note that SCORM and AICC connectors are not optimized for mobile usage

### CrossKnowledge content additional requirements

As the contents are played on our Learning Suite, you need the Learning Suite requirements listed above, and the following ones:
 	
<table width="100%">
    <tbody>
        <tr>
            <td width="45%">PDF plugin</td>
            <td width="55%">Adobe Acrobat Reader DC (latest version)</td>
        </tr>
        <tr>
            <td width="45%">Adobe Flash Player (<a href="https://blog.adobe.com/en/publish/2017/07/25/adobe-flash-update.html" target="_blank"><b>until December 2020</b></a>, CrossKnowledge Sessions)</td>
            <td width="55%">latest version</td>
        </tr>
    </tbody>
</table>


## Network Information

### Media extensions
The following media extensions should be authorised.<br/>
`.FLV, .mp3, .mp4, .srt, .woff, .vtt, .xhtml`

### Domain white-listing
The following domain names should be whitelisted by customers and their partners.
```txt
https://*.crossknowledge.com, https://*.crossknowledge-player.com
```

If wildcards (*) are not allowed, authorise at least the following URLs:<br/>

#### General CKLS CDN URLs:

```txt
https://ckls-cdn.crossknowledge.com/
https://ckls-cdn.crossknowledge-china.com/
https://ckls-assets.eu.crossknowledge.com/
https://ckls-assets.na.crossknowledge.com/
https://ckls-assets.sa.crossknowledge.com/
https://ckls-assets.asia.crossknowledge.com/
https://ckls-cdn-eu.crossknowledge.com/
https://ckls-api.crossknowledge.com/
```

#### External medias (cloudfront URL)
```txt
https://d3d8qnlcu0b7xk.cloudfront.net
https://media-cdn2.crossknowledge.com
```

#### CK-Player URLs (for CrossKnowledge content delivery)

##### For users based in Europe
```txt
https://cdn.crossknowledge.com/*
https://d12yhdsdwe7din.cloudfront.net/* and http(s)://mohivecontents-eu.crossknowledge.com
```

##### For users based in the US:
```txt
https://d2niiguqm1v5wm.cloudfront.net/* and http(s)://ckcontents-na.crossknowledge.com
https://dmi776hgmgo8n.cloudfront.net/* and http(s)://mohivecontents-na.crossknowledge.com
```

##### For users based in Asia:
```txt
https://ckcontents-jp.crossknowledge.com
https://mohivecontents-jp.crossknowledge.com
https://crossknowledge-player.digitallearning.cn
```

#### CKLM (XKA, Digital Literacy, Leaders...)
```txt
https://d12pbbvc3h54xm.cloudfront.net/*
https://cklm-prod.s3.amazonaws.com/*
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

### CKLS portal IP addresses

#### Europe CKLS created since September 2017 https://*.eu.crossknowledge.com: 
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the eu-central-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp-aws.eu.crossknowledge.com (52.58.183.197)
```

<br/>

#### Europe CKLS created before September 2017 https://*.eu.crossknowledge.com or https://*.lms.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) Could be hitting any IPs within the ranges 78.153.226.128/27 and 78.153.234.128/26
sftp server : sftp.crossknowledge.com (78.153.226.149)
sftp server : sftp.eu.crossknowledge.com (78.153.234.131)
```
<br/>

#### USA https://*.na.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the us-east-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.na.crossknowledge.com (54.221.219.193)
```

<br/>

#### South America: https://*.sa.crossknowledge.com
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the sa-east-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.sa.crossknowledge.com (54.232.80.112)
```

<br/>

#### Asia: https://*.asia.crossknowledge.com
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the ap-northeast-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2"
sftp server : sftp.asia.crossknowledge.com (54.65.104.30)
```

<br/>

#### IPs addresses and URLs for CK-Hub https://ck-hub.crossknowledge.com:
```txt
web interfaces (ports 80 and 443) : Could be hitting any of the eu-west-1 IP ranges listed in https://ip-ranges.amazonaws.com/ip-ranges.json Where  "service" = "EC2".
(also ck-hub-preprod.crossknowledge.com for UAT)
```

## Email servers requirements

@crossknowledge.com domain must be whitelisted as a trusted sender. 

### Supported email configuration scenario :

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
<td>All emails are sent by Amazon SES service using a FROM address that belongs to the client's domain (or crossknowledge.com domain)
</td>
<td>
<p>This setup requires some extra IT configuration tasks for both CrossKnowledge and client's IT Teams&nbsp;: DKIM entries to be added in client's DNS zone&nbsp;: client.com. <br>
E.g mail can be sent from noreply@client.com or any other @client.com addresses. <br>
In case an email having a FROM attribute not belonging to either client.com or crossknowledge.com domain, the FROM attribute is automatically replaced by noreply@client.com or any other generic address chosen by the client during the setup phase.
Dedicated IPs can be used for whitelisting or security purposes.
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

### Mail servers' IP addresses and whitelist

At the time of this writing, these are the IP ranges used by AWS SES:

```txt
199.255.192.0/22 199.127.232.0/22 54.240.0.0/18 69.169.224.0/20
```
However these ranges may change, so to get an up to date list, please run the following command: 
From a Linux or Mac OS system:
```txt
$ dig TXT amazonses.com +short| grep 'v=spf1'
```
From a Windows system
```txt
C:>nslookup -type=TXT amazonses.com | find "v=spf1"
```
Emails can also be sent from this spare IP :
```
174.129.245.244/32
```
and for CKLS instances created before September 2017 and still hosted by Jaguar Network, please add also:
```
85.31.192.42/32 85.31.193.42/32 174.129.245.244/32
```
### Hostnames of SMTP relays and custom MAIL FROM domains used for sending 	

```txt
email-smtp.us-east-1.amazonaws.com
sesmailna.crossknowledge.com
email-smtp.eu-west-1.amazonaws.com
sesmaileu.crossknowledge.com
smtp01.crossknowledge.com
```

## Sharepoint pre-requisites

### Sharepoint 2010
Internet Explorer 11, Mozilla Firefox, Google Chrome
### Sharepoint 2013 
Internet Explorer 11, Mozilla Firefox, Google Chrome<br/>

{% include note.html content="This plugin is not supported on the latest version of Office 365 (SharePoint 2016)." %}

## URL of CKLS platform
### Supported formats

* `https://customername.(eu,lms,na,sa).crossknowledge.com`, with `http://customername.(eu,lms,na,sa).crossknowledge.com` being redirected to HTTPS (default setting).

### Unsupported formats
* `https://customername.customerdomain.com` - CrossKnowledge only supports HTTPS protocol with its own urls.
