---
title: Supported metrics - Microsoft.NotificationHubs/Namespaces/NotificationHubs
description: Reference for Microsoft.NotificationHubs/Namespaces/NotificationHubs metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.NotificationHubs/Namespaces/NotificationHubs  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.NotificationHubs/Namespaces/NotificationHubs resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Incoming Messages<p><p>The count of all successful send API calls.  |`incoming` |Count |Total |No Dimensions |Yes|
|All Incoming Failed Requests<p><p>Total incoming failed requests for a notification hub |`incoming.all.failedrequests` |Count |Total |No Dimensions |Yes|
|All Incoming Requests<p><p>Total incoming requests for a notification hub |`incoming.all.requests` |Count |Total |No Dimensions |Yes|
|Scheduled Push Notifications Sent<p><p>Scheduled Push Notifications Sent |`incoming.scheduled` |Count |Total |No Dimensions |Yes|
|Scheduled Push Notifications Cancelled<p><p>Scheduled Push Notifications Cancelled |`incoming.scheduled.cancel` |Count |Total |No Dimensions |Yes|
|Installation Management Operations<p><p>Installation Management Operations |`installation.all` |Count |Total |No Dimensions |Yes|
|Delete Installation Operations<p><p>Delete Installation Operations |`installation.delete` |Count |Total |No Dimensions |Yes|
|Get Installation Operations<p><p>Get Installation Operations |`installation.get` |Count |Total |No Dimensions |Yes|
|Patch Installation Operations<p><p>Patch Installation Operations |`installation.patch` |Count |Total |No Dimensions |Yes|
|Create or Update Installation Operations<p><p>Create or Update Installation Operations |`installation.upsert` |Count |Total |No Dimensions |Yes|
|All Outgoing Notifications<p><p>All outgoing notifications of the notification hub |`notificationhub.pushes` |Count |Total |No Dimensions |Yes|
|Bad or Expired Channel Errors<p><p>The count of pushes that failed because the channel/token/registrationId in the registration was expired or invalid. |`outgoing.allpns.badorexpiredchannel` |Count |Total |No Dimensions |Yes|
|Channel Errors<p><p>The count of pushes that failed because the channel was invalid not associated with the correct app throttled or expired. |`outgoing.allpns.channelerror` |Count |Total |No Dimensions |Yes|
|Payload Errors<p><p>The count of pushes that failed because the PNS returned a bad payload error. |`outgoing.allpns.invalidpayload` |Count |Total |No Dimensions |Yes|
|External Notification System Errors<p><p>The count of pushes that failed because there was a problem communicating with the PNS (excludes authentication problems). |`outgoing.allpns.pnserror` |Count |Total |No Dimensions |Yes|
|Successful notifications<p><p>The count of all successful notifications. |`outgoing.allpns.success` |Count |Total |No Dimensions |Yes|
|APNS Bad Channel Error<p><p>The count of pushes that failed because the token is invalid (APNS status code: 8). |`outgoing.apns.badchannel` |Count |Total |No Dimensions |Yes|
|APNS Expired Channel Error<p><p>The count of token that were invalidated by the APNS feedback channel. |`outgoing.apns.expiredchannel` |Count |Total |No Dimensions |Yes|
|APNS Authorization Errors<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.apns.invalidcredentials` |Count |Total |No Dimensions |Yes|
|APNS Invalid Notification Size Error<p><p>The count of pushes that failed because the payload was too large (APNS status code: 7). |`outgoing.apns.invalidnotificationsize` |Count |Total |No Dimensions |Yes|
|APNS Errors<p><p>The count of pushes that failed because of errors communicating with APNS. |`outgoing.apns.pnserror` |Count |Total |No Dimensions |Yes|
|APNS Successful Notifications<p><p>The count of all successful notifications. |`outgoing.apns.success` |Count |Total |No Dimensions |Yes|
|GCM Authentication Errors<p><p>The count of pushes that failed because the PNS did not accept the provided credentials the credentials are blocked or the SenderId is not correctly configured in the app (GCM result: MismatchedSenderId). |`outgoing.gcm.authenticationerror` |Count |Total |No Dimensions |Yes|
|GCM Bad Channel Error<p><p>The count of pushes that failed because the registrationId in the registration was not recognized (GCM result: Invalid Registration). |`outgoing.gcm.badchannel` |Count |Total |No Dimensions |Yes|
|GCM Expired Channel Error<p><p>The count of pushes that failed because the registrationId in the registration was expired (GCM result: NotRegistered). |`outgoing.gcm.expiredchannel` |Count |Total |No Dimensions |Yes|
|GCM Authorization Errors (Invalid Credentials)<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.gcm.invalidcredentials` |Count |Total |No Dimensions |Yes|
|GCM Invalid Notification Format<p><p>The count of pushes that failed because the payload was not formatted correctly (GCM result: InvalidDataKey or InvalidTtl). |`outgoing.gcm.invalidnotificationformat` |Count |Total |No Dimensions |Yes|
|GCM Invalid Notification Size Error<p><p>The count of pushes that failed because the payload was too large (GCM result: MessageTooBig). |`outgoing.gcm.invalidnotificationsize` |Count |Total |No Dimensions |Yes|
|GCM Errors<p><p>The count of pushes that failed because of errors communicating with GCM. |`outgoing.gcm.pnserror` |Count |Total |No Dimensions |Yes|
|GCM Successful Notifications<p><p>The count of all successful notifications. |`outgoing.gcm.success` |Count |Total |No Dimensions |Yes|
|GCM Throttled Notifications<p><p>The count of pushes that failed because GCM throttled this app (GCM status code: 501-599 or result:Unavailable). |`outgoing.gcm.throttled` |Count |Total |No Dimensions |Yes|
|GCM Wrong Channel Error<p><p>The count of pushes that failed because the registrationId in the registration is not associated to the current app (GCM result: InvalidPackageName). |`outgoing.gcm.wrongchannel` |Count |Total |No Dimensions |Yes|
|MPNS Authentication Errors<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.authenticationerror` |Count |Total |No Dimensions |Yes|
|MPNS Bad Channel Error<p><p>The count of pushes that failed because the ChannelURI in the registration was not recognized (MPNS status: 404 not found). |`outgoing.mpns.badchannel` |Count |Total |No Dimensions |Yes|
|MPNS Channel Disconnected<p><p>The count of pushes that failed because the ChannelURI in the registration was disconnected (MPNS status: 412 not found). |`outgoing.mpns.channeldisconnected` |Count |Total |No Dimensions |Yes|
|MPNS Dropped Notifications<p><p>The count of pushes that were dropped by MPNS (MPNS response header: X-NotificationStatus: QueueFull or Suppressed). |`outgoing.mpns.dropped` |Count |Total |No Dimensions |Yes|
|MPNS Invalid Credentials<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. |`outgoing.mpns.invalidcredentials` |Count |Total |No Dimensions |Yes|
|MPNS Invalid Notification Format<p><p>The count of pushes that failed because the payload of the notification was too large. |`outgoing.mpns.invalidnotificationformat` |Count |Total |No Dimensions |Yes|
|MPNS Errors<p><p>The count of pushes that failed because of errors communicating with MPNS. |`outgoing.mpns.pnserror` |Count |Total |No Dimensions |Yes|
|MPNS Successful Notifications<p><p>The count of all successful notifications. |`outgoing.mpns.success` |Count |Total |No Dimensions |Yes|
|MPNS Throttled Notifications<p><p>The count of pushes that failed because MPNS is throttling this app (WNS MPNS: 406 Not Acceptable). |`outgoing.mpns.throttled` |Count |Total |No Dimensions |Yes|
|WNS Authentication Errors<p><p>Notification not delivered because of errors communicating with Windows Live invalid credentials or wrong token. |`outgoing.wns.authenticationerror` |Count |Total |No Dimensions |Yes|
|WNS Bad Channel Error<p><p>The count of pushes that failed because the ChannelURI in the registration was not recognized (WNS status: 404 not found). |`outgoing.wns.badchannel` |Count |Total |No Dimensions |Yes|
|WNS Channel Disconnected<p><p>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.channeldisconnected` |Count |Total |No Dimensions |Yes|
|WNS Channel Throttled<p><p>The notification was dropped because the ChannelURI in the registration is throttled (WNS response header: X-WNS-NotificationStatus:channelThrottled). |`outgoing.wns.channelthrottled` |Count |Total |No Dimensions |Yes|
|WNS Dropped Notifications<p><p>The notification was dropped because the ChannelURI in the registration is throttled (X-WNS-NotificationStatus: dropped but not X-WNS-DeviceConnectionStatus: disconnected). |`outgoing.wns.dropped` |Count |Total |No Dimensions |Yes|
|WNS Expired Channel Error<p><p>The count of pushes that failed because the ChannelURI is expired (WNS status: 410 Gone). |`outgoing.wns.expiredchannel` |Count |Total |No Dimensions |Yes|
|WNS Authorization Errors (Invalid Credentials)<p><p>The count of pushes that failed because the PNS did not accept the provided credentials or the credentials are blocked. (Windows Live does not recognize the credentials). |`outgoing.wns.invalidcredentials` |Count |Total |No Dimensions |Yes|
|WNS Invalid Notification Format<p><p>The format of the notification is invalid (WNS status: 400). Note that WNS does not reject all invalid payloads. |`outgoing.wns.invalidnotificationformat` |Count |Total |No Dimensions |Yes|
|WNS Invalid Notification Size Error<p><p>The notification payload is too large (WNS status: 413). |`outgoing.wns.invalidnotificationsize` |Count |Total |No Dimensions |Yes|
|WNS Authorization Errors (Invalid Token)<p><p>The token provided to WNS is not valid (WNS status: 401 Unauthorized). |`outgoing.wns.invalidtoken` |Count |Total |No Dimensions |Yes|
|WNS Errors<p><p>Notification not delivered because of errors communicating with WNS. |`outgoing.wns.pnserror` |Count |Total |No Dimensions |Yes|
|WNS Successful Notifications<p><p>The count of all successful notifications. |`outgoing.wns.success` |Count |Total |No Dimensions |Yes|
|WNS Throttled Notifications<p><p>The count of pushes that failed because WNS is throttling this app (WNS status: 406 Not Acceptable). |`outgoing.wns.throttled` |Count |Total |No Dimensions |Yes|
|WNS Authorization Errors (Unreachable)<p><p>Windows Live is not reachable. |`outgoing.wns.tokenproviderunreachable` |Count |Total |No Dimensions |Yes|
|WNS Authorization Errors (Wrong Token)<p><p>The token provided to WNS is valid but for another application (WNS status: 403 Forbidden). This can happen if the ChannelURI in the registration is associated with another app. Check that the client app is associated with the same app whose credentials are in the notification hub. |`outgoing.wns.wrongtoken` |Count |Total |No Dimensions |Yes|
|Registration Operations<p><p>The count of all successful registration operations (creations updates queries and deletions).  |`registration.all` |Count |Total |No Dimensions |Yes|
|Registration Create Operations<p><p>The count of all successful registration creations. |`registration.create` |Count |Total |No Dimensions |Yes|
|Registration Delete Operations<p><p>The count of all successful registration deletions. |`registration.delete` |Count |Total |No Dimensions |Yes|
|Registration Read Operations<p><p>The count of all successful registration queries. |`registration.get` |Count |Total |No Dimensions |Yes|
|Registration Update Operations<p><p>The count of all successful registration updates. |`registration.update` |Count |Total |No Dimensions |Yes|
|Pending Scheduled Notifications<p><p>Pending Scheduled Notifications |`scheduled.pending` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->