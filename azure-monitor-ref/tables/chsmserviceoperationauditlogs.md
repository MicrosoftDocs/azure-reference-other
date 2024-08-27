---
title: Azure Monitor Logs reference - CHSMServiceOperationAuditLogs
description: Reference for CHSMServiceOperationAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 08/26/2024
---

# CHSMServiceOperationAuditLogs

This table contains HSM Commands send to your Azure Cloud HSM resource's HSM partitions. These logs captures all service operations performed by Customer over E2E channel on each HSM partition of that Cloud HSM resource. They can be used to monitor events and configure necessary alerts on your Cloud HSM resource.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.hardwaresecuritymodules/cloudhsmclusters|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/chsmserviceoperationauditlogs)|



## Columns
  
[!INCLUDE [chsmserviceoperationauditlogs](./includes/chsmserviceoperationauditlogs-include.md)]
