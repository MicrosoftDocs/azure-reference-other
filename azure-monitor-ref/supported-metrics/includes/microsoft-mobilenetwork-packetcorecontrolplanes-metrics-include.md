---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/07/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Session Count**<p><p>Number of active PDU/PDN sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `SiteId`, `RanId`, `Dnn`|PT1M |No|
|Traffic|**Authentication Attempts**<p><p>4G/5G authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Authentication Failures**<p><p>4G/5G authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|Traffic|**Authentication Successes**<p><p>4G/5G authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Connected NodeBs**<p><p>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Attempt**<p><p>Default Bearer Attach Attempt rate (per minute) |`DefaultBearerAttachAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Failure**<p><p>Default Bearer Attach Failure rate (per minute) |`DefaultBearerAttachFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Success**<p><p>Default Bearer Attach Success rate (per minute) |`DefaultBearerAttachSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**DeRegistration Attempts**<p><p>Deregistration (5G) or detachment (4G) attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**DeRegistration Successes**<p><p>Deregistration (5G) or detachment (4G) success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Diameter Peer Request Received**<p><p>Diameter Peer Request Received rate (per minute) |`DiameterPeerRequestReceived` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`|PT1M |No|
|Traffic|**Diameter Peer Request Sent**<p><p>Diameter Peer Request Sent rate (per minute) |`DiameterPeerRequestSent` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`|PT1M |No|
|Traffic|**Diameter Peer Response Received**<p><p>Diameter Peer Response Received rate (per minute) |`DiameterPeerResponseReceived` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`, `ResultCode`|PT1M |No|
|Traffic|**Diameter Peer Response Sent**<p><p>Diameter Peer Response Sent rate (per minute) |`DiameterPeerResponseSent` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`, `ResultCode`|PT1M |No|
|Traffic|**Initial Context Setup Failures**<p><p>4G/5G Initial Context Setup Failures message rate (per minute) |`InitialContextSetupFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Initial Context Setup Requests**<p><p>4G/5G Initial Context Setup Request message rate (per minute) |`InitialContextSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Initial Context Setup Responses**<p><p>4G/5G Initial Context Setup Response message rate (per minute) |`InitialContextSetupResponse` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Attempts**<p><p>N2Handover (5G) or s1Handover (4G) attempts rate (per minute) |`N2HandoverAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Failures**<p><p>N2Handover (5G) or s1Handover (4G) failure rate (per minute) |`N2HandoverFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Successes**<p><p>N2Handover (5G) or s1Handover (4G) success rate (per minute) |`N2HandoverSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Paging Attempts**<p><p>4G/5G paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Paging Failures**<p><p>4G/5G paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**PDU Resource Setup Request**<p><p>PDU Resource Setup Request rate (per minute) |`PDUResourceSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**PDU Resource Setup Response**<p><p>PDU Resource Setup Response rate (per minute) |`PDUResourceSetupResponse` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Provisioned Subscribers**<p><p>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`SiteId`|PT1M |No|
|Traffic|**RAN Setup Failures**<p><p>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `SiteId`, `Cause`|PT1M |No|
|Traffic|**RAN Setup Requests**<p><p>RAN setup request rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**RAN Setup Successes**<p><p>RAN setup success rate (per minute) |`RanSetupSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers**<p><p>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers Connected**<p><p>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers Idle**<p><p>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registration Attempts**<p><p>Registration (5G) or attachment (4G) attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registration Failures**<p><p>Registration (5G) or attachment (4G) failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|Traffic|**Registration Successes**<p><p>Registration (5G) or attachment (4G) success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Service Request Attempts**<p><p>4G/5G service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Service Request Failures**<p><p>4G/5G service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`, `Tai`|PT1M |No|
|Traffic|**Service Request Successes**<p><p>4G/5G service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Session Establishment Attempts**<p><p>PDU/PDN session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|Traffic|**Session Establishment Failures**<p><p>PDU/PDN session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Session Establishment Successes**<p><p>PDU/PDN session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|Traffic|**Session Releases**<p><p>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Commands**<p><p>4G/5G UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Completes**<p><p>4G/5G UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Requests**<p><p>4G/5G UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Attempts**<p><p>XnHandover (5G) or X2Handover (4G) attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Failures**<p><p>XnHandover (5G) or X2Handover (4G) failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Successes**<p><p>XnHandover (5G) or X2Handover (4G) success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|