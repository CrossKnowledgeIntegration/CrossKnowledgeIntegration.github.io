---
title: Team Shift Technical Prerequisites
keywords: pre-requisites, prerequisites, requirements, teamshift
last_updated: 8 May, 2018
sidebar: home_sidebar
permalink: TeamShift-prerequisites.html
folder: prerequisites
---


## Workstation requirements 

The first requirement and mandatory one, is having the possibility to access Amazon Cloud URLs and IPs adresses.

Team Shift is a new CrossKnowledge solution which requires the following environment on the customer side to run properly:

<table>
    <tbody>
		  <tr>
            <td>Windows operating system</td>
            <td>Windows 7, 8, 10 (all W10 versions)</td>
        </tr>
        <tr>
            <td>Apple operating system</td>
            <td>Mac OSX (10.4) and newer</td>
        </tr>
        <tr>
            <td>Internet Explorer</td>
            <td>11 and later versions</td>
        </tr>
        <tr>
            <td>Microsoft Edge</td>
            <td>Current version and Current-1 version</td>
        </tr>
        <tr>
            <td>Firefox</td>
            <td>Current version and Current-1 version</td>
        </tr>
        <tr>
            <td>Chrome</td>
            <td>Current version and Current-1 version</td>
        </tr>
        <tr>
            <td>Safari</td>
            <td>iOS (10 and up) using Safari</td>
        </tr>
        <tr>
            <td>Opera and others browsers</td>
            <td>Not supported</td>
        </tr>
        <tr>
            <td>Email clients</td>
            <td>Outlook 2010, 2013 or 365, Lotus Notes: 8.5 or newer, Gmail or Google Inbox</td>
        </tr>
		<tr>
            <td>Sound card</td>
            <td>Sound card Activated (speakers/headphones are required for most content)</td>
        </tr>
		<tr>
            <td>Screen resolution</td>
            <td>Supporting resolutions bigger than 320x568px (iPhone 5 in portrait mode)</td>
        </tr>
        <tr>
            <td>HTTPS</td>
            <td>Only "Medium and High" ciphers are allowed (HIGH:MEDIUM:!ADH). TLSv1.x protocols are supported.</td>
        </tr>
        <tr>
            <td>Popup blocker for the solution</td>
            <td>Has to be disabled</td>
        </tr>
		        <tr>
            <td width="30%">Adobe Flash Player</td>
            <td width="70%">Not required</td>
        </tr>
        <tr>
            <td width="30%">PDF Reader</td>
            <td width="70%">Adobe Reader, SUMO PDF, Firefox, Edge or Chrome browsers</td>
        </tr>
    </tbody>
</table>

We systematically test the latest versions of Chrome, Firefox and Internet Explorer browsers to ensure the best experience for our users. Older versions of these browsers are not systematically tested, but run smoothly in most cases according the prerequisites defined previously. 

### Mobile device compatibility

iOS (10 and up) using SAFARI browser
ANDROID (4.4 and up) using CHROME browser
Other mobile devices are not supported

## Network Information

### Domain white-listing
The following domain names should be whitelisted.
```txt
http(s)://*.crossknowledge.com, http(s)://*.crossknowledge-player.com
```

If wildcards (*) are not allowed, authorise at least the following URLs:<br/>
#### General CKLS & Team Shift cloudfront URLs:

```txt
https://ckls-assets.crossknowledge.com/
https://ckls-api.crossknowledge.com/
https://ckls-cdn-eu.crossknowledge.com/
https://teamshift.crossknowledge.com/*
https://teamshift.eu.crossknowledge.com/* - this is the CKLS instance
https://alltypes-assessment.s3-sa-east-1.amazonaws.com/*
https://teamshift.s3-sa-east-1.amazonaws.com/*
```

#### External medias (cloudfront URL)
```txt
https://d3d8qnlcu0b7xk.cloudfront.net
https://media-cdn2.crossknowledge.com
```

#### CK-Player URLs (for CrossKnowledge content delivery)

##### For all users
```txt
http(s)://cdn.crossknowledge.com/*
http(s)://d12yhdsdwe7din.cloudfront.net/*
```

### AWS CloudFront IP Ranges

Part of our content is hosted on Amazon Cloud for a better experience around the globe.

```txt
54.182.0.0/16
54.192.0.0/16
54.230.0.0/16
54.239.128.0/18
54.239.192.0/19
54.240.128.0/18
204.246.164.0/22
204.246.168.0/22
204.246.174.0/23
204.246.176.0/20
205.251.192.0/19
205.251.249.0/24
205.251.250.0/23
205.251.252.0/23
205.251.254.0/24
216.137.32.0/19
```

### CKLS & Team Shift portal IPs addresses

##### CKLS urls format
Europe https://*.eu.crossknowledge.com
USA https://*.na.crossknowledge.com
South Amarica https://*.sa.crossknowledge.com
Asia https://*.asia.crossknowledge.com

### Email servers requirements

##### Mail servers' IP addresses and whitelist

TeamShift relies on Amazon SES service for sending emails. 
At the time of this writing, these are the IP ranges used by AWS SES:

```txt
199.255.192.0/22 199.127.232.0/22 54.240.0.0/18
Emails can also be sent from this spare IP : 174.129.245.244/32
no-reply@crossknowledge.com should be whitelisted
```
However these range may change so in order to get an up to date list, please run the following command 
From a Linux or Mac OS system:
```txt
$ dig TXT amazonses.com +short| grep 'v=spf1'
```
From a Windows system
``txt
C:>nslookup -type=TXT amazonses.com | find "v=spf1"
```

#### Hostnames of SMTP relay used for sending 	

```txt
email-smtp.us-east-1.amazonaws.com
sesmailna.crossknowledge.com
email-smtp.eu-west-1.amazonaws.com
sesmaileu.crossknowledge.com
smtp01.crossknowledge.com
```
