---
title: Azure Monitor Logs reference - UCServiceUpdateStatus
description: Reference for UCServiceUpdateStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 1/13/2022
---

# UCServiceUpdateStatus

 Update Compliance - Update Event that comes directly from the service-side, and only tells the "service-side" of the story, for one device (client), and one update, in one deployment. As such, this event is stripped of certain fields in favor of being able to show data in near real-time.

## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AzureADDeviceId | string | A GUID corresponding to the AAD Tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD Device ID |
| DeploymentId | string | The identifier of the Deployment that is targeting this update to this device, else empty. |
| DeploymentIsExpedited | bool | Whether this content is being expedited by WUfB DS. |
| GlobalDeviceId | string | Microsoft internal Global Device Identifier |
| OfferReadyTime | datetime | DateTime of OfferReady transition. If empty, not yet been Offered. |
| ProjectedOfferReadyTime | datetime | Projected time update will be Offered to device. If empty, unknown.  |
| ServiceState | string | High-level state of update's status relative to device, service-side. |
| ServiceSubstate | string | Last-known state of this update relative to the device, from the client (the device's WDD). |
| ServiceSubstateRank | int | Ranking of Substates for sequential ordering in funnel-type views. The rankings between ServiceSubstate and ClientSubstate can be used together. |
| ServiceSubstateTime | datetime | DateTime of last ServiceSubstate transition. |
| SourceSystem | string |  |
| TargetBuild | string | The full build of the content this DeviceUpdateEvent is tracking. For Windows 10 updates, this would correspond to the full build (10.0.14393.385). |
| TargetVersion | string | The target OS Version - eg, 1909. |
| TenantId | string |  |
| TimeGenerated | datetime | Time at which this event is generated. |
| Type | string | The name of the table |
| UpdateCategory | string | The type of content this DeviceUpdateEvent is tracking. |
| UpdateClassification | string | Whether this content is an Upgrade (FU), Security (QU), NonSecurity (QU). |
| UpdateDisplayName | string | The long-form display name for the given update. Varies on content type (FU/QU). |
| UpdateManufacturer | string | Manufacturer of update. Microsoft for WU FU/QU, for D&F name of driver manufacturer e.g. NVIDIA. |
| UpdateReleaseTime | datetime | DateTime of update's release date. |
