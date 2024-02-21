---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/21/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Attestation/attestationProviders, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AuditEvent` |AuditEvent message log category. ||No|Yes||No |
|`NotProcessed` |Requests which could not be processed. ||No|Yes||Yes |
|`Operational` |Operational message log category. |[AzureAttestationDiagnostics](/azure/azure-monitor/reference/tables/azureattestationdiagnostics)<p>Logs from attestation requests.|No|No|[Queries](/azure/azure-monitor/reference/queries/azureattestationdiagnostics)|Yes |