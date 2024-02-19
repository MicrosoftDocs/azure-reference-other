---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AuditLogs` |Audit logs |[AHDSDicomAuditLogs](/azure/azure-monitor/reference/tables/ahdsdicomauditlogs)<p>Data plane audit logs of privileged actions made against Azure Health Data DICOM service. For example, storing a DICOM instance.|Yes|No|[Queries](../../queries/ahdsdicomauditlogs.md)|Yes |
|`DiagnosticLogs` |Diagnostic logs ||No|No||Yes |