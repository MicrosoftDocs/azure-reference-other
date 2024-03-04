---
title: Azure Monitor Logs reference - AZKVAuditLogs
description: Reference for AZKVAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/04/2024
---

# AZKVAuditLogs

Audit logs can be used to monitor how and when your key vaults are accessed, and by whom. Customers will be able to log all authentication api requests. Operations on the key vault itself, including creation, deletion, setting key vault access policies, and updating key vault attributes such as tags.Operation on keys and secrets in keyvault including creating, deleting, signing.


## Categories

- Azure Resources
- Audit

## Solutions

- LogManagement

## Resource types

- Key Vaults

## Queries

 Sample queries for the [AZKVAuditLogs](/azure/azure-monitor/reference/queries/azkvauditlogs) table.


## Columns
  
[!INCLUDE [azkvauditlogs](.././tables/includes/azkvauditlogs-include.md)]
