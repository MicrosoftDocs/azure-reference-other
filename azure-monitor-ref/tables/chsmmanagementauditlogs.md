---
title: Azure Monitor Logs reference - CHSMManagementAuditLogs
description: Reference for CHSMManagementAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# CHSMManagementAuditLogs

This table contains audit logs retrieved from your Azure CloudHsm resource's HSM partitions. These logs captures all management operations performed by Customer over E2E channel on each HSM partition of that CloudHsm resource. They can be used to monitor events and configure necessary alerts on your CloudHsm resource.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.hardwaresecuritymodules/cloudhsmclusters|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/chsmmanagementauditlogs)|



## Columns
  
[!INCLUDE [chsmmanagementauditlogs](.././tables/includes/chsmmanagementauditlogs-include.md)]
