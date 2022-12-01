---
title: Azure Monitor Logs reference - PowerBIReportUsageTenant
description: Reference for PowerBIReportUsageTenant table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# PowerBIReportUsageTenant

 Contains usage metric logs for open report and change report page for the workspaces on tenant level. Typically used to monitor usage of Power BI workspaces for customer tenant.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Power BI Datasets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ArtifactId | string | Report unique identifier. |
| ArtifactKind | string | Type of artifact this entry describe. |
| ArtifactName | string | Report friendly name. As at time of event being raised. |
| BootstrapDurationMs | long | The duration of Power BI application initialization in milliseconds. |
| BrowserName | string | Name of the browser used to view the report. |
| BrowserTabId | string | Unique identifier of the browser tab used to view the report. |
| BrowserVersion | string | Browser version number. |
| CallerIpAddress | string | IP address of the user machine initiating the activity. |
| ClientVersion | string | Version number of the Power BI client (where applicable). |
| ConsumptionMethod | string | Describes the method used to consume the content such as Power BI Web App. |
| CorrelationId | string | Root activity ID. Will be replaced by correlation vector in future. |
| CustomerTenantId | string | Customer Tenant ID where the operation was performed. |
| DatasetId | string | Dataset unique identifier. |
| DatasetLocation | string | What infrastrcure is the phsyical SSAS dataset hosted on. |
| DatasetMode | string | What type of SSAS data model is it i.e. Import/DirectQuery/Composite. |
| DatasetName | string | Dataset friendly name. As at time of event being raised. |
| DistributionMethod | string | For report views which distribution method did the user leverage to access it. |
| DurationMs | long | How long did the entire operation take from start to finish in milliseconds. |
| EffectiveDAXQueryDurationMs | long | What was the DAX query duration from First query start to Last Query end in milliseconds. Applies to all model types. |
| EffectiveDQQueryDurationMs | long | For DQ sources what was the DQ query duration from First query start to Last query end in milliseconds. |
| EffectiveRenderDurationMs | long | For reports what was the report render duration excluding bootstrap time in milliseconds. |
| EffectiveVisualLoadDurationMs | long | For reports what was the visual loading duration from first visual start to last visual end in milliseconds. |
| EmbedAppId | string | For PaaS embed the GUID of the application registered with Azure AD which hosts the Power BI content. |
| EmbedType | string | For embedded reports which method was used to embed the content. |
| ExecutingUser | string | UserPrincipalName of the user executing/using the artifact. Can be impersonated. |
| HomeWorkspaceId | string | For app and direct share report cases the unique identifier of the workspace hosting the dataset that powers the report. |
| HomeWorkspaceName | string | For app and direct share report cases the name of the workspace hosting the dataset that powers the report. |
| Identity | dynamic | User and claim details. |
| IsBootstrapIncluded | bool | For report view events shows whether the operation incurs application bootstrapping to initialize Power BI before the report load. |
| IsQueryResultCacheEnabled | bool | For models on Premium capacities shows whether Query Result Caching enabled. |
| Level | string | Log classification indicating if the entry is informational or represents a warning or error state. |
| LogAnalyticsCategory | string | Category of the operation being logged. |
| OperatingSystemName | string | Operating System name. |
| OperatingSystemVersion | string | Operating System version number. |
| OperationEndTimestamp | datetime | End timestamp for the reported operation applicable to operations with an absolute duration. UTC date time value in RFC3339 format. |
| OperationName | string | The operation associated with the log record. |
| OperationStartTimestamp | datetime | Start timestamp for the reported operations applicable to operations with an absolute duration. UTC date time value in RFC3339 format. |
| OperationVersion | string | This is the version of the event. |
| PowerBIAppId | string | Unique identifier of the Power BI App if a report was viewed through the app. |
| PowerBIAppName | string | Name of the Power BI App if a report was viewed through the app. |
| PowerBIWorkspaceId | string | PowerBI workspace unique identifier - the workspace containing the artifact. |
| PowerBIWorkspaceName | string | Friendly name of the Power BI workspace containing the artifact as at the time when the event was raised. |
| PremiumCapacityId | string | Premium capacity unique identifier. |
| Region | string | Azure region containing the artifact reporting the event. Typically the value shown in the About screen in the service under \"Your data is stored in:\" |
| ReportPageId | string | Power BI Interactive Report page/section unique identifier. |
| ReportPageName | string | Power BI Interactive Report page friendly name. As at time of event being raised. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Status of the operation. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp(UTC) of when the log entry was generated. |
| TotalDAXQueryDurationMs | long | Sum of all DAX query durations in milliseconds. Applies to all model types. |
| TotalDQQueryDurationMs | long | For DQ Sources sum of all DQ query durations in milliseconds. |
| TotalVisibleVisualCount | int | For reports how many total visuals were on the page that was viewed. Excludes hidden visuals. |
| Type | string | The name of the table |
| UserAgent | string | Information the client sends to the server typically contains operating system and client browser details. |
| UserFirstName | string | The first name of the top level user principal that initiated the action. |
| UserLastName | string | The last name of the top level user principal that initiated the action. |
| UserSession | string | Unique identifier of the user session. |
| VisualTypesAndCounts | string | For reportswhich visuals were on the page that was viewed and how many. Includes Custom visuals. |
