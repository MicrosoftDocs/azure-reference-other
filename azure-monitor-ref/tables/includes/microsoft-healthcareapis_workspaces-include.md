---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.healthcareapis/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AHDSDicomAuditLogs](/azure/azure-monitor/reference/tables/AHDSDicomAuditLogs)<p>Data plane audit logs of privileged actions made against Azure Health Data DICOM service. For example, storing a DICOM instance. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/ahdsdicomauditlogs)|
| [AHDSDicomDiagnosticLogs](/azure/azure-monitor/reference/tables/AHDSDicomDiagnosticLogs)<p>Actionable logs generated from your Azure Health Data DICOM service, including events information like, warning logs per tag per DICOM instance denoting validation issues. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/ahdsdicomdiagnosticlogs)|
| [AHDSMedTechDiagnosticLogs](/azure/azure-monitor/reference/tables/AHDSMedTechDiagnosticLogs)<p>Actionable logs generated from your MedTech application. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/ahdsmedtechdiagnosticlogs)|

  
