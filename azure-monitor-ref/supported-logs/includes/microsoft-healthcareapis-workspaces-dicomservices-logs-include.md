---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AuditLogs` |Audit logs |[AHDSDicomAuditLogs](/azure/azure-monitor/reference/tables/ahdsdicomauditlogs)<p>Data plane audit logs of privileged actions made against Azure Health Data DICOM service. For example, storing a DICOM instance.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/ahdsdicomauditlogs)|Yes |
|`DiagnosticLogs` |Diagnostic logs |[AHDSDicomDiagnosticLogs](/azure/azure-monitor/reference/tables/ahdsdicomdiagnosticlogs)<p>Actionable logs generated from your Azure Health Data DICOM service, including events information like, warning logs per tag per DICOM instance denoting validation issues.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/ahdsdicomdiagnosticlogs)|Yes |