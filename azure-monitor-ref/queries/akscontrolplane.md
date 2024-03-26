---
title: Example log table queries for AKSControlPlane
description:  Example queries for AKSControlPlane log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/26/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AKSControlPlane table


### Cluster Autoscaler logs  


Query for logs from the cluster autoscaler. This can help explain why the cluster is unexpectedly scaling up or down. Requires Diagnostic Settings to use the Resource Specific destination table.  

```query
AKSControlPlane
| where Category=="cluster-autoscaler"
| limit 100
| project TimeGenerated, Level, Message

```



### Kubernetes API server logs  


Query for logs from the Kubernetes API server. Requires Diagnostic Settings to use the Resource Specific destination table.  

```query
AKSControlPlane
| where Category=="kube-apiserver"
| limit 100
| project TimeGenerated, Level, Message

```

