---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Session Count**<p><p>Number of active PDU/PDN sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `SiteId`, `RanId`, `Dnn`|PT1M |No|
|**Authentication Attempts**<p><p>4G/5G authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Authentication Failures**<p><p>4G/5G authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|**Authentication Successes**<p><p>4G/5G authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Connected NodeBs**<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**DeRegistration Attempts**<p><p>Deregistration (5G) or detachment (4G) attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**DeRegistration Successes**<p><p>Deregistration (5G) or detachment (4G) success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Paging Attempts**<p><p>4G/5G paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Paging Failures**<p><p>4G/5G paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Provisioned Subscribers**<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`SiteId`|PT1M |No|
|**RAN Setup Failures**<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `SiteId`, `Cause`|PT1M |No|
|**RAN Setup Requests**<p><p>RAN setup request rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**RAN Setup Successes**<p><p>RAN setup success rate (per minute) |`RanSetupSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Registered Subscribers**<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Registered Subscribers Connected**<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Registered Subscribers Idle**<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Registration Attempts**<p><p>Registration (5G) or attachment (4G) attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Registration Failures**<p><p>Registration (5G) or attachment (4G) failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|**Registration Successes**<p><p>Registration (5G) or attachment (4G) success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Service Request Attempts**<p><p>4G/5G service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Service Request Failures**<p><p>4G/5G service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`, `Tai`|PT1M |No|
|**Service Request Successes**<p><p>4G/5G service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Session Establishment Attempts**<p><p>PDU/PDN session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|**Session Establishment Failures**<p><p>PDU/PDN session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Session Establishment Successes**<p><p>PDU/PDN session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|**Session Releases**<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**UE Context Release Commands**<p><p>4G/5G UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**UE Context Release Completes**<p><p>4G/5G UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**UE Context Release Requests**<p><p>4G/5G UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Xn Handover Attempts**<p><p>XnHandover (5G) or X2Handover (4G) attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Xn Handover Failures**<p><p>XnHandover (5G) or X2Handover (4G) failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|**Xn Handover Successes**<p><p>XnHandover (5G) or X2Handover (4G) success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|