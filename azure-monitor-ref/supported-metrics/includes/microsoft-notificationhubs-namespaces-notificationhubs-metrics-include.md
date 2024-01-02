---
ms.service: azure-monitor
ms.topic: include
ms.date: 11/09/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NotificationHubs/namespaces/notificationHubs, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Incoming Messages**<p><p>The count of all successful send API calls.  |`incoming` |Count |Total |\<none\>|PT1M |Yes|
|**All Incoming Failed Requests**<p><p>Total incoming failed requests for a notification hub |`incoming.all.failedrequests` |Count |Total |\<none\>|PT1M |Yes|
|**All Incoming Requests**<p><p>Total incoming requests for a notification hub |`incoming.all.requests` |Count |Total |\<none\>|PT1M |Yes|
|**Scheduled Push Notifications Sent**<p><p>Scheduled Push Notifications Sent |`incoming.scheduled` |Count |Total |\<none\>|PT1M |Yes|
|**Scheduled Push Notifications Cancelled**<p><p>Scheduled Push Notifications Cancelled |`incoming.scheduled.cancel` |Count |Total |\<none\>|PT1M |Yes|
|**Installation Management Operations**<p><p>Installation Management Operations |`installation.all` |Count |Total |\<none\>|PT1M |Yes|
|**Delete Installation Operations**<p><p>Delete Installation Operations |`installation.delete` |Count |Total |\<none\>|PT1M |Yes|
|**Get Installation Operations**<p><p>Get Installation Operations |`installation.get` |Count |Total |\<none\>|PT1M |Yes|
|**Patch Installation Operations**<p><p>Patch Installation Operations |`installation.patch` |Count |Total |\<none\>|PT1M |Yes|
|**Create or Update Installation Operations**<p><p>Create or Update Installation Operations |`installation.upsert` |Count |Total |\<none\>|PT1M |Yes|
|**All Outgoing Notifications**<p><p>All outgoing notifications of the notification hub |`notificationhub.pushes` |Count |Total |\<none\>|PT1M |Yes|
|**Bad or Expired Channel Errors**<p><p>The count of pushes that failed because the channel/token/registrationId in the registration was expired or invalid. |`outgoing.allpns.badorexpiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**Channel Errors**<p><p>The count of pushes that failed because the channel was invalid not associated with the correct app throttled or expired. |`outgoing.allpns.channelerror` |Count |Total |\<none\>|PT1M |Yes|
|**Payload Errors**<p><p>The count of pushes that failed because the PNS returned a bad payload error. |`outgoing.allpns.invalidpayload` |Count |Total |\<none\>|PT1M |Yes|
|**External Notification System Errors**<p><p>The count of pushes that failed because there was a problem communicating with the PNS (excludes authentication problems). |`outgoing.allpns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**Successful notifications**<p><p>The count of all successful notifications. |`outgoing.allpns.success` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Bad Channel Error**<p><p>The count of pushes that failed because the token is invalid (APNS status code: 8). |`outgoing.apns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Expired Channel Error**<p><p>The count of token that were invalidated by the APNS feedback channel. |`outgoing.apns.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Authorization Errors**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.apns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Invalid Notification Size Error**<p><p>The count of pushes that failed because the payload was too large (APNS status code: 7). |`outgoing.apns.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Errors**<p><p>The count of pushes that failed because of errors communicating with APNS. |`outgoing.apns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Successful Notifications**<p><p>The count of all successful notifications. |`outgoing.apns.success` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Authentication Errors**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials the credentials are blocked or the SenderId is not correctly configured in the app (GCM result: MismatchedSenderId). |`outgoing.gcm.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Bad Channel Error**<p><p>The count of pushes that failed because the registrationId in the registration was not recognized (GCM result: Invalid Registration). |`outgoing.gcm.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Expired Channel Error**<p><p>The count of pushes that failed because the registrationId in the registration was expired (GCM result: NotRegistered). |`outgoing.gcm.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Authorization Errors (Invalid Credentials)**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.gcm.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Invalid Notification Format**<p><p>The count of pushes that failed because the payload was not formatted correctly (GCM result: InvalidDataKey or InvalidTtl). |`outgoing.gcm.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Invalid Notification Size Error**<p><p>The count of pushes that failed because the payload was too large (GCM result: MessageTooBig). |`outgoing.gcm.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Errors**<p><p>The count of pushes that failed because of errors communicating with GCM. |`outgoing.gcm.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Successful Notifications**<p><p>The count of all successful notifications. |`outgoing.gcm.success` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Throttled Notifications**<p><p>The count of pushes that failed because GCM throttled this app (GCM status code: 501-599 or result:Unavailable). |`outgoing.gcm.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Wrong Channel Error**<p><p>The count of pushes that failed because the registrationId in the registration is not associated to the current app (GCM result: InvalidPackageName). |`outgoing.gcm.wrongchannel` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Authentication Errors**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Bad Channel Error**<p><p>The count of pushes that failed because the ChannelURI in the registration was not recognized (MPNS status: 404 not found). |`outgoing.mpns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Channel Disconnected**<p><p>The count of pushes that failed because the ChannelURI in the registration was disconnected (MPNS status: 412 not found). |`outgoing.mpns.channeldisconnected` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Dropped Notifications**<p><p>The count of pushes that were dropped by MPNS (MPNS response header: X-NotificationStatus: QueueFull or Suppressed). |`outgoing.mpns.dropped` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Invalid Credentials**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Invalid Notification Format**<p><p>The count of pushes that failed because the payload of the notification was too large. |`outgoing.mpns.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Errors**<p><p>The count of pushes that failed because of errors communicating with MPNS. |`outgoing.mpns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Successful Notifications**<p><p>The count of all successful notifications. |`outgoing.mpns.success` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Throttled Notifications**<p><p>The count of pushes that failed because MPNS is throttling this app (WNS MPNS: 406 Not Acceptable). |`outgoing.mpns.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authentication Errors**<p><p>Notification not delivered because of errors communicating with Windows Live invalid credentials or wrong token. |`outgoing.wns.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Bad Channel Error**<p><p>The count of pushes that failed because the ChannelURI in the registration was not recognized (WNS status: 404 not found). |`outgoing.wns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Channel Disconnected**<p><p>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.channeldisconnected` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Channel Throttled**<p><p>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-NotificationStatus:channelThrottled). |`outgoing.wns.channelthrottled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Dropped Notifications**<p><p>The notification was dropped because the ChannelURI in the registration is throttled (X-WNS-NotificationStatus: dropped but not X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.dropped` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Expired Channel Error**<p><p>The count of pushes that failed because the ChannelURI is expired (WNS status: 410 Gone). |`outgoing.wns.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Invalid Credentials)**<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. (Windows Live does not recognize the credentials). |`outgoing.wns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Invalid Notification Format**<p><p>The format of the notification is invalid (WNS status: 400). Note that WNS does not reject all invalid payloads. |`outgoing.wns.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Invalid Notification Size Error**<p><p>The notification payload is too large (WNS status: 413). |`outgoing.wns.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Invalid Token)**<p><p>The token provided to WNS is not valid (WNS status: 401 Unauthorized). |`outgoing.wns.invalidtoken` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Errors**<p><p>Notification not delivered because of errors communicating with WNS. |`outgoing.wns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Successful Notifications**<p><p>The count of all successful notifications. |`outgoing.wns.success` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Throttled Notifications**<p><p>The count of pushes that failed because WNS is throttling this app (WNS status: 406 Not Acceptable). |`outgoing.wns.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Unreachable)**<p><p>Windows Live is not reachable. |`outgoing.wns.tokenproviderunreachable` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Wrong Token)**<p><p>The token provided to WNS is valid but for another application (WNS status: 403 Forbidden). This can happen if the ChannelURI in the registration is associated with another app. Check that the client app is associated with the same app whose credentials are in the notification hub. |`outgoing.wns.wrongtoken` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Operations**<p><p>The count of all successful registration operations (creations updates queries and deletions).  |`registration.all` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Create Operations**<p><p>The count of all successful registration creations. |`registration.create` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Delete Operations**<p><p>The count of all successful registration deletions. |`registration.delete` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Read Operations**<p><p>The count of all successful registration queries. |`registration.get` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Update Operations**<p><p>The count of all successful registration updates. |`registration.update` |Count |Total |\<none\>|PT1M |Yes|
|**Pending Scheduled Notifications**<p><p>Pending Scheduled Notifications |`scheduled.pending` |Count |Total |\<none\>|PT1M |Yes|