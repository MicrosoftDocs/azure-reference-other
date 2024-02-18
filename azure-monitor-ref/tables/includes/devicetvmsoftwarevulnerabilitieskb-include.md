---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceTvmSoftwareVulnerabilitiesKB
---


| Column | Type | Description |
|---|---|---|
| AffectedSoftware | dynamic | List of all software products affected by the vulnerability. |
| _BilledSize | real | The record size in bytes |
| CveId | string | Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system. |
| CvssScore | real | Severity score assigned to the security vulnerability under the Common Vulnerability Scoring System (CVSS). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsExploitAvailable | bool | Indicates whether exploit code for the vulnerability is publicly available. |
| LastModifiedTime | datetime | Date and time the item or related metadata was last modified. |
| PublishedDate | datetime | Date vulnerability was disclosed to the public. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Timestamp | datetime | Date and time when the record was generated |
| Type | string | The name of the table |
| VulnerabilityDescription | string | Description of the vulnerability and associated risks. |
| VulnerabilitySeverityLevel | string | Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape. |
