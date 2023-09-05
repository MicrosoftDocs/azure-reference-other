---
title: Supported metrics - Microsoft.MobileNetwork/packetcorecontrolplanes
description: Reference for Microsoft.MobileNetwork/packetcorecontrolplanes metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.MobileNetwork/packetcorecontrolplanes  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.MobileNetwork/packetcorecontrolplanes resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Session Count<p><p>Number of active PDU/PDN sessions |`ActiveSessionCount` |Count |Total |3gppGen, SiteId |No|
|Authentication Attempts<p><p>4G/5G authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |3gppGen, SiteId |No|
|Authentication Failures<p><p>4G/5G authentication failure rate (per minute) |`AuthFailure` |Count |Total |3gppGen, SiteId, Result |No|
|Authentication Successes<p><p>4G/5G authentication success rate (per minute) |`AuthSuccess` |Count |Total |3gppGen, SiteId |No|
|Connected NodeBs<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |3gppGen, SiteId |No|
|DeRegistration Attempts<p><p>Deregistration (5G) or detachment (4G) attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |3gppGen, SiteId |No|
|DeRegistration Successes<p><p>Deregistration (5G) or detachment (4G) success rate (per minute) |`DeRegistrationSuccess` |Count |Total |3gppGen, SiteId |No|
|Paging Attempts<p><p>4G/5G paging attempts rate (per minute) |`PagingAttempt` |Count |Total |3gppGen, SiteId |No|
|Paging Failures<p><p>4G/5G paging failure rate (per minute) |`PagingFailure` |Count |Total |3gppGen, SiteId |No|
|Provisioned Subscribers<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |SiteId |No|
|RAN Setup Failures<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |3gppGen, SiteId, Cause |No|
|RAN Setup Requests<p><p>RAN setup request rate (per minute) |`RanSetupRequest` |Count |Total |3gppGen, SiteId |No|
|RAN Setup Successes<p><p>RAN setup success rate (per minute) |`RanSetupSuccess` |Count |Total |3gppGen, SiteId |No|
|Registered Subscribers<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |3gppGen, SiteId |No|
|Registered Subscribers Connected<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |3gppGen, SiteId |No|
|Registered Subscribers Idle<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |3gppGen, SiteId |No|
|Registration Attempts<p><p>Registration (5G) or attachment (4G) attempts rate (per minute) |`RegistrationAttempt` |Count |Total |3gppGen, SiteId |No|
|Registration Failures<p><p>Registration (5G) or attachment (4G) failure rate (per minute) |`RegistrationFailure` |Count |Total |3gppGen, SiteId, Result |No|
|Registration Successes<p><p>Registration (5G) or attachment (4G) success rate (per minute) |`RegistrationSuccess` |Count |Total |3gppGen, SiteId |No|
|Service Request Attempts<p><p>4G/5G service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |3gppGen, SiteId |No|
|Service Request Failures<p><p>4G/5G service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |3gppGen, SiteId, Result, Tai |No|
|Service Request Successes<p><p>4G/5G service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |3gppGen, SiteId |No|
|Session Establishment Attempts<p><p>PDU/PDN session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |3gppGen, SiteId, Dnn |No|
|Session Establishment Failures<p><p>PDU/PDN session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |3gppGen, SiteId |No|
|Session Establishment Successes<p><p>PDU/PDN session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |3gppGen, SiteId, Dnn |No|
|Session Releases<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |3gppGen, SiteId |No|
|UE Context Release Commands<p><p>4G/5G UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |3gppGen, SiteId |No|
|UE Context Release Completes<p><p>4G/5G UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |3gppGen, SiteId |No|
|UE Context Release Requests<p><p>4G/5G UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |3gppGen, SiteId |No|
|Xn Handover Attempts<p><p>XnHandover (5G) or X2Handover (4G) attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |3gppGen, SiteId |No|
|Xn Handover Failures<p><p>XnHandover (5G) or X2Handover (4G) failure rate (per minute) |`XnHandoverFailure` |Count |Total |3gppGen, SiteId |No|
|Xn Handover Successes<p><p>XnHandover (5G) or X2Handover (4G) success rate (per minute) |`XnHandoverSuccess` |Count |Total |3gppGen, SiteId |No|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->