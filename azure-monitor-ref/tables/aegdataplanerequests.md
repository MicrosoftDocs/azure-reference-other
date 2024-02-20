---
title: Azure Monitor Logs reference - AegDataPlaneRequests
description: Reference for AegDataPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# AegDataPlaneRequests

Logs for Event Grid data plane requests (publish and options) against a topic/domain/partnernamespace. It can be used for auditing purposes. Logs are aggregated over a minute and displays the total number of requests with specific request properties.


## Categories

- Azure Resources
- Audit

## Solutions

- LogManagement

## Resource types

- Event Grid Topics
- Event Grid Domains
- Event Grid Partner Namespaces

## Queries

 Sample queries for the [AegDataPlaneRequests](../queries/aegdataplanerequests.md) table.


## Columns
  
[!INCLUDE [aegdataplanerequests](.././tables/includes/aegdataplanerequests-include.md)]
