---
title: Azure Monitor Logs reference - AWSCloudTrail
description: Reference for AWSCloudTrail table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AWSCloudTrail

 

## Categories

- Security
## Solutions

- SecurityInsights




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime||
|AwsEventId|string||
|EventVersion|string||
|EventSource|string||
|EventTypeName|string||
|EventName|string||
|UserIdentityType|string||
|UserIdentityPrincipalid|string||
|UserIdentityArn|string||
|UserIdentityAccountId|string||
|UserIdentityInvokedBy|string||
|UserIdentityAccessKeyId|string||
|UserIdentityUserName|string||
|SessionMfaAuthenticated|bool||
|SessionCreationDate|datetime||
|SessionIssuerType|string||
|SessionIssuerPrincipalId|string||
|SessionIssuerArn|string||
|SessionIssuerAccountId|string||
|SessionIssuerUserName|string||
|AWSRegion|string||
|SourceIpAddress|string||
|UserAgent|string||
|ErrorCode|int||
|ErrorMessage|string||
|RequestParameters|string||
|ResponseElements|string||
|AdditionalEventData|string||
|AwsRequestId|string||
|Resources|string||
|APIVersion|string||
|ReadOnly|bool||
|RecipientAccountId|string||
|ServiceEventDetails|string||
|SharedEventId|string||
|VpcEndpointId|string||
|ManagementEvent|bool||
|OperationName|string||
|Category|string||
|Type|string||
