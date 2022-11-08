---
title: Azure Monitor Logs reference - AppServiceServerlessSecurityPluginData
description: Reference for AppServiceServerlessSecurityPluginData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AppServiceServerlessSecurityPluginData

 Logs from the data collection services of the defender for serverless apps. Used to detect security issues and provide alerts and recommendations on how to mitigate/fix them.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Index | int | Available when multiple payloads exist for the same message. In that case, payloads share the same SlSecRequestId and Index defines the chronological order of payloads. |
| MsgVersion | string | The version of the message schema. Used to make code changes backward- and forward- compatible. |
| Payload | dynamic | An array of messages, where each one is a JSON string. |
| PayloadType | string | The type of the payload. Mostly used to distinguish between messages meant for different types of security analysis. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Sender | string | The name of the component that published this message. Almost always will be the name of the plugin, but can also be platform. |
| SlSecMetadata | dynamic | Contains details about the resource like the deployment ID, runtime info, website info, OS, etc. |
| SlSecProps | dynamic | Contains other details that might be needed for debugging end-to-end requests, e.g., slsec nuget version. |
| SlSecRequestId | string | The ingestion request ID used for identifying the message and the request for diagnostics and debugging. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time (UTC) this message was created on the node. |
| Type | string | The name of the table |
