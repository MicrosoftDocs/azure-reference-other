---
title: Azure Monitor Logs reference - PowerBIDatasetsWorkspacePreview
description: Reference for PowerBIDatasetsWorkspacePreview table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# PowerBIDatasetsWorkspacePreview

 Contains Analysis Services engine process events such as the start of a batch or transaction e.g. execute query, process partition. Typically used to monitor the performance, health and usage of Power BI's data engine. Contains information per workspace.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationContext | string | Property bag of unique identifiers providing details about the application executing the request. E.g. report ID. |
| ApplicationName | string | Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program. |
| ClientHostName | string | The name of the computer on which the client application is running. This column is populated with the values passed by the client application. |
| ClientProcessId | string | Contains the process ID of the client application. |
| ConnectionId | string | Unique identifier of the connection. |
| CPUTime | long | Amount of CPU time (in milliseconds) used by the event. |
| CustomerTenantId | string | Unique identifier of the Power BI tenant. |
| DatabaseName | string | Contains the name of the database in which the query is running. |
| Duration | long | Amount of time (in milliseconds) taken by the event. |
| EffectiveUsername | string | The user on whose behalf the operation is running. Used when an end user identity must be impersonated on the server. |
| Error | string | Contains the error number of any error associated with the event. |
| EventClass | string | Event Class is used to categorize events. |
| EventSubclass | string | Event Subclass provides additional information about each event class. |
| IntegerData | long | Contains the integer data associated with the reported event, such as the current count of the number of rows processed for a processing event. |
| ObjectId | string | Contains the object ID associated with the reported event. |
| ObjectName | string | The name of the object for which the event occurred. |
| ObjectPath | string | Object path. A comma-separated list of parents, starting with the object's parent. |
| ObjectReference | string | Object reference. Encoded as XML for all parents, using tags to describe the object. |
| ObjectType | int | Identifies the type of object associated with a particular lock. For example, a lock timeout on a database will indicate the object type 100002, which is the Database object type. |
| OperationName | string | The operation associated with log record. |
| PremiumCapacityId | string | Unique identifier of the Premium capacity being operated on. |
| ProgressTotal | long | An integer representing how many rows have been processed in the current operation at a point in time. |
| RequestParameters | string | Contains the parameters for parameterized queries and commands associated with the event. |
| RequestProperties | string | Contains the properties of the XMLA request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | Unique Identifier of request |
| SessionId | string | Unique identifier of a session which represents multiple transactions occurring within the same scope e.g. Sharing calculated members. |
| Severity | string | Contains the severity level of an exception associated with the command event. Values are: 0 = Success, 1 = Informational, 2 = Warning, 3 = Error. |
| SourceSystem | string |  |
| SpId | int | Server process ID. This uniquely identifies a user session. This directly corresponds to the session GUID used by XML/A. |
| StartTime | datetime | Contains the time at which the event started, when available. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Success | string | Indicates if the operation was successful. 1 = success. 0 = failure. |
| TenantId | string |  |
| TextData | string | Contains verbose information associated with the event |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| WorkspaceId | string | Unique identifier of the workspace being operated on. |
