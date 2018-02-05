---
title: SAML 2.0
keywords: ...
last_updated: February 5, 2018
tags:
sidebar: home_sidebar
permalink: adfs.html
folder: Authentication
---

## Pre-requisite

* Your CKLS must be in HTTPS.
* You can't use the same certificates of an other CKLS in the same ADFS (default is ck.crt), you have to upload new ones in the LMS Back-Office.


## Generate metadata file from the ADFS and send it to CK

To generate the file, go to url https://server/federationmetadata/2007-06/federationmetadata.xml

Replace "server" by the actual server name

## On the ADFS server configuration interface, add a new Relying Party Trust using CrossKowledge federationMetadata.xml


![alt text](http://developers.crossknowledge.com/images/Party_trust_1.jpg)

![alt text](http://developers.crossknowledge.com/images/Party_trust_2.jpg)

![alt text](http://developers.crossknowledge.com/images/Party_trust_3.jpg)

![alt text](http://developers.crossknowledge.com/images/Party_trust_5.jpg)

![alt text](http://developers.crossknowledge.com/images/Party_trust_6.jpg)

Let the checkbox checked to open Claim Rules (or right click on your new relying party trust)


## Create a claim rule, type: "Transfor an incomming claim"

![alt text](http://developers.crossknowledge.com/images/Claim_Rules_nameID_1.jpg)

![alt text](http://developers.crossknowledge.com/images/Claim_Rules_nameID_2.jpg)

![alt text](http://developers.crossknowledge.com/images/Claim_Rules_nameID_3.jpg)

* Incoming claim type : E-Mail Address
* Outgoing claim type : Name ID
* Outgoing name ID format : Transient Identifier (you can modify the format, CKLS support emailAddress, transient, persistent and unspecified)

## Edit Active Directory 's Claims rules on Claims Provider Trusts, and add matching between AD email and ADFS email

Maybe a value from LDAP is not set in ADFS such as the emailAddress so you can't use the emailAddress as a nameID or an attribute. To add a mapping between LDAP and ADFS, you have to :

On the left menu, click on Claims Provider Trusts :

* Right click on Active Directory
* Edit Claim Rules... > Add Rule...
* Send LDAP Attributes as Claims
* Set a claim rule name, chose Active Directory as Attribute Store
* Set your ldap attribute as a saml attribute

![alt text](http://developers.crossknowledge.com/images/Ldap_adfs_mapping_1.jpg)

## You can add attributes from your ADFS by adding a Claim Rule in your Relying Party Trust

* Right click on your new Relying Party Trust
* Edit Claim Rules... > Add Rule...
* Send LDAP Attributes as Claims
* Set all mappings you want (group, name, surname, email etc)

![alt text](http://developers.crossknowledge.com/images/Claim_Rules_attributes_1.jpg)

![alt text](http://developers.crossknowledge.com/images/Claim_Rules_attributes_2.jpg)

## Debug ADFS

You can see logs in the Server Manager.

![alt text](http://developers.crossknowledge.com/images/ServermanagerADFS.jpg)



