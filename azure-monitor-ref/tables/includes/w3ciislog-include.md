---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: W3CIISLog
---


| Column | Type | Description |
|---|---|---|
| AzureDeploymentID | string | Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent  when data is pulled from Azure storage. |
| _BilledSize | real | The record size in bytes |
| cIP | string | IP address of the client that accessed the web server. |
| Computer | string | Name of the computer that the event was collected from. |
| Confidence | string | Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension. |
| csBytes | long | Number of bytes that the server received. |
| csCookie | string | Content of the cookie sent or received if any. |
| csHost | string | Host header name if any. |
| csMethod | string | Method of the request such as GET or POST. |
| csReferer | string | Site that the user last visited. This site provided a link to the current site. |
| csUriQuery | string | The query if any that the client was trying to perform. A Universal Resource Identifier (URI) query is necessary only for dynamic pages. |
| csUriStem | string | Target of the action such as a web page for example Default.htm. |
| csUserAgent | string | Browser type of the client. |
| csUserName | string | Name of the authenticated user that accessed the server. Anonymous users are indicated by a hyphen. |
| csVersion | string | Protocol version that the client used. |
| Description | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| FirstReportedDateTime | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| IndicatorThreatType | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| IsActive | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastReportedDateTime | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| MaliciousIP | string | Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension). |
| ManagementGroupName | string | Name of the management group for Operations Manager agents. For other agents this is AOI-\<workspace ID\>. |
| RemoteIPCountry | string | Country/region of the IP address of the client. |
| RemoteIPLatitude | real | Latitude of the client IP address. |
| RemoteIPLongitude | real | Longitude of the client IP address. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Role instance of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and data is pulled from Azure storage. |
| RoleInstance | string | Role of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and data is pulled from Azure storage. |
| scBytes | long | Number of bytes that the server sent. |
| scStatus | string | HTTP status code. |
| scSubStatus | string | Substatus error code. |
| scWin32Status | string | Windows status code. |
| Severity | int | Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension. |
| sIP | string | IP address of the server on which the log file entry was generated. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| sPort | int | Server port number that is configured for the service. |
| sSiteName | string | Name of the IIS site. |
| StorageAccount | string | Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TimeTaken | long | Length of time to process the request in milliseconds. |
| TLPLevel | string | Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension. |
| Type | string | The name of the table |
