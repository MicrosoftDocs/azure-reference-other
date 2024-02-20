---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceTvmSecureConfigurationAssessment
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ConfigurationCategory | string | Category or grouping to which the configuration belongs |
| ConfigurationId | string | Unique identifier for a specific configuration |
| ConfigurationImpact | real | Rated impact of the configuration to the overall configuration score (1-10) |
| ConfigurationSubcategory | string | Subcategory or subgrouping to which the configuration belongs. In many cases, this describes specific capabilities or features. |
| Context | dynamic | Machine data configuration context |
| DeviceId | string | Unique identifier for the device in the service |
| DeviceName | string | Fully qualified domain name (FQDN) of the device |
| IsApplicable | bool | Indicates whether the configuration or policy is applicable |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsCompliant | bool | Indicates whether the configuration or policy is properly configured |
| IsExpectedUserImpact | bool | Indicates if user impact is expected when configuration applied |
| OSPlatform | string | Platform of the operating system running on the device. This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7 |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when the record was generated |
| Timestamp | datetime | Date and time when the record was generated |
| Type | string | The name of the table |
