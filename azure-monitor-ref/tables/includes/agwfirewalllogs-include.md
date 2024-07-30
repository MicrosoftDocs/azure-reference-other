---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AGWFirewallLogs
---


| Column | Type | Description |
|---|---|---|
| Action | string | Action taken on the request. Available values are Blocked and Allowed (for custom rules), Matched (when a rule matches a part of the request), and Detected and Blocked (these are both for mandatory rules, depending on if the WAF is in detection or prevention mode). |
| _BilledSize | real | The record size in bytes |
| ClientIp | string | Originating IP for the request. |
| ClientPort | int | Originating port for the request. |
| DetailedData | string | Specific data found in request that matched the rule for the triggered event. |
| DetailedMessage | string | Description of the rule for the triggered event. |
| FileDetails | string | Configuration file that contained the rule for the triggered event. |
| Hostname | string | Hostname or IP address of the Application Gateway. |
| InstanceId | string | Application Gateway instance for which firewall data is being generated. For a multiple-instance application gateway, there is one row per instance. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LineDetails | string | Line number in the configuration file that triggered the event. |
| Message | string | User-friendly message for the triggering event. More details are provided in the details section. |
| OperationName | string | Name of the operation. |
| RequestUri | string | URL of the received request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleId | string | Rule ID of the triggering event. |
| RuleSetType | string | Rule set type. The available value is OWASP. |
| RuleSetVersion | string | Rule set version used. Available values are 2.2.9 and 3.0. |
| Site | string | Site for which the log was generated. Currently, only Global is listed because rules are global. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| TransactionId | string | Unique ID for a given transaction which helps group multiple rule violations that occurred within the same request. |
| Type | string | The name of the table |
