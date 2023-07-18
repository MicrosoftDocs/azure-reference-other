---
title: Supported metrics - microsoft.kubernetesconfiguration/extensions
description: Reference for microsoft.kubernetesconfiguration/extensions metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.kubernetesconfiguration/extensions  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.kubernetesconfiguration/extensions resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active PDU Sessions<p><p>Number of Active PDU Sessions |`ActiveSessionCount` |Count |Total |3gppGen, PccpId, SiteId |No|
|Authentication Attempts<p><p>Authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Authentication Failures<p><p>Authentication failure rate (per minute) |`AuthFailure` |Count |Total |3gppGen, PccpId, SiteId, Result |Yes|
|Authentication Successes<p><p>Authentication success rate (per minute) |`AuthSuccess` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Connected NodeBs<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|DeRegistration Attempts<p><p>UE deregistration attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|DeRegistration Successes<p><p>UE deregistration success rate (per minute) |`DeRegistrationSuccess` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Paging Attempts<p><p>Paging attempts rate (per minute) |`PagingAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Paging Failures<p><p>Paging failure rate (per minute) |`PagingFailure` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Provisioned Subscribers<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |PccpId, SiteId |No|
|RAN Setup Failures<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |3gppGen, PccpId, SiteId, Cause |Yes|
|RAN Setup Requests<p><p>RAN setup reuests rate (per minute) |`RanSetupRequest` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|RAN Setup Responses<p><p>RAN setup response rate (per minute) |`RanSetupResponse` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Registered Subscribers<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Registered Subscribers Connected<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Registered Subscribers Idle<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Registration Attempts<p><p>Registration attempts rate (per minute) |`RegistrationAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Registration Failures<p><p>Registration failure rate (per minute) |`RegistrationFailure` |Count |Total |3gppGen, PccpId, SiteId, Result |Yes|
|Registration Successes<p><p>Registration success rate (per minute) |`RegistrationSuccess` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Service Request Attempts<p><p>Service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Service Request Failures<p><p>Service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |3gppGen, PccpId, SiteId, Result, Tai |Yes|
|Service Request Successes<p><p>Service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Session Establishment Attempts<p><p>PDU session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |3gppGen, PccpId, SiteId, Dnn |Yes|
|Session Establishment Failures<p><p>PDU session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |3gppGen, PccpId, SiteId, Dnn |Yes|
|Session Establishment Successes<p><p>PDU session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |3gppGen, PccpId, SiteId, Dnn |Yes|
|Session Releases<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|UE Context Release Commands<p><p>UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|UE Context Release Completes<p><p>UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|UE Context Release Requests<p><p>UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|User Plane Bandwidth<p><p>User plane bandwidth in bits/second. |`UserPlaneBandwidth` |BitsPerSecond |Total |PcdpId, SiteId, Direction, Interface |No|
|User Plane Packet Drop Rate<p><p>User plane packet drop rate (packets/sec) |`UserPlanePacketDropRate` |CountPerSecond |Total |PcdpId, SiteId, Cause, Direction, Interface |No|
|User Plane Packet Rate<p><p>User plane packet rate (packets/sec) |`UserPlanePacketRate` |CountPerSecond |Total |PcdpId, SiteId, Direction, Interface |No|
|Xn Handover Attempts<p><p>Handover attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Xn Handover Failures<p><p>Handover failure rate (per minute) |`XnHandoverFailure` |Count |Total |3gppGen, PccpId, SiteId |Yes|
|Xn Handover Successes<p><p>Handover success rate (per minute) |`XnHandoverSuccess` |Count |Total |3gppGen, PccpId, SiteId |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->