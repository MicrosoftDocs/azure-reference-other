---
title: Azure Monitor tables for microsoft.recoveryservices/vaults
description: Azure Monitor tables for resource type microsoft.recoveryservices/vaults
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.recoveryservices/vaults  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ASRJobs](/azure/azure-monitor/reference/tables/ASRJobs)<p>This table contains records of Azure Site Recovery (ASR) jobs such as failover, test failover, reprotection etc., with key details for monitoring and diagnostics, such as the replicated item information, duration, status, description and so on. Whenever an ASR job is completed (i.e., succeeded or failed), a corresponding record for the job is sent to this table. You can view history of ASR jobs by querying this table over a larger time range, provided your workspace has the required retention configured. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/asrjobs)|
| [ASRReplicatedItems](/azure/azure-monitor/reference/tables/ASRReplicatedItems)<p>This table contains details of Azure Site Recovery (ASR) replicated items, such as associated vault, policy, replication health, failover readiness. etc. Data is pushed once a day to this table for all replicated items, to provide the latest information for each item. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/asrreplicateditems)|
| [AddonAzureBackupAlerts](/azure/azure-monitor/reference/tables/AddonAzureBackupAlerts)<p> | management, resources | LogManagement | No| -|
| [AddonAzureBackupJobs](/azure/azure-monitor/reference/tables/AddonAzureBackupJobs)<p> | management, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/addonazurebackupjobs)|
| [AddonAzureBackupPolicy](/azure/azure-monitor/reference/tables/AddonAzureBackupPolicy)<p> | management, resources | LogManagement | No| -|
| [AddonAzureBackupProtectedInstance](/azure/azure-monitor/reference/tables/AddonAzureBackupProtectedInstance)<p> | management, resources | LogManagement | No| -|
| [AddonAzureBackupStorage](/azure/azure-monitor/reference/tables/AddonAzureBackupStorage)<p> | management, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/addonazurebackupstorage)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureBackupOperations](/azure/azure-monitor/reference/tables/AzureBackupOperations)<p>This table contains details of Azure Backup operations. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azurebackupoperations)|
| [CoreAzureBackup](/azure/azure-monitor/reference/tables/CoreAzureBackup)<p> | management, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/coreazurebackup)|

