---
title: Azure Monitor Logs reference - BehaviorAnalytics
description: Reference for BehaviorAnalytics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# BehaviorAnalytics

 This table stores the enriched events for Sentinel UEBA, providing behavior analytics over raw data.

## Categories

- Security
## Solutions

- Microsoft Sentinel UEBA




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionType | string | The specific type of action that triggered the event |
| ActivityInsights | dynamic | Activity and behavioral insights |
| ActivityType | string | The activity type that triggered the event |
| DestinationDevice | string | The hostname of the destination device |
| DestinationIPAddress | string | The destination IP address |
| DestinationIPLocation | string | The destination Geo location based on the IP address |
| DevicesInsights | dynamic | Devices metadata and insights |
| EventSource | string | Data source for this event |
| InvestigationPriority | int | Investigation priority score |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceDevice | string | The hostname of the source device |
| SourceIPAddress | string | The source IP address |
| SourceIPLocation | string | The source Geo location based on the IP address |
| SourceRecordId | string | The unique Id of the source raw event |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when the raw event was generated (UTC) |
| TimeProcessed | datetime | Time when enrichment processing occurred (UTC) |
| Type | string | The name of the table |
| UserName | string | User name of the account |
| UserPrincipalName | string | User principal name of the account |
| UsersInsights | dynamic | Users metadata and insights |
