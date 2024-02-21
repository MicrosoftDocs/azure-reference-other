---
title: Azure Monitor Logs reference - ASimDnsActivityLogs
description: Reference for ASimDnsActivityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/21/2024
---

# ASimDnsActivityLogs

The ASim DNS activity schema represents DNS protocol activity, which may be logged either by a DNS server or by a device sending DNS requests to a DNS server. The DNS protocol activity includes DNS queries, DNS server updates, and DNS bulk data transfers. Since the schema represents protocol activity, it is governed by RFCs and officially assigned parameter lists. The DNS activity schema does not represent DNS server audit events.


## Categories

- Security

## Solutions

- SecurityInsights

## Resource types

- Microsoft Sentinel DNS activity ASim schema

## Queries

 Sample queries for the [ASimDnsActivityLogs](/azure/azure-monitor/reference/queries/asimdnsactivitylogs) table.


## Columns
  
[!INCLUDE [asimdnsactivitylogs](.././tables/includes/asimdnsactivitylogs-include.md)]
