---
title: Azure Monitor Logs reference - AWSCloudTrail
description: Reference for AWSCloudTrail table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# AWSCloudTrail

 CloudTrail logs, which ingested from Sentinel's connector, holds all your data and management events of your Amazon Wev Services account.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalEventData | string |  |
| APIVersion | string |  |
| AwsEventId | string |  |
| AWSRegion | string |  |
| AwsRequestId_ | string |  |
| Category | string |  |
| ErrorCode | string |  |
| ErrorMessage | string |  |
| EventName | string |  |
| EventSource | string |  |
| EventTypeName | string |  |
| EventVersion | string |  |
| ManagementEvent | bool |  |
| OperationName | string |  |
| ReadOnly | bool |  |
| RecipientAccountId | string |  |
| RequestParameters | string |  |
| Resources | string |  |
| ResponseElements | string |  |
| ServiceEventDetails | string |  |
| SessionCreationDate | datetime |  |
| SessionIssuerAccountId | string |  |
| SessionIssuerArn | string |  |
| SessionIssuerPrincipalId | string |  |
| SessionIssuerType | string |  |
| SessionIssuerUserName | string |  |
| SessionMfaAuthenticated | bool |  |
| SharedEventId | string |  |
| SourceIpAddress | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserAgent | string |  |
| UserIdentityAccessKeyId | string |  |
| UserIdentityAccountId | string |  |
| UserIdentityArn | string |  |
| UserIdentityInvokedBy | string |  |
| UserIdentityPrincipalid | string |  |
| UserIdentityType | string |  |
| UserIdentityUserName | string |  |
| VpcEndpointId | string |  |
