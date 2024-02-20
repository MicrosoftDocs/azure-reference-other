---
title: Azure Monitor Logs reference - WVDAutoscaleEvaluationPooled
description: Reference for WVDAutoscaleEvaluationPooled table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# WVDAutoscaleEvaluationPooled

The results of an Azure Virtual Desktop Autoscale scaling plan evaluation on a hostpool. This includes information on the actions Autoscale took on the sessions hosts, such as starting or deallocating them, and why it took those actions. The column names that start with 'Config' contain the scaling plan configuration values for the current Autoscale schedule phase. If the ResultType column value is 'Failed' then join to the WVDErrors table using the CorrelationId column to get more details. For Autoscale documentation see https://go.microsoft.com/fwlink/?linkid=2169532 .


## Categories

- Azure Virtual Desktop

## Solutions

- LogManagement

## Resource types

- Desktop Virtualization Host Pools

## Columns
  
[!INCLUDE [wvdautoscaleevaluationpooled](.././tables/includes/wvdautoscaleevaluationpooled-include.md)]
