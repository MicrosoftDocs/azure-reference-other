---
title: Azure Monitor Logs reference - CDBPartitionKeyStatistics
description: Reference for CDBPartitionKeyStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 01/15/2024
---

# CDBPartitionKeyStatistics

This table provides outlier logical partition keys that have consumed more storage space than others. Statistics are based on a sub-sampling of partition keys within the collection and hence these are approximate. Partition keys that are below 1GB of storage may not show up in the reported statistics.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Cosmos DB

            


## Columns
  
[!INCLUDE [cdbpartitionkeystatistics](../includes/cdbpartitionkeystatistics-include.md)]
