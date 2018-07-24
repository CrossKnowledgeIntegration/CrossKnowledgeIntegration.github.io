---
title: CKLS Technical Prerequisites
keywords: pre-requisites, prerequisites, requirements
last_updated: 14 June, 2018
sidebar: home_sidebar
permalink: CKLS-prerequisites
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
            <td>Only "Medium and High" ciphers are allowed : <br>
                ECDH+AESGCM,DH+AESGCM,ECDH+AES256,DH+AES256,ECDH+AES128<br>DH+AES,ECDH+3DES,DH+3DES,RSA+AESGCM,RSA+AES,RSA+3DES.<br>
                TLSv1.1 and TLSv1.2 protocols are supported (TLS1.0 no longer supported as of 2018, Agust 31.</td>
        </tr>
        <tr>
            <td>Popup blocker for your URL</td>
            <td>Disabled</td>
        </tr>
    </tbody>
</table>

We systematically test the latest versions of Chrome, Firefox and Internet Explorer browsers to ensure the best experience for our users. Older versions of these browsers are not systematically tested, but run smoothly in most cases. If, however, there is a problem specific to a particular version of one of these browsers, please contact us.

These technical requirements may be modified according to technical developments of CrossKnowledge solutions.

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
https://*.crossknowledge.com, https://*.crossknowledge-player.com
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
### CKLS portal IPs addresses

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

@crossknowledge.com domain must be whitelisted as a trused sender. 

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

### Mail servers' IP addresses and whitelist

At the time of this writing, these are the IP ranges used by AWS SES:

```txt
199.255.192.0/22 199.127.232.0/22 54.240.0.0/18
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
from IE7 to IE9, Firefox, Chrome
### Sharepoint 2013 
from IE8 to IE10, Firefox, Chrome<br/>

{% include note.html content="This plugin is not supported on the latest version of Office 365 (SharePoint 2016)." %}

## URL of CKLS platform
### Supported formats

* `https://customername.(eu,lms,na,sa).crossknowledge.com`, with `http://customername.(eu,lms,na,sa).crossknowledge.com` being redirected to HTTPS (default setting).
* `http://customername.customerdomain.com` being redirected to HTTPS CrossKnowledge urls, as soon as customer domain has a valid DNS entry pointing to crossknowledge load balancer.
e.g : http://customername.customerdomain.com with automatic rediction to https://customername.eu.crossknowledge.com

### Unsupported formats
* `https://customername.customerdomain.com` - Crossknowledge only support HTTPS protocol with its own urls.
