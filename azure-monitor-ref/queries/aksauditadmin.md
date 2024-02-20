---
title: Example log table queries for AKSAuditAdmin
description:  Example queries for AKSAuditAdmin log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AKSAuditAdmin table


### Volume of admin Kubernetes audit events per username  


Display the count of admin Kubernetes audit events generated from a given user name for each AKS cluster. Requires Diagnostic Settings to use the Resource Specific destination table.  

```query
AKSAuditAdmin
| where ResponseStatus.code != 401  // Exclude unauthorized responses
| summarize Count = count() by Username = tostring(User.username), ResourceId = _ResourceId
| sort by Count desc
```



### Admin Kubernetes audit events for deployment  


Query for admin Kubernetes audit events against deployments within the default namespace. Requires Diagnostic Settings to use the Resource Specific destination table.  

```query
AKSAuditAdmin
| where ObjectRef.resource == "deployments"
| where ObjectRef.namespace == "default"
| where User.username != "system:serviceaccount:kube-system:deployment-controller" // Exclude updates from the kube controller for deployments
| limit 100
| project TimeGenerated, Verb, RequestUri, User, RequestObject, ObjectRef
```

