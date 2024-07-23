---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ThreatIntelObjects
---


| Column | Type | Description |
|---|---|---|
| AdditionalFields | dynamic | The type specifc fields that Sentinel adds. Contains the TLPLevel: white, green, amber, or red. |
| AzureTenantId | string | The tenant that submitted the STIX object. |
| _BilledSize | real | The record size in bytes |
| Data | dynamic | All object properties, formatted according to STIX specification (https://docs.oasis-open.org/cti/stix/v2.1/os/stix-v2.1-os.pdf). |
| Id | string | A value that uniquely identifies the STIX object. This value is usable with Sentinel APIs. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDeleted | bool | A value that indicates whether the data was deleted from Sentinel or not. |
| LastUpdateMethod | string | The component that last updated the record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The name of the source. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StixType | string | The name of this STIX Object. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time of STIX object ingestion. |
| Type | string | The name of the table |
| WorkspaceId | string | The workspace that submitted the STIX object. |
