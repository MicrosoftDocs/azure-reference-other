---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Session Count**<br><br>Number of active PDU/PDN sessions |`ActiveSessionCount` |Count |Total |`3gppGen`, `SiteId`, `RanId`, `Dnn`|PT1M |No|
|Traffic|**Authentication Attempts**<br><br>4G/5G authentication attempts rate (per minute) |`AuthAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Authentication Failures**<br><br>4G/5G authentication failure rate (per minute) |`AuthFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|Traffic|**Authentication Successes**<br><br>4G/5G authentication success rate (per minute) |`AuthSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Connected NodeBs**<br><br>Number of connected gNodeBs or eNodeBs |`ConnectedNodebs` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Attempt**<br><br>Default Bearer Attach Attempt rate (per minute) |`DefaultBearerAttachAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Failure**<br><br>Default Bearer Attach Failure rate (per minute) |`DefaultBearerAttachFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Default Bearer Attach Success**<br><br>Default Bearer Attach Success rate (per minute) |`DefaultBearerAttachSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**DeRegistration Attempts**<br><br>Deregistration (5G) or detachment (4G) attempts rate (per minute) |`DeRegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**DeRegistration Successes**<br><br>Deregistration (5G) or detachment (4G) success rate (per minute) |`DeRegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Diameter Peer Request Received**<br><br>Diameter Peer Request Received rate (per minute) |`DiameterPeerRequestReceived` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`|PT1M |No|
|Traffic|**Diameter Peer Request Sent**<br><br>Diameter Peer Request Sent rate (per minute) |`DiameterPeerRequestSent` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`|PT1M |No|
|Traffic|**Diameter Peer Response Received**<br><br>Diameter Peer Response Received rate (per minute) |`DiameterPeerResponseReceived` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`, `ResultCode`|PT1M |No|
|Traffic|**Diameter Peer Response Sent**<br><br>Diameter Peer Response Sent rate (per minute) |`DiameterPeerResponseSent` |Count |Total |`3gppGen`, `SiteId`, `CommandCode`, `ResultCode`|PT1M |No|
|Traffic|**Initial Context Setup Failures**<br><br>4G/5G Initial Context Setup Failures message rate (per minute) |`InitialContextSetupFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Initial Context Setup Requests**<br><br>4G/5G Initial Context Setup Request message rate (per minute) |`InitialContextSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Initial Context Setup Responses**<br><br>4G/5G Initial Context Setup Response message rate (per minute) |`InitialContextSetupResponse` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Attempts**<br><br>N2Handover (5G) or s1Handover (4G) attempts rate (per minute) |`N2HandoverAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Failures**<br><br>N2Handover (5G) or s1Handover (4G) failure rate (per minute) |`N2HandoverFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**N2 Handover Successes**<br><br>N2Handover (5G) or s1Handover (4G) success rate (per minute) |`N2HandoverSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Paging Attempts**<br><br>4G/5G paging attempts rate (per minute) |`PagingAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Paging Failures**<br><br>4G/5G paging failure rate (per minute) |`PagingFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**PDU Resource Setup Request**<br><br>PDU Resource Setup Request rate (per minute) |`PDUResourceSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**PDU Resource Setup Response**<br><br>PDU Resource Setup Response rate (per minute) |`PDUResourceSetupResponse` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Provisioned Subscribers**<br><br>Number of provisioned subscribers |`ProvisionedSubscribers` |Count |Total |`SiteId`|PT1M |No|
|Traffic|**Radius Access Accept Received**<br><br>Radius Access Accept Received rate (per minute) |`RadiusAccessAcceptReceived` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Radius Access Reject Received**<br><br>Radius Access Reject Received rate (per minute) |`RadiusAccessRejectReceived` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Radius Access Request Send Failed**<br><br>Radius Access Request Send Failed rate (per minute) |`RadiusAccessRequestSendFailed` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Radius Access Request Sent**<br><br>Radius Access Request Sent rate (per minute) |`RadiusAccessRequestSent` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Radius Access Request Timeout**<br><br>Radius Access Request Timeout rate (per minute) |`RadiusAccessRequestTimeout` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**RAN Setup Failures**<br><br>RAN setup failure rate (per minute) |`RanSetupFailure` |Count |Total |`3gppGen`, `SiteId`, `Cause`|PT1M |No|
|Traffic|**RAN Setup Requests**<br><br>RAN setup request rate (per minute) |`RanSetupRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**RAN Setup Successes**<br><br>RAN setup success rate (per minute) |`RanSetupSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers**<br><br>Number of registered subscribers |`RegisteredSubscribers` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers Connected**<br><br>Number of registered and connected subscribers |`RegisteredSubscribersConnected` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registered Subscribers Idle**<br><br>Number of registered and idle subscribers |`RegisteredSubscribersIdle` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registration Attempts**<br><br>Registration (5G) or attachment (4G) attempts rate (per minute) |`RegistrationAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Registration Failures**<br><br>Registration (5G) or attachment (4G) failure rate (per minute) |`RegistrationFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`|PT1M |No|
|Traffic|**Registration Successes**<br><br>Registration (5G) or attachment (4G) success rate (per minute) |`RegistrationSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Service Request Attempts**<br><br>4G/5G service request attempts rate (per minute) |`ServiceRequestAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Service Request Failures**<br><br>4G/5G service request failure rate (per minute) |`ServiceRequestFailure` |Count |Total |`3gppGen`, `SiteId`, `Result`, `Tai`|PT1M |No|
|Traffic|**Service Request Successes**<br><br>4G/5G service request success rate (per minute) |`ServiceRequestSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Session Establishment Attempts**<br><br>PDU/PDN session establishment attempts rate (per minute) |`SessionEstablishmentAttempt` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|Traffic|**Session Establishment Failures**<br><br>PDU/PDN session establishment failure rate (per minute) |`SessionEstablishmentFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Session Establishment Successes**<br><br>PDU/PDN session establishment success rate (per minute) |`SessionEstablishmentSuccess` |Count |Total |`3gppGen`, `SiteId`, `Dnn`|PT1M |No|
|Traffic|**Session Releases**<br><br>Session release rate (per minute) |`SessionRelease` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Commands**<br><br>4G/5G UE context release command message rate (per minute) |`UeContextReleaseCommand` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Completes**<br><br>4G/5G UE context release complete message rate (per minute) |`UeContextReleaseComplete` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**UE Context Release Requests**<br><br>4G/5G UE context release request message rate (per minute) |`UeContextReleaseRequest` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Attempts**<br><br>XnHandover (5G) or X2Handover (4G) attempts rate (per minute) |`XnHandoverAttempt` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Failures**<br><br>XnHandover (5G) or X2Handover (4G) failure rate (per minute) |`XnHandoverFailure` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|
|Traffic|**Xn Handover Successes**<br><br>XnHandover (5G) or X2Handover (4G) success rate (per minute) |`XnHandoverSuccess` |Count |Total |`3gppGen`, `SiteId`|PT1M |No|