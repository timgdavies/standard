---
layout: default
title: Getting started
---

# 1. Get registered

To publish 360 Giving data you will need a unique ID. You can register to get your 360G ID here. 

# 2. Grab our sample spreadsheet

We've prepared a simple spreadsheet template, ideal if you have between 10s and 1000s grants to describe. 

You can download a copy in Excel format for working offline, but the easiest way to keep your 360 Giving data updated is to make a copy of the Google Spreadsheet version of the template, and save it in your Google Drive account. 

The Google Spreadsheet copy comes with a range of handy tools to help you manage your data.

If you have more than a few thousand grants to publish details of then get in touch for advice on how best to create your data. 

# 3. Read the guidance

There are a few important things you need to know about using the spreadsheet template. Here's a summary:


## A. Understanding identifiers

You might usually refer to your grants by name: but computers find it a lot easier to match things together with IDs, particularly when combining data from different systems. Identifiers 

There are two kinds of identifier used in the standard:

* Your own identifiers
* Shared identifiers

### Your own IDs
Your own identifiers are the ones that you make up, or that come from your internal systems. For example, you might number your grants each year, giving them identifiers like 2013-01, 2013-02 and so-on. 

Whenever you are using an Internal Identifier, you need to prefix it your 360G identifier, followed by ":". For example, if your 360G identifier was '360G-indigo' and you have a grant known in your internal system as 'IND123, it's Activity identifier would be: '360G-indigo:IDN123'.

As a rule of thumb, if you are wholly responsible for it (a grant, a document, an event etc.) then you get to decide on the ID - and just need to add your 360G prefix to it

Note: identifiers should not include spaces, or special characters. Replace these with - (dash)

Tip: You might find it useful to let your grantees know the 360G identifier you have given to their project. This identifier is likely to be unique online, so if you ask them to include it in project documents somewhere, or when they mention the funding you have given, then you will be able to search the web and more easily find online documents related to this funding if any are available. 

### Shared identifiers

Shared identifiers are mainly used for referring to organisations. Most organisations have been assigned an official registration number, so making use of this helps to join up data between different systems.

Of course, there are different kinds of registration number: you might give money to charities, companies and Universities, all of which have different registration bodies and identifiers. So shared organisation identifiers also have a prefix to indicate who the registration body is.

We're using the International Aid Transparency Initiative standard for organisation identifiers. You can [find a tool here](http://practicalparticipation.github.io/organisation-id-tool/) which will help you work out the organisation identifiers to use.

(Tip, the prefix for UK charities is 'GB-CHC-' and for UK companies is 'GB-COH').

If you have not recorded charity numbers, company numbers or some other official identifier for your grantees - don't worry. The Organisation ID tool will point you to where you can look these up if you only have a small number of grants, or there are automated look up tools available if you have lots of grantees to find IDs for. 

As a temporary measure you can also generate your own internal IDs if you need to (e.g. 360G-indigo:temp_org_01).

## B. A Simple summary, or in-depth details

You will see the that the template consists of a number of sheets (look for the tabs along the bottom). You can describe all the basic facts about your grants on the 'Activity' tab.

However, sometimes you may have extra details to share that don't fit here. That's where the other tabs come in.

For example, if the beneficiaries of a grant are located in lots of different locations, you can go to the Locations tab. Here, you would:
* Add the 'Activity ID' of the grant these beneficiary locations relate to;
* Select 'beneficiaryLocation' as the relationship type; and
* Fill in details of the location.

In other words, this location is related to the grant as a 'beneficiaryLocation'. You can add as many locations related to a single activity as you need. The same thing works for related documents, events (like planned and actual dates of an activity), and financial transactions. 

## C. Dates

In the US dates are normally written month/day/year. In the UK we write them day/month/year. That gets confusing when combining data from different places (Is 02/05/2014 in February or May? A computer can't easily tell). 

To avoid confusion the 360 giving standard uses the 'year-month-day' format for writing dates. For example 2014-02-01 to describe the 1st February 2014. 

The dates you in your systems might not be in this format, but don't worry - it's easy to convert them. In Google Spreadsheets the formula '=Text(R2,"yyyy-mm-dd")', where R2 is a cell containing a date in another format, will get dates into the right format for you (check carefully whether the spreadsheet properties are set to the right one of US or UK date formats when doing this).

## D. Add columns if you need - but don't rename the defaults

We've tried to name all the columns in as intuitive a way as possible. It's really important that you don't change the name of any of the columns in the spreadsheet template. There will be detailed descriptions of each column available here soon.

However, you can add extra columns if you need. Just start their name with 'Internal' and then whatever you want. For example, if you want to make updating your data easier by having somewhere to paste in the IDs you use for grants, and then have a formula make the Activity ID with your prefix, that's absolutely fine. Tools that use the data should just ignore those extra columns. 

You can also change the order of columns, and hide the ones you don't need. Just don't delete them completely, and again, don't change their names! 

## E. Classifications and vocabularies

There are lots of different ways you might want to classify your grants. Right now, the 360 Giving standard does not provide a core set of codelists or classifications, but instead lets you flexibly use the classifications you already have (for example, if you divide your grants into 'arts', 'sports' and so-on).

Classifications are made up of:
 
* A vocabulary
* A code
* An optional title and description

### Vocabularies
A vocabulary is the list of valid codes. For example, the US [National Taxonomy of Exempt Entities](http://foundationcenter.org/ntee/) (NTEE) is a vocabulary that provides a list of valid codes, ranging from A20 for 'Arts and cultural orgnaisations' through Z for 'Not elsewhere clasified'

Vocabularies can either be shared identifiers, or internal to your organisation.

For internal vocabularies, prefix a vocabulary identifiers with your 360G Id. For example '360G-indigo:programArea' 

360G will soon maintain a list of recognised vocabularies, and their identifiers, such as 360G:NTEE for the National Taxonomy of Exempt entities that has been mentioned.

A special vocabulary of 360G:TAGS can be used for free-tagging

### Codes 
Codes should be a short identifier for this category, with no spaces or other special characters. 

If you don't currently have codes for the categories you use (e.g. you just refer to them by name) you could add a new tab to the spreadsheet to start building up your own codelist. Add columns for 'Vocabulary', 'Code', 'Title' and list each code on it's own line. You can then use this to lookup codes in future. 

### What are you classifying?

You will notice the classification sheet has space for 'Organsation ID', 'Activity ID', 'Document ID' and so-on. That's because all these different kinds of things can be classified and categorised. Just fill in the relevant one for the thing you are classifying and leave the others blank.
