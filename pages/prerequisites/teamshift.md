---
title: TeamSHIFT Technical Prerequisites
keywords: pre-requisites, prerequisites, requirements, teamshift
last_updated: 30 June, 2020
sidebar: home_sidebar
permalink: TeamShift-prerequisites
folder: prerequisites
---


## Workstation requirements 

The first requirement and mandatory one, is having the possibility to access Amazon Cloud URLs and IPs adresses.

TeamSHIFT is a CrossKnowledge solution which requires the following environment on the customer side to run properly:

<table>
    <tbody>
		<tr>
            <td>Screen resolution</td>
            <td>Supporting resolutions bigger than 320x568px (iPhone 5 in portrait mode)</td>
        </tr>
		<tr>
            <td>Sound card</td>
            <td>Recommended (speakers/headphones are required for most content)</td>
        </tr>
        <tr>
            <td>Operating system</td>
            <td>Microsoft Windows 8.1 (Desktop mode only) or 10, Apple macOS (10.13+)</td>
        </tr>
        <tr>
            <td>Web browser</td>
            <td>Microsoft Internet Explorer 11 (latest version), Microsoft Edge (latest version), Apple Safari (latest version), Google Chrome (latest version), Mozilla Firefox (latest version)</td>
        </tr>
        <tr>
            <td>Email clients</td>
            <td>Standard email readers are supported to deliver CK standard emails. Email content is HTML.</td>
        </tr>
        <tr>
            <td>Popup blocker</td>
            <td>Disabled</td>
        </tr>
        <tr>
            <td>PDF Reader</td>
            <td>Adobe Acrobat Reader DC (latest version)</td>
        </tr>
        <tr>
            <td>HTTPS</td>
            <td>Only "Medium and High" SSL ciphers are allowed (HIGH:MEDIUM:!ADH). Only TLSv1.2 SSL protocol is supported.</td>
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
#### General CKLS & TeamShift cloudfront URLs:

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

### CKLS & TeamShift portal IPs addresses

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
```txt
C:>nslookup -type=TXT amazonses.com | find "v=spf1"
```

#### Hostnames of SMTP relays and custom "MAIL FROM" domains used for sending 	

```txt
email-smtp.us-east-1.amazonaws.com
sesmailna.crossknowledge.com
email-smtp.eu-west-1.amazonaws.com
sesmaileu.crossknowledge.com
smtp01.crossknowledge.com
```
