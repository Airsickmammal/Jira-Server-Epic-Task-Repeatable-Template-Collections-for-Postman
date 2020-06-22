# Jira-Server-Epic-Task-Repeatable-Template-Collections-for-Postman
Jira Server Epic / Task Repeatable Template Collection for Postman

The Postman Collections serve as a template which demonstrates a number of ways to post both issue types, links and field type values to Jira Cloud using Epics and Epic Links; 
If you find any issues, want to request Readme updates etc please dont hesitate to create pull requests for review.

You can find me on Linkedin, Twitter, Twitch under username "Airsickmammal". 
Always happy to hear from and collaborate with the community.

Also Available on the Postman Templates Site. 
Server: https://documenter.getpostman.com/view/10332232/SzzobbJ7?version=latest
Cloud: https://documenter.getpostman.com/view/10332232/SzzobbJ8?version=latest

---Readme Still Under Construction---

------------------------------
Pre-Requisites: 
------------------------------
* PostMan (https://www.postman.com/)
* A Jira Server Setup (Will make a generic collection for Jira Cloud API at some point.)
* Administrator Permissions to any Projects you wish to deploy Issues into. (Unsure if this has changed since the last time i checked)
* Import either the Jira Server or Cloud JSON into PostMan to begin

------------------------------
Quick Note On Variables
------------------------------
Within the Postman JSON calls you will see various variables denoted by curly brackets "{{This is a Variable}}". 
These are globally referenced from Collection settings. Simply right click on (e.g.) "Jira Cloud Epic/Task Template Collection", select "Edit" and go to the "Variables" tab. Each of these variables are explained below, or within the Collection's Description tab using the above right-click> Edit collection method.

-------------------------------
JIRA SERVER - From Collection Description
-------------------------------
For Jira Server use REST API version 2 (already in the URLs within this collection). 

To use the API you will need collaborative rights to any target Jira projects.

Use basic Authentication on the "Authorization" tab (above), input your basic username and password. 

EPIC and Task Jira issue types must be enabled within your project to work with the vanilla postman collection.
Epic Name, Epic Link are required fields within your project. Epic Name being specific to the EPIC issue type.

2 ways to get the custom field number for Epic Name and Epic Link: 
1) Go to your global settings, Custom Fields, select Epic Name field, the url will contain "customFieldid=#####" you need to update in the json file. 
2) Use rest API to find the required field(s). You can find this under the "queries" folder or simply note down a Jira issue reference which contains the fields you need, and replace [Jira Host] and [ABC-1] with yours (minus the square brackets):
https://[Jira Host]/rest/api/2/search?jql=key=[ABC-1]

---------------------
PLEASE NOTE - in the API POST calls i have included a few notes, prefixed with "--", you need to remove these when you try to send the POST or it will fail, these are just to instruct with your first time using the template.
---------------------

Fill in the following Variables (see above Variables Tab)
* EPIC REF - Reference for your Epic (e.g. ABC)
* EPIC NAME - Summary/Title for your Epic
* Reporter
* Assignee
* Project Key - Key of your project that normally forms the pre-fix (e.g Issues ABC-1, ABC-2, your Project Key is ABC)
* Jira Host - Your Jira Server URL e.g. jira.Host.com
* Version - Use the version GET in Queries folder to obtain the version Name if you choose to use this
* Impact Name - Create an Array or List field to use this, exampls shows how to enter in a value, this could be a component, or a client's name, whatever your impact name list is defined with
* Due Date - Due date of the issue if you choose to use this, must be in Jira date format e.g. 2020-06-20T00:00:00.000+0100

These fields auto populate
* EPIC KEY - Populates with the issue Key of the epic (e.g. ABC-1) using a "test" after the API call has run
* Task 2 Key, and Task 3 Key: Used in the Vanilla collection to populate with the "2) Task With 2 Sub-Tasks" and "3) Task With Issue Link" issue keys, for use with updating ticket links in API call steps 4) and 5)
To see the "test" which auto populates the values go to either API calls 1), 2) or 3) and select the "Tests" tab

-------------------------------
JIRA CLOUD - From Collection Description
-------------------------------
For Jira Cloud use REST API version 3 (already in the URLs within this collection). 

To use the API you will need to generate a token via Atlassian api-tokens site here: 
https://id.atlassian.com/manage-profile/security/api-tokens

Use basic Authentication on the "Authorization" tab (above), input your basic username and then the token as your password. 

EPIC and Task Jira issue types must be enabled within your project to work with the vanilla postman collection.
Epic Name, Epic Link are required fields within your project. Epic Name being specific to the EPIC issue type.

2 ways to get the custom field number for Epic Name and Epic Link: 
1) Go to your global settings, Custom Fields, select Epic Name field, the url will contain "customFieldid=#####" you need to update in the json file. 
2) I found a brief explanation of this on the following Atlassian site: https://developer.atlassian.com/cloud/jira/software/rest/#introduction
3) Use rest API to find the required field(s). You can find this under the "queries" folder or simply note down a Jira issue reference which contains the fields you need, and replace [Jira Host] and [ABC-1] with yours (minus the square brackets):
https://[Jira Host]/rest/api/3/search?jql=key=[ABC-1]

---------------------
PLEASE NOTE - in the API POST calls i have included a few notes, prefixed with "--", you need to remove these when you try to send the POST or it will fail, these are just to instruct with your first time using the template.
---------------------

Fill in the following Variables (see above Variables Tab)
* EPIC REF - Reference for your Epic (e.g. ABC)
* EPIC NAME - Summary/Title for your Epic
* Reporter
* Assignee
* Project Key - Key of your project that normally forms the pre-fix (e.g Issues ABC-1, ABC-2, your Project Key is ABC)
* Jira Host - Your Jira Cloud URL e.g. ABC.atlassian.net
* Version - Use the version GET in Queries folder to obtain the version Name if you choose to use this
* Impact Name - Create an Array or List field to use this, exampls shows how to enter in a value, this could be a component, or a client's name, whatever your impact name list is defined with
* Due Date - Due date of the issue if you choose to use this, must be in Jira date format e.g. 2020-06-20T00:00:00.000+0100

These fields auto populate
* EPIC KEY - Populates with the issue Key of the epic (e.g. ABC-1) using a "test" after the API call has run
* Task 2 Key, and Task 3 Key: Used in the Vanilla collection to populate with the "2) Task With 2 Sub-Tasks" and "3) Task With Issue Link" issue keys, for use with updating ticket links in API call steps 4) and 5)
To see the "test" which auto populates the values go to either API calls 1), 2) or 3) and select the "Tests" tab
