---
title: Azure Monitor Logs reference - WaaSInsiderStatus
description: Reference for WaaSInsiderStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# WaaSInsiderStatus

 Summary of each run of your update schedule with details like how many updates were not installed etc.

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string |  |
| ComputerID | string |  |
| LastScan | datetime |  |
| OSArchitecture | string |  |
| OSBuild | string |  |
| OSEdition | string |  |
| OSFamily | string |  |
| OSName | string |  |
| OSRevisionNumber | int |  |
| OSVersion | string |  |
| SourceSystem | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
