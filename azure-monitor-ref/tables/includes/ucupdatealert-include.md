---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: UCUpdateAlert
---


| Column | Type | Description |
|---|---|---|
| AlertClassification | string | Whether this Alert is an Error, a Warning, or Informational. |
| AlertData | string | An optional string formatted as a json payload containing metadata for the alert. |
| AlertId | string | The unique identifier of this Alert. |
| AlertRank | int | Integer ranking of Alert for prioritization during troubleshooting. |
| AlertStatus | string | Whether this Alert is Active, Resolved, or Deleted. |
| AlertSubtype | string | The Subtype of Alert. |
| AlertType | string | The type of Alert this is, ClientUpdateAlert, ServiceUpdateAlert. Indicates which fields will be present. |
| AzureADDeviceId | string | A GUID corresponding to the AAD Tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD Device ID. |
| _BilledSize | real | The record size in bytes |
| CatalogId | string | The update catalog ID. |
| ClientSubstate | string | If the Alert is from the Client, the ClientSubstate at the time thie Alert was activated or updated, else Empty. |
| ClientSubstateRank | int | Rank of ClientSubstate. |
| DeploymentId | string | The identifier of the Deployment that is targeting this update to this device, else empty. |
| Description | string | A localized string translated from a combination of other Alert fields + language preference that describes the issue in detail. |
| DeviceName | string | Device's given name. |
| ErrorCode | string | The Error Code, if any, that triggered this Alert. In the case of Client-based explicit alerts, error codes can have extended error codes, which are appended to the error code with a underscore separator. |
| ErrorSymName | string | The symbolic name that maps to the Error Code, if any. Otherwise empty. |
| GlobalDeviceId | string | Microsoft internal Global Device Identifier. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Recommendation | string | A localized string translated from RecommendedAction, Message, and other fields (depending on source of Alert) that provides a recommended action. |
| ResolvedTime | datetime | The time this alert was resolved, else empty. |
| SCCMClientId | string | A GUID corresponding to the SCCM Client ID on the device. |
| ServiceSubstate | string | Ranking of Client Substates for sequential ordering in funnel-type views. The rankings between ServiceSubstate and ClientSubstate can be used together. |
| ServiceSubstateRank | int | Rank of ServiceSubstate |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The time this alert was activated. |
| TargetBuild | string | The full build of the content this DeviceUpdateEvent is tracking. For Windows 10 updates, this would correspond to the full build (10.0.14393.385). |
| TargetVersion | string | The target OS Version - eg, 1909. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time at which this event is generated. |
| Type | string | The name of the table |
| UpdateCategory | string | The type of content this DeviceUpdateEvent is tracking. |
| UpdateClassification | string | Whether this content is an Upgrade (FU), Security (QU), NonSecurity (QU) |
| UpdateId | string | Update ID of the targeted update. |
| URL | string | An optional URL to get more in-depth information related to this alert. |
