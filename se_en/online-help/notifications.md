# Notifications

This section contains system notifications about any known issues or enhancements.

## EasyCruit Notification - Mulltiposting. fr intermittent service - RESOLVED

#### Issue description / What is the issue?

The job distribution service provided by  Multiposting.fr  was providing an intermittent service. This issue occurred after the completion of a migration of their job distribution service to a new data center that occurred over the Easter Weekend. For the customers who have been enabled to use the Multiposting.fr feature, they were experiencing longer than expected page load times for the Posting page. Also, if the customer chose from the Posting page to post using Multiposting.fr, the post could take up to 3 minutes and might not be successful, displaying an 801 error message.

#### Customer impact / Am I impacted?

Only customers that have enabled the new Multiposting.fr service were affected.

#### Workaround / Can I work around this?

There was no work around for this issue.

#### Measures and actions / What is the EasyCruit team doing about it?

The Multiposting.fr service was patched, the performance is back to normal. The EasyCruit team will continue to monitor the performance next week.

Should you have any queries on this, please don’t hesitate to contact us.

## Visma EasyCruit Support

The Community allows you to log support cases (issues) and monitor their status. If you do not have accesss to the Community, please contact your administrator or EasyCruit Support

[Norwegian Community Portal Login](https://community.visma.no/)

[All other Countries Community Portal Login](https://visma.force.com/customers/login)

## Notifications

### EasyCruit migration to Visma hosted environment

#### Update - 23/04/2017

The migration to our new data center has been completed and all customer are now live on the new platform.

We are however currently experiencing problems of receiving test results from SHL and Assessio. We are working on fixing this as soon as possible and will keep you updated on this page.

Update 24/04/2017 09:30 CET: We are now receiving test results from SHL and Assessio again. These results are however only from new tests and any tests that has been run by candidates during Saturday afternoon and Sunday has however not yet been updated in EasyCruit. We are currently working on fixing this.

#### Update - 11/04/2017

As part of the migration to the Visma hosted environment, there will be changes in the way EasyCruit handles the Sender Policy Framework for emails that you write in EasyCruit.

An SPF record will be created on the Visma hosted environment and it can be included as part of your own SPF record to avoid having to list the individual entries. Here is an example:

"v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Please note that any old record should not be removed until after the migration has taken place.

#### Update - 28/03/2017

As previously announced, the migration of data from Lumesse to Visma's hosting environment is in progress. The migration of the pilot customers has now successfully been completed.

Based on experience gained from the pilot period, we see that the time calculated to migrate is longer than originally anticipated.

The planned down-time has therefore been changed to Saturday 22.4 16:00 - Sunday 23.4 06:00 CEST.

#### Overview

In 2016 Visma acquired EasyCruit from Lumesse. After thorough preparation we are finally moving EasyCruit from Lumesse to Visma's hosting environment. The migration will happen in stages from mid March to mid April.

The EasyCruit service will be available during the migration period, with the exception of a planned downtime Saturday 22.4 16.00 - Sunday 23.4 06.00 CEST. Important updates and status of the migration can be found on this page.

You as a customer should not be affected by this change, unless you have white-listed the EasyCruit email server IP in your SPF record or firewall/spam filter. After the migration, the email server IP address will change and you will need to update any white listings with the new address. The IP address will be announced in advance of the migration 22th of April.

We ask you to go to: Visma Trust-Center/Transparency for updated information regarding our hosting environment and processing of data.Please ensure you share this information with all relevant users and your IT department. If any questions - contact your account manager or support.

#### New mail server IPs

As EasyCruit is being moved to Visma's hosting environment, the mail server IP will change at the time of migration.

All customers currently utilising SPF records to confirm EasyCruit as a valid sender must add new IPs to their SPF record. This is a manual change done by your IT administrator. The old IP, 62.209.53.50, must not be removed until the migration has taken place.

The additional IPs can be added at any time from now on. To ensure that there are no interruptions in the emails sent from EasyCruit, this needs to be done by the 21st of April.

The new IPs are:

34.249.196.78

34.251.157.56

34.252.27.239

35.157.154.159

35.157.187.101

As part of this migration, an SPF record has been created that can be included instead of adding the individual IPs manually. Example of how to include this: "v=spf1 a mx a:outmail.easycruit.com include:_spf.easycruit.com ~all"

Please note that any old record should not be removed until after the migration has taken place.

#### DNS Propagation

As EasyCruit is being moved from one hosting provider to another, all the servers in the system will be given new IPs.

It is expected that the propagation of the new IPs to DNS servers will take place during the downtime and therefore not cause any issues to our customers.

However, there are possibilities that certain servers have not received the new IPs or that a customer uses locally cached DNS records. In these scenarios it might be a need for a customer to clear the local cache or use an alternative DNS server until their normal one has been updated.

#### New IPs for outbound traffic

As EasyCruit is being moved from one hosting provider to another, all the servers in the system will be given new IPs.

This includes the servers that make outbound connections, e.g. job board integrations and assessment integrations.

Compared to how EasyCruit operates today, the connections will come from a range of IPs rather than a single one. If white listing is being conducted by the integrating partner, they would therefore need to update their firewall to accommodate these changes.

### Operational issues notifications 31.8.2016: 18:43 CEST SOLVED

The issues are now solved and all applicants should no be able to apply to all positions.

Please note that to implement the solution, the servers had to be restarted. This may have caused a short interruption to the service. We apologize for any inconvenience caused.

#### Operational issues notification 31.8.2016: 14:46 CEST

We currently experience some disturbance on the EasyCruit service. The issue prevents some candidates to complete their applications. This happens if the education and experience fields are made mandatory in the project. We can ensure you that we are working to solve this issue as quickly as we possible can and apologize for the inconvenience this may cause you.

### Operational issues notification- security certificate issue

Operational issues notification- security certificate issue 14.10.2016 13.13 CEST

The issuer of our security certificate, GlobalSign, are experiencing an error which is affecting EasyCruit and other services. Users and candidates may therefore currently get error messages when they try to access the EasyCruit service.

GlobalSign is working to resolve the issue, but due to caching issues, this may take up to 4 days to fix completely.

If you can't wait you can follow this guide from GlobalSign webpage, which will help you clear the relevant cache:

[https://support.globalsign.com/custo...ticles/1353318](https://support.globalsign.com/customer/portal/articles/1353318)

We apologize for the inconvenience this may cause you.

### Visma EasyCruit Maintenance notification 05.06.2017 21.00-21.10 CEST

Maintenance of Visma EasyCruit will be carried out on June 5th 2017 between 21.00-21.10 CEST. During this time Visma EasyCruit will not be available.

Users will not be able to login to the system and candidates will not be able to use career center or apply for vacancies.

We want to apologize for the inconvenience this may cause.

If you have any question regarding this maintenance please do not hesitate to contact your local Visma Easycruit support.

### Operational issues notification- performance issues update 17.01.2017

Visma EasyCruit is currently experiencing some disturbance on the service resulting in a longer response time for system users. We can ensure you that we are working to solve this issue as quickly as we possible can and apologize for the inconvenience this may cause you.

Our development team have dedicated resources and give this issues highest priority.

At the end of this week we will be adding more memory as one of the action to improve the response time.

### EasyCruit Maintenance notification 14.03.2017 18.30-19.00 CET

Maintenance of memcache will be carried out on March 14th 2017 between 18.30-19.00 CET. During this time EasyCruit will not be available.

Users will not be able to login to the system and candidates will not be able to use career center or apply for vacancies.

We want to apologize for the inconvenience this may cause.

If you have any question regarding this maintenance please do not hesitate to contact your local Easycruit support.



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNTYwOTY2MjZdfQ==
-->