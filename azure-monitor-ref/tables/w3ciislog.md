---
title: Azure Monitor Logs reference - W3CIISLog
description: Reference for W3CIISLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# W3CIISLog

 Internet Information Server (IIS) log on Windows computers using the Log Analytics agent.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|Type of agent the event was collected from. Possible values are OpsManager and AzureStorage.|
|TimeGenerated|datetime|Date and time the record was created.|
|sSiteName|string|Name of the IIS site.|
|sIP|string|IP address of the server on which the log file entry was generated.|
|csMethod|string|Method of the request such as GET or POST.|
|csUriStem|string|Target of the action such as a web page for example Default.htm.|
|csUriQuery|string|The query if any that the client was trying to perform. A Universal Resource Identifier (URI) query is necessary only for dynamic pages.|
|sPort|int|Server port number that is configured for the service.|
|csUserName|string|Name of the authenticated user that accessed the server. Anonymous users are indicated by a hyphen.|
|cIP|string|IP address of the client that accessed the web server.|
|csVersion|string|Protocol version that the client used.|
|csUserAgent|string|Browser type of the client.|
|csCookie|string|Content of the cookie sent or received if any.|
|csReferer|string|Site that the user last visited. This site provided a link to the current site.|
|csHost|string|Host header name if any.|
|scStatus|string|HTTP status code.|
|scSubStatus|string|Substatus error code.|
|scWin32Status|string|Windows status code.|
|scBytes|long|Number of bytes that the server sent.|
|csBytes|long|Number of bytes that the server received.|
|TimeTaken|long|Length of time to process the request in milliseconds.|
|Computer|string|Name of the computer that the event was collected from.|
|ManagementGroupName|string|Name of the management group for Operations Manager agents. For other agents this is AOI-<workspace ID>.|
|MaliciousIP|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|IndicatorThreatType|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|Description|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|TLPLevel|string|Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension.|
|Confidence|string|Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension.|
|Severity|int|Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension.|
|FirstReportedDateTime|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|LastReportedDateTime|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|IsActive|string|Only populated for IIS logs collected from Azure Cloud Services (through Azure Diagnostics Extension).|
|RemoteIPLongitude|real|Longitude of the client IP address.|
|RemoteIPLatitude|real|Latitude of the client IP address.|
|RemoteIPCountry|string|Country/region of the IP address of the client.|
|StorageAccount|string|Only populated for IIS logs collected from Azure Cloud Services through Azure Diagnostics Extension.|
|AzureDeploymentID|string|Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent  when data is pulled from Azure storage.|
|Role|string|Role instance of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and data is pulled from Azure storage.|
|RoleInstance|string|Role of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and data is pulled from Azure storage.|
|Type|string||
|_ResourceId|string||
