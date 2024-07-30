---
title: Azure Monitor Logs reference - AWSGuardDuty
description: Reference for AWSGuardDuty table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AWSGuardDuty

Guard Duty Findings, which ingested from Sentinel's connector, represents a potential security issue detected within your network. GuardDuty generates a finding whenever it detects unexpected and potentially malicious activity in your AWS environment.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Security|
|**Solutions**| SecurityInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/awsguardduty)|



## Columns
  
[!INCLUDE [awsguardduty](./includes/awsguardduty-include.md)]
