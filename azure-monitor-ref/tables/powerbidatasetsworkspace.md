---
title: Azure Monitor Logs reference - PowerBIDatasetsWorkspace
description: Reference for PowerBIDatasetsWorkspace table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# PowerBIDatasetsWorkspace

 Contains Analysis Services engine process events such as the start of a batch or transaction e.g. execute query, process partition. Typically used to monitor the performance, health and usage of Power BI's data engine. Contains information from the entire tenant.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Power BI Datasets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationContext | dynamic | Unique identifiers providing details about the context of the operation. E.g. Report ID, DatasetID. |
| ApplicationName | string | Contains the name of the client application that created the connection to the Power BI dataset. This is provided by the application and is optional. |
| ArtifactId | string | Unique ID of the resource logging the data. |
| ArtifactKind | string | Type of artifact logging the operation e.g. Dataset. |
| ArtifactName | string | The name of the Power BI artifact logging this operation. |
| CorrelationId | string | An event ID that can be used to correlated events between multiple tables. |
| CpuTimeMs | long | Amount of CPU time (in milliseconds) used by the operation. |
| CustomerTenantId | string | Unique identifier of the Power BI tenant. |
| DatasetMode | string | The mode of the dataset. Import, DirectQuery or Composite. |
| DurationMs | long | Amount of time (in milliseconds) taken by the operation. |
| EventText | string | Contains verbose information associated with operation e.g. DAX query. |
| ExecutingUser | string | The user executing the operation. |
| Identity | dynamic | Information about user and claims. |
| Level | string | Contains the severity level of the operation being logged. Success, Informational, Warning, or Error. |
| LogAnalyticsCategory | string | Unique category of the events like Audit/Security/Request. |
| OperationDetailName | string | Provides subcategories of OperationName. |
| OperationName | string | The operation associated with the log record. |
| PowerBIWorkspaceId | string | Unique identifier of the Power BI workspace that contains the artifact being operated on. |
| PowerBIWorkspaceName | string | Name of the Power BI workspace containing the artifact. |
| PremiumCapacityId | string | Unique identifier of the Premium capacity hosting the artifact being operated on. |
| ProgressCounter | long | Progress Counter. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Status of the operation. |
| StatusCode | int | Status code of the operation. It covers success and failure. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp(UTC) of when the log entry was generated. |
| Type | string | The name of the table |
| User | string | The user on whose behalf the operation is running. Used when an end user identity must be impersonated on the server. |
| XmlaObjectPath | string | A comma-separated list of parents, starting with the object's parent. |
| XmlaProperties | string | Properties of the XMLA request. |
| XmlaRequestId | string | Unique Identifier of request. |
| XmlaSessionId | string | Analysis services session identifier. |
