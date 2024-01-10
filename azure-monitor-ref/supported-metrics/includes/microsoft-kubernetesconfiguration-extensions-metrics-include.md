---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.kubernetesconfiguration/extensions, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active PDU Sessions**<p><p>Number of Active PDU Sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |No|
|Traffic|**Authentication Attempts**<p><p>Authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Authentication Failures**<p><p>Authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|Traffic|**Authentication Successes**<p><p>Authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Connected NodeBs**<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**DeRegistration Attempts**<p><p>UE deregistration attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**DeRegistration Successes**<p><p>UE deregistration success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Paging Attempts**<p><p>Paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Paging Failures**<p><p>Paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Provisioned Subscribers**<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`PccpId`, `SiteId`|PT1M |No|
|Traffic|**RAN Setup Failures**<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Cause`|PT1M |Yes|
|Traffic|**RAN Setup Requests**<p><p>RAN setup reuests rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**RAN Setup Responses**<p><p>RAN setup response rate (per minute) |`RanSetupResponse` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers**<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers Connected**<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers Idle**<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registration Attempts**<p><p>Registration attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registration Failures**<p><p>Registration failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|Traffic|**Registration Successes**<p><p>Registration success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Service Request Attempts**<p><p>Service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Service Request Failures**<p><p>Service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`, `Tai`|PT1M |Yes|
|Traffic|**Service Request Successes**<p><p>Service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Session Establishment Attempts**<p><p>PDU session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Establishment Failures**<p><p>PDU session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Establishment Successes**<p><p>PDU session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Releases**<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Commands**<p><p>UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Completes**<p><p>UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Requests**<p><p>UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**User Plane Bandwidth**<p><p>User plane bandwidth in bits/second. |`UserPlaneBandwidth` |BitsPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**User Plane Packet Drop Rate**<p><p>User plane packet drop rate (packets/sec) |`UserPlanePacketDropRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|Traffic|**User Plane Packet Rate**<p><p>User plane packet rate (packets/sec) |`UserPlanePacketRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Xn Handover Attempts**<p><p>Handover attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Xn Handover Failures**<p><p>Handover failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Xn Handover Successes**<p><p>Handover success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|