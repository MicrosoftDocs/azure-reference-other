---
title: Azure Monitor Logs reference - OLPSupplyChainEvents
description: Reference for OLPSupplyChainEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# OLPSupplyChainEvents

The events table captures every event that was dispatched from the Open Logistics Platform workspace. Events can be a result of a data plane API call (e.g. Shipment Created, Item Deleted, Notification sent, etc.) or a long running job operation completion (e.g. Data ingestion results in NewDataAvailable event).


## Categories

- Azure Resources

## Solutions

- LogManagement

## Resource types

- Microsoft.OpenLogisticsPlatform/Workspaces

## Columns
  
[!INCLUDE [olpsupplychainevents](.././tables/includes/olpsupplychainevents-include.md)]
