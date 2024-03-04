---
title: Azure Monitor Logs reference - AZMSVnetConnectionEvents
description: Reference for AZMSVnetConnectionEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/04/2024
---

# AZMSVnetConnectionEvents

Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules).


## Categories

- Azure Resources
- Audit

## Solutions

- LogManagement

## Resource types

- Event Hubs
- Service Bus
- Relay

## Queries

 Sample queries for the [AZMSVnetConnectionEvents](/azure/azure-monitor/reference/queries/azmsvnetconnectionevents) table.


## Columns
  
[!INCLUDE [azmsvnetconnectionevents](.././tables/includes/azmsvnetconnectionevents-include.md)]
