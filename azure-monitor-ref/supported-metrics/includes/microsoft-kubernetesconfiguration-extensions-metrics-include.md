---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.kubernetesconfiguration/extensions, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active PDU Sessions**<br><br>Number of Active PDU Sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |No|
|Traffic|**Authentication Attempts**<br><br>Authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Authentication Failures**<br><br>Authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|Traffic|**Authentication Successes**<br><br>Authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Connected NodeBs**<br><br>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**DeRegistration Attempts**<br><br>UE deregistration attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**DeRegistration Successes**<br><br>UE deregistration success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Paging Attempts**<br><br>Paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Paging Failures**<br><br>Paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Provisioned Subscribers**<br><br>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`PccpId`, `SiteId`|PT1M |No|
|Traffic|**RAN Setup Failures**<br><br>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Cause`|PT1M |Yes|
|Traffic|**RAN Setup Requests**<br><br>RAN setup reuests rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**RAN Setup Responses**<br><br>RAN setup response rate (per minute) |`RanSetupResponse` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers**<br><br>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers Connected**<br><br>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registered Subscribers Idle**<br><br>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registration Attempts**<br><br>Registration attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Registration Failures**<br><br>Registration failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`|PT1M |Yes|
|Traffic|**Registration Successes**<br><br>Registration success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Service Request Attempts**<br><br>Service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Service Request Failures**<br><br>Service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Result`, `Tai`|PT1M |Yes|
|Traffic|**Service Request Successes**<br><br>Service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Session Establishment Attempts**<br><br>PDU session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Establishment Failures**<br><br>PDU session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Establishment Successes**<br><br>PDU session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`, `Dnn`|PT1M |Yes|
|Traffic|**Session Releases**<br><br>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Commands**<br><br>UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Completes**<br><br>UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**UE Context Release Requests**<br><br>UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**User Plane Bandwidth**<br><br>User plane bandwidth in bits/second. |`UserPlaneBandwidth` |BitsPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**User Plane Packet Drop Rate**<br><br>User plane packet drop rate (packets/sec) |`UserPlanePacketDropRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|Traffic|**User Plane Packet Rate**<br><br>User plane packet rate (packets/sec) |`UserPlanePacketRate` |CountPerSecond |Total |`PcdpId`, `SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Xn Handover Attempts**<br><br>Handover attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Xn Handover Failures**<br><br>Handover failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|
|Traffic|**Xn Handover Successes**<br><br>Handover success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `PccpId`, `SiteId`|PT1M |Yes|