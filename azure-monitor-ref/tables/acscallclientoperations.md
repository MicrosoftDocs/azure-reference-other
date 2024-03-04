---
title: Azure Monitor Logs reference - ACSCallClientOperations
description: Reference for ACSCallClientOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/04/2024
---

# ACSCallClientOperations

Call client operation logs provide information regarding operations performed by clients using the Azure Communication Service Calling client SDK. It includes information regarding events raised by the SDK, such as state changes, e.g. createView, startAudio,DevicePermissionRequest. This log will be used by Call Diagnostics Center to visualize a call flow in a time series manner.


## Categories

- Azure Resources

## Solutions

- LogManagement

## Resource types

- Communication Services

## Queries

 Sample queries for the [ACSCallClientOperations](/azure/azure-monitor/reference/queries/acscallclientoperations) table.


## Columns
  
[!INCLUDE [acscallclientoperations](.././tables/includes/acscallclientoperations-include.md)]
