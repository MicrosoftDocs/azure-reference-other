---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.keyvault/managedhsms, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AuditEvent` |Audit Event |[AZKVAuditLogs](/azure/azure-monitor/reference/tables/azkvauditlogs)<p>Audit logs can be used to monitor how and when your key vaults are accessed, and by whom. Customers will be able to log all authentication api requests. Operations on the key vault itself, including creation, deletion, setting key vault access policies, and updating key vault attributes such as tags.Operation on keys and secrets in keyvault including creating, deleting, signing.|Yes|No|[Queries](../../queries/azkvauditlogs.md)|No |