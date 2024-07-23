---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ThreatIntelIndicators
---


| Column | Type | Description |
|---|---|---|
| AdditionalFields | dynamic | The type specifc fields that Sentinel adds. Contains the TLPLevel: white, green, amber, or red. |
| AzureTenantId | string | The tenant that submitted the indicator. |
| _BilledSize | real | The record size in bytes |
| Confidence | int | The confidence that the creator has in the correctness of their data. The value must be a number in the range of 0-100. |
| Created | datetime | The date when the indicator was created. |
| Data | dynamic | All object properties, formatted according to the STIX specification (https://docs.oasis-open.org/cti/stix/v2.1/os/stix-v2.1-os.pdf). |
| Id | string | A value that uniquely identifies the indicator STIX object. This value is usable with Sentinel APIs. |
| IsActive | bool | A value that specifies if an indicator is active and valid for detections. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDeleted | bool | A value that indicates whether the data was deleted from Sentinel or not. |
| LastUpdateMethod | string | The component that last updated the indicator. |
| Modified | datetime | The date when the indicator was modified. |
| ObservableKey | string | The entire left-hand side of an equality comparison from the pattern. |
| ObservableValue | string | The entire right-hand side of an equality comparison from the pattern. |
| Pattern | string | The detection pattern for this indicator MAY be expressed as a STIX pattern. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Revoked | bool | A value that specifies whether the indicator was revoked. |
| Source | string | The name of the source. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Sentinel defined tags for the indicator. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time of indicator ingestion. |
| Type | string | The name of the table |
| ValidFrom | datetime | The time from which this indicator is considered a valid indicator of the behaviors it is related or represents. |
| ValidUntil | datetime | The time at which this indicator should no longer be considered a valid indicator of the bahviors it is related to or represents. |
| WorkspaceId | string | The workspace that submitted the indicator. |
