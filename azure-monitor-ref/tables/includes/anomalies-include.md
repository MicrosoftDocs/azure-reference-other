---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Anomalies
---


| Column | Type | Description |
|---|---|---|
| ActivityInsights | dynamic | Insights about the activites corresponding to the generated anomaly as JSON. |
| AnomalyDetails | dynamic | JSON object containing general information about the rule and algorithm that generated the anomaly as well as explanations for the anomaly. |
| AnomalyReasons | dynamic | The detailed explanation of the generated anomaly as JSON. |
| AnomalyTemplateId | string | The ID of the Anomaly template that generated this anomaly. |
| AnomalyTemplateName | string | The name of the Anomaly template that generated this anomaly. |
| AnomalyTemplateVersion | string | The version of the Anomaly template that generated this anomaly. |
| _BilledSize | real | The record size in bytes |
| Description | string | The description of the anomaly. |
| DestinationDevice | string | The destination device for which the anomaly was generated. |
| DestinationIpAddress | string | The destination ip address for which the anomaly was generated. |
| DestinationLocation | dynamic | Info about the destination location for which the anomaly was generated as JSON. |
| DeviceInsights | dynamic | Insights about the devices corresponding to the generated anomaly as JSON. |
| EndTime | datetime | The time (UTC) when the anomaly ended. |
| Entities | dynamic | JSON object containing all entities involved in the generated anomaly. |
| ExtendedLinks | dynamic | List of links pointing to the data that generated the anomaly. |
| ExtendedProperties | dynamic | JSON object with additional data on the anomaly as key-value pairs. |
| Id | string | The ID of the generated anomaly. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| RuleConfigVersion | string | The configuration version of the Anomaly analytics rule that generated this anomaly. |
| RuleId | string | The ID of the Anomaly analytics rule that generated this anomaly. |
| RuleName | string | The name of the Anomaly analytics rule that generated this anomaly. |
| RuleStatus | string | The status (Flighting/Production) of the Anomaly analytics rule that generated this anomaly. |
| Score | real | The score of the anomaly. |
| SourceDevice | string | The source device for which the anomaly was generated. |
| SourceIpAddress | string | The source ip address for which the anomaly was generated. |
| SourceLocation | dynamic | Info about the source location for which the anomaly was generated as JSON. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The time (UTC) when the anomaly started. |
| Tactics | string | List of MITRE ATT&CK tactics (strings) corresponding to the anomaly. |
| Techniques | string | List MITRE ATT&CK techniques (strings) corresponding to the anomaly. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the anomaly was generated. |
| Type | string | The name of the table |
| UserInsights | dynamic | Insights about the users corresponding to the generated anomaly as JSON. |
| UserName | string | The username for which the anomaly was generated. |
| UserPrincipalName | string | The UPN of the user for which the anomaly was generated. |
| VendorName | string | The name of the vendor that generated this anomaly. |
| WorkspaceId | string | The ID of the Sentinel workspace. |
