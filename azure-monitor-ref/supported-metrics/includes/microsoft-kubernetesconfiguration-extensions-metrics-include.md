---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.kubernetesconfiguration/extensions, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active PDU Sessions**<p><p>Number of Active PDU Sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |No|
|**Authentication Attempts**<p><p>Authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Authentication Failures**<p><p>Authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|**Authentication Successes**<p><p>Authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Connected NodeBs**<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**DeRegistration Attempts**<p><p>UE deregistration attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**DeRegistration Successes**<p><p>UE deregistration success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Paging Attempts**<p><p>Paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Paging Failures**<p><p>Paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Provisioned Subscribers**<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`PccpId`, `SiteId`|PT1M |No|
|**RAN Setup Failures**<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Cause`|PT1M |Yes|
|**RAN Setup Requests**<p><p>RAN setup reuests rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**RAN Setup Responses**<p><p>RAN setup response rate (per minute) |`RanSetupResponse` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Registered Subscribers**<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Registered Subscribers Connected**<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Registered Subscribers Idle**<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Registration Attempts**<p><p>Registration attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Registration Failures**<p><p>Registration failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|**Registration Successes**<p><p>Registration success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Service Request Attempts**<p><p>Service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Service Request Failures**<p><p>Service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`, `Tai`|PT1M |Yes|
|**Service Request Successes**<p><p>Service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Session Establishment Attempts**<p><p>PDU session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|**Session Establishment Failures**<p><p>PDU session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|**Session Establishment Successes**<p><p>PDU session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|**Session Releases**<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**UE Context Release Commands**<p><p>UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**UE Context Release Completes**<p><p>UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**UE Context Release Requests**<p><p>UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**User Plane Bandwidth**<p><p>User plane bandwidth in bits/second. |`UserPlaneBandwidth` |BitsPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|**User Plane Packet Drop Rate**<p><p>User plane packet drop rate (packets/sec) |`UserPlanePacketDropRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|**User Plane Packet Rate**<p><p>User plane packet rate (packets/sec) |`UserPlanePacketRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|**Xn Handover Attempts**<p><p>Handover attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Xn Handover Failures**<p><p>Handover failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|**Xn Handover Successes**<p><p>Handover success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|