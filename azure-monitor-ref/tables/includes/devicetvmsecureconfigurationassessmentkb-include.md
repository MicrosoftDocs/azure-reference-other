---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceTvmSecureConfigurationAssessmentKB
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ConfigurationBenchmarks | dynamic | List of industry benchmarks which recommend the same or similar configuration. |
| ConfigurationCategory | string | Category or grouping to which the configuration belongs. |
| ConfigurationDescription | string | Description of the configuration. |
| ConfigurationId | string | Unique identifier for a specific configuration. |
| ConfigurationImpact | real | Rated impact of the configuration to the overall configuration score (1-10). |
| ConfigurationName | string | Display name of the configuration. |
| ConfigurationSubcategory | string | Subcategory or subgrouping to which the configuration belongs. Commonly, this describes specific capabilities or features. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| RelatedMitreTactics | dynamic | Related tactics from Mitre knowledge base. |
| RelatedMitreTechniques | dynamic | Related techniques from Mitre knowledge base. |
| RemediationOptions | string | Recommended actions to reduce or address any associated risks |
| RiskDescription | string | Description of any associated risks. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Tags | dynamic | Labels representing various attributes, used to identify or categorize a security configuration. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Timestamp | datetime | Date and time when the record was generated |
| Type | string | The name of the table |
