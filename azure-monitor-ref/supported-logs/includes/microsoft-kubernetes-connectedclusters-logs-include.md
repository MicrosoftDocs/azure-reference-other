---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: microsoft.kubernetes/connectedClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`cloud-controller-manager` |Kubernetes Cloud Controller Manager ||No|No||Yes |
|`cluster-autoscaler` |Kubernetes Cluster Autoscaler ||No|No||Yes |
|`csi-aksarcdisk-controller` |csi-aksarcdisk-controller ||No|No||Yes |
|`csi-aksarcnfs-controller` |csi-aksarcnfs-controller ||No|No||Yes |
|`csi-aksarcsmb-controller` |csi-aksarcsmb-controller ||No|No||Yes |
|`guard` |guard ||No|No||Yes |
|`kube-apiserver` |Kubernetes API Server |[ArcK8sControlPlane](/azure/azure-monitor/reference/tables/arck8scontrolplane)<p>Contains diagnostic logs for the Kubernetes API Server, Controller Manager, Scheduler, Cluster Autoscaler, Cloud Controller Manager, Guard, and the Azure CSI storage drivers. These diagnostic logs have distinct Category entries corresponding their diagnostic log setting (e.g. kube-apiserver, kube-audit-admin). Requires Diagnostic Settings to use the Resource Specific destination table.|Yes|No||Yes |
|`kube-audit` |Kubernetes Audit |[ArcK8sAudit](/azure/azure-monitor/reference/tables/arck8saudit)<p>Contains all Kubernetes API Server audit logs including events with the get and list verbs. These events are useful for monitoring all of the interactions with the Kubernetes API. To limit the scope to modifying operations see the ArcK8sAuditAdmin table. Requires Diagnostic Settings to use the Resource Specific destination table.|Yes|No||Yes |
|`kube-audit-admin` |Kubernetes Audit Admin Logs |[ArcK8sAuditAdmin](/azure/azure-monitor/reference/tables/arck8sauditadmin)<p>Contains Kubernetes API Server audit logs excluding events with the get and list verbs. These events are useful for monitoring resource modification requests made to the Kubernetes API. To see all modifying and non-modifying operations see the ArcK8sAudit table. Requires Diagnostic Settings to use the Resource Specific destination table.|Yes|No||Yes |
|`kube-controller-manager` |Kubernetes Controller Manager ||No|No||Yes |
|`kube-scheduler` |Kubernetes Scheduler ||No|No||Yes |