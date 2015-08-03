---
layout: kb
title: Announcement 1, w=1
tags: highlighted
created_at: 2015-07-13
updated_at: 2015-07-15
---

###MX Record Configuration: ZoneEdit###

Log in to your account at ZoneEdit.com.
Select the zone that has the MX entries you would like to change.
Click Mail Servers (MS).
Delete the current entries: Select all checkboxes in the delete column.
Press the Delete button.
Click Yes to verify.
Add the MX record:
MailServer, add mail.mailroute.net. (note the trailing dot "."!)
Select *1st *priority for the rank
Add the name of your domain.
Click Add New Mail Server.
You will be asked to confirm the operation. Press Yes.
Note: If your mx record is not updating first check to make sure that the @ symbol appears in the Subdomain window. The Type will be MX, the TTL can be set to 1800, Set the Preference to 10 and the Host to mail.mailroute.net. If there is still an issue please make sure that your A record is set up correctly >> https://www.zoneedit.com/faq.html

