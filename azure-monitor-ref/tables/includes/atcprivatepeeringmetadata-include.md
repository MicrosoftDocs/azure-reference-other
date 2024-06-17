---
ms.service: azure-monitor
ms.topic: include
ms.date: 06/17/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ATCPrivatePeeringMetadata
---


| Column | Type | Description |
|---|---|---|
| ATCRegion | string | Azure Traffic Collector (ATC) deployment region. |
| ATCResourceId | string | Azure resource ID of Azure Traffic Collector (ATC). |
| _BilledSize | real | The record size in bytes |
| ExRCircuitId | string | Azure resource ID of Express Route Circuit. |
| ExRCircuitServiceKey | string | Service key of Express Route Circuit. |
| IpMask | int | Mask of Virtual Network resource. |
| IpSubnet | dynamic | Azure resource ID of subnet and subnet IP address. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The specific Azure Traffic Collector (ATC) operation that emitted this record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string | Flow record schema version. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the Azure Traffic Collector (ATC) emitted this record. |
| Type | string | The name of the table |
| VnetAddressPrefix | string | IP address of Virtual Network resource. |
| VnetId | string | Azure resource ID of Virtual Network. |
| VnetLocation | string | Azure region of Virtual Network resource. |
| VnetName | string | Virtual Network resource name. |
| VnetResourceGroup | string | Azure resource group of Virtual Network. |
| VnetSubscriptionId | string | Azure subscription ID of Virtual Network. |
