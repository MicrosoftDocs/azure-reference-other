---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 08/08/2024
ms.custom: Microsoft.NotificationHubs/namespaces/notificationHubs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Incoming Messages**<br><br>The count of all successful send API calls. |`incoming` |Count |Total |\<none\>|PT1M |Yes|
|**All Incoming Failed Requests**<br><br>Total incoming failed requests for a notification hub |`incoming.all.failedrequests` |Count |Total |\<none\>|PT1M |Yes|
|**All Incoming Requests**<br><br>Total incoming requests for a notification hub |`incoming.all.requests` |Count |Total |\<none\>|PT1M |Yes|
|**Scheduled Push Notifications Sent**<br><br>Scheduled Push Notifications Sent |`incoming.scheduled` |Count |Total |\<none\>|PT1M |Yes|
|**Scheduled Push Notifications Cancelled**<br><br>Scheduled Push Notifications Cancelled |`incoming.scheduled.cancel` |Count |Total |\<none\>|PT1M |Yes|
|**Installation Management Operations**<br><br>Installation Management Operations |`installation.all` |Count |Total |\<none\>|PT1M |Yes|
|**Delete Installation Operations**<br><br>Delete Installation Operations |`installation.delete` |Count |Total |\<none\>|PT1M |Yes|
|**Get Installation Operations**<br><br>Get Installation Operations |`installation.get` |Count |Total |\<none\>|PT1M |Yes|
|**Patch Installation Operations**<br><br>Patch Installation Operations |`installation.patch` |Count |Total |\<none\>|PT1M |Yes|
|**Create or Update Installation Operations**<br><br>Create or Update Installation Operations |`installation.upsert` |Count |Total |\<none\>|PT1M |Yes|
|**All Outgoing Notifications**<br><br>All outgoing notifications of the notification hub |`notificationhub.pushes` |Count |Total |\<none\>|PT1M |Yes|
|**Bad or Expired Channel Errors**<br><br>The count of pushes that failed because the channel/token/registrationId in the registration was expired or invalid. |`outgoing.allpns.badorexpiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**Channel Errors**<br><br>The count of pushes that failed because the channel was invalid not associated with the correct app throttled or expired. |`outgoing.allpns.channelerror` |Count |Total |\<none\>|PT1M |Yes|
|**Payload Errors**<br><br>The count of pushes that failed because the PNS returned a bad payload error. |`outgoing.allpns.invalidpayload` |Count |Total |\<none\>|PT1M |Yes|
|**External Notification System Errors**<br><br>The count of pushes that failed because there was a problem communicating with the PNS (excludes authentication problems). |`outgoing.allpns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**Successful notifications**<br><br>The count of all successful notifications. |`outgoing.allpns.success` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Bad Channel Error**<br><br>The count of pushes that failed because the token is invalid (APNS status code: 8). |`outgoing.apns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Expired Channel Error**<br><br>The count of token that were invalidated by the APNS feedback channel. |`outgoing.apns.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Authorization Errors**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.apns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Invalid Notification Size Error**<br><br>The count of pushes that failed because the payload was too large (APNS status code: 7). |`outgoing.apns.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Errors**<br><br>The count of pushes that failed because of errors communicating with APNS. |`outgoing.apns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**APNS Successful Notifications**<br><br>The count of all successful notifications. |`outgoing.apns.success` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Bad Channel Errors**<br><br>The count of pushes that failed because the registrationId in the registration was not recognized (FCMv1 result: Invalid registration, Missing Registration, Not registered, Not found, or Gone). |`outgoing.fcmv1.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Authorization Errors (Invalid Credentials)**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials (FCMv1 result: Sender Id Mismatch, Unauthorized, or Forbidden). |`outgoing.fcmv1.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Invalid Notification Format**<br><br>The count of pushes that failed because the payload was not formatted correctly (FCMv1 result: Invalid TTL, Invalid parameters, or Invalid data key). |`outgoing.fcmv1.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Invalid Notification Size Errors**<br><br>The count of pushes that failed because the payload was too large (FCMv1 result: Message too big). |`outgoing.fcmv1.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Errors**<br><br>The count of pushes that failed because of errors communicating with FCMv1. |`outgoing.fcmv1.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Successful Notifications**<br><br>The count of all successful notifications. |`outgoing.fcmv1.success` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Throttled Notifications**<br><br>The count of pushes that failed because FCMv1 throttled this app (FCMv1 Result: Quota Exceeded or 429). |`outgoing.fcmv1.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**FCMv1 Wrong Channel Errors**<br><br>The count of pushes that failed because the registrationId in the registration is not associated to the current app (FCMv1 result: Invalid package name). |`outgoing.fcmv1.wrongchannel` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Authentication Errors**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials the credentials are blocked or the SenderId is not correctly configured in the app (GCM result: MismatchedSenderId). |`outgoing.gcm.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Bad Channel Error**<br><br>The count of pushes that failed because the registrationId in the registration was not recognized (GCM result: Invalid Registration). |`outgoing.gcm.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Expired Channel Error**<br><br>The count of pushes that failed because the registrationId in the registration was expired (GCM result: NotRegistered). |`outgoing.gcm.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Authorization Errors (Invalid Credentials)**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.gcm.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Invalid Notification Format**<br><br>The count of pushes that failed because the payload was not formatted correctly (GCM result: InvalidDataKey or InvalidTtl). |`outgoing.gcm.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Invalid Notification Size Error**<br><br>The count of pushes that failed because the payload was too large (GCM result: MessageTooBig). |`outgoing.gcm.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Errors**<br><br>The count of pushes that failed because of errors communicating with GCM. |`outgoing.gcm.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Successful Notifications**<br><br>The count of all successful notifications. |`outgoing.gcm.success` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Throttled Notifications**<br><br>The count of pushes that failed because GCM throttled this app (GCM status code: 501-599 or result:Unavailable). |`outgoing.gcm.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**GCM Wrong Channel Error**<br><br>The count of pushes that failed because the registrationId in the registration is not associated to the current app (GCM result: InvalidPackageName). |`outgoing.gcm.wrongchannel` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Authentication Errors**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Bad Channel Error**<br><br>The count of pushes that failed because the ChannelURI in the registration was not recognized (MPNS status: 404 not found). |`outgoing.mpns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Channel Disconnected**<br><br>The count of pushes that failed because the ChannelURI in the registration was disconnected (MPNS status: 412 not found). |`outgoing.mpns.channeldisconnected` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Dropped Notifications**<br><br>The count of pushes that were dropped by MPNS (MPNS response header: X-NotificationStatus: QueueFull or Suppressed). |`outgoing.mpns.dropped` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Invalid Credentials**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Invalid Notification Format**<br><br>The count of pushes that failed because the payload of the notification was too large. |`outgoing.mpns.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Errors**<br><br>The count of pushes that failed because of errors communicating with MPNS. |`outgoing.mpns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Successful Notifications**<br><br>The count of all successful notifications. |`outgoing.mpns.success` |Count |Total |\<none\>|PT1M |Yes|
|**MPNS Throttled Notifications**<br><br>The count of pushes that failed because MPNS is throttling this app (WNS MPNS: 406 Not Acceptable). |`outgoing.mpns.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authentication Errors**<br><br>Notification not delivered because of errors communicating with Windows Live invalid credentials or wrong token. |`outgoing.wns.authenticationerror` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Bad Channel Error**<br><br>The count of pushes that failed because the ChannelURI in the registration was not recognized (WNS status: 404 not found). |`outgoing.wns.badchannel` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Channel Disconnected**<br><br>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.channeldisconnected` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Channel Throttled**<br><br>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-NotificationStatus:channelThrottled). |`outgoing.wns.channelthrottled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Dropped Notifications**<br><br>The notification was dropped because the ChannelURI in the registration is throttled (X-WNS-NotificationStatus: dropped but not X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.dropped` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Expired Channel Error**<br><br>The count of pushes that failed because the ChannelURI is expired (WNS status: 410 Gone). |`outgoing.wns.expiredchannel` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Invalid Credentials)**<br><br>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. (Windows Live does not recognize the credentials). |`outgoing.wns.invalidcredentials` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Invalid Notification Format**<br><br>The format of the notification is invalid (WNS status: 400). Note that WNS does not reject all invalid payloads. |`outgoing.wns.invalidnotificationformat` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Invalid Notification Size Error**<br><br>The notification payload is too large (WNS status: 413). |`outgoing.wns.invalidnotificationsize` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Invalid Token)**<br><br>The token provided to WNS is not valid (WNS status: 401 Unauthorized). |`outgoing.wns.invalidtoken` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Errors**<br><br>Notification not delivered because of errors communicating with WNS. |`outgoing.wns.pnserror` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Successful Notifications**<br><br>The count of all successful notifications. |`outgoing.wns.success` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Throttled Notifications**<br><br>The count of pushes that failed because WNS is throttling this app (WNS status: 406 Not Acceptable). |`outgoing.wns.throttled` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Unreachable)**<br><br>Windows Live is not reachable. |`outgoing.wns.tokenproviderunreachable` |Count |Total |\<none\>|PT1M |Yes|
|**WNS Authorization Errors (Wrong Token)**<br><br>The token provided to WNS is valid but for another application (WNS status: 403 Forbidden). This can happen if the ChannelURI in the registration is associated with another app. Check that the client app is associated with the same app whose credentials are in the notification hub. |`outgoing.wns.wrongtoken` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Operations**<br><br>The count of all successful registration operations (creations updates queries and deletions). |`registration.all` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Create Operations**<br><br>The count of all successful registration creations. |`registration.create` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Delete Operations**<br><br>The count of all successful registration deletions. |`registration.delete` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Read Operations**<br><br>The count of all successful registration queries. |`registration.get` |Count |Total |\<none\>|PT1M |Yes|
|**Registration Update Operations**<br><br>The count of all successful registration updates. |`registration.update` |Count |Total |\<none\>|PT1M |Yes|
|**Pending Scheduled Notifications**<br><br>Pending Scheduled Notifications |`scheduled.pending` |Count |Total |\<none\>|PT1M |Yes|