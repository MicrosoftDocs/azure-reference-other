---
title: Azure Monitor Logs reference - UCClientUpdateStatus
description: Reference for UCClientUpdateStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# UCClientUpdateStatus

 Update Compliance - Update Event that combines the latest client-based data with the latest service-based data to create a complete picture for one device (client) and one update.

## Solutions

- LogManagement
- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AzureADDeviceId | string | A GUID corresponding to the AAD Tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD Device ID. |
| CatalogId | string | The update catalog ID. |
| ClientState | string | Higher-level bucketization of ClientSubstate. |
| ClientSubstate | string | Last-known state of this update relative to the device, from the client (the device's WDD). |
| ClientSubstateRank | int | Ranking of Client Substates for sequential ordering in funnel-type views. The rankings between ServiceSubstate and ClientSubstate can be used together. |
| ClientSubstateTime | datetime | DateTime of last Client Substate transition. |
| DeploymentId | string | The identifier of the Deployment that is targeting this update to this device, else empty. |
| DeviceName | string | Device's given name. |
| EventData | string | Json to fill with arbitrary K/V pairs. Used to populate contextual data that would otherwise be sparsely populated if elevated to a field always present in the schema.  |
| FurthestClientSubstate | string | Furthest clientSubstate. |
| FurthestClientSubstateRank | int | Ranking of furthest clientSubstate. |
| GlobalDeviceId | string | Microsoft internal Global Device Identifier |
| IsUpdateHealthy | bool | True: No issues preventing this device from updating to this update have been found. False: There is something that may prevent this device from updating. |
| OfferReceivedTime | datetime | DateTime when device last reported entering OfferReceived, else empty. |
| RestartRequiredTime | datetime | DateTime when device first reported entering RebootRequired (or RebootPending), else empty. |
| SCCMClientId | string | A GUID corresponding to the SCCM Client ID on the device. |
| SourceSystem | string |  |
| TargetBuild | string | The full build of the content this DeviceUpdateEvent is tracking. For Windows 10 updates, this would correspond to the full build (10.0.14393.385). |
| TargetBuildNumber | int | Integer of the Major portion of Build. |
| TargetKBNumber | string | KB Article. |
| TargetRevisionNumber | int | Integer or the Minor (or Revision) portion of Build. |
| TargetVersion | string | The target OS Version - eg, 1909. |
| TenantId | string |  |
| TimeGenerated | datetime | The time the snapshot generated this specific record. |
| Type | string | The name of the table |
| UpdateCategory | string | The type of content this DeviceUpdateEvent is tracking. |
| UpdateClassification | string | Whether this content is an Upgrade (FU), Security (QU), NonSecurity (QU). |
| UpdateConnectivityLevel | string | Whether or not this device is maintaining a sufficiently cumulative and continuous connection to Windows Update so the update can progress optimally.  |
| UpdateDisplayName | string | The long-form display name for the given update. Varies on content type (FU/QU). |
| UpdateHealthGroupL1 | string | Grouping design to describe the current update installation's "health", L1 (highest-level). |
| UpdateHealthGroupL2 | string | Second grouping, subset of L1, more detailed. |
| UpdateHealthGroupL3 | string | Third grouping, subset of L3, more detailed. |
| UpdateHealthGroupRankL1 | int | Integer for ranking the L1 UpdateHealthGroup. |
| UpdateHealthGroupRankL2 | int | Integer for ranking the L2 UpdateHealthGroup. |
| UpdateHealthGroupRankL3 | int | Integer for ranking the L3 UpdateHealthGroup. |
| UpdateId | string | Update ID of the targeted update. |
| UpdateInstalledTime | datetime | DateTime when event transitioned to UpdateInstalled, else empty. |
| UpdateManufacturer | string | Manufacturer of update. Microsoft for WU FU/QU, for D&F name of driver manufacturer e.g. NVIDIA. |
| UpdateReleaseTime | datetime | The release date of the update. |
| UpdateSource | string | The source of the update - UUP, MUv6, Media. |
