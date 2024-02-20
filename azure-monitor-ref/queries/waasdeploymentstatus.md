---
title: Example log table queries for WaaSDeploymentStatus
description:  Example queries for WaaSDeploymentStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WaaSDeploymentStatus table


### Update deployment failures  


Update deployment failures by device and update classification.  

```query
WaaSDeploymentStatus
| where DeploymentStatus == "Failed"
| summarize arg_max(TimeGenerated, *) by ComputerID, UpdateClassification 
| project Computer, ComputerID, ReleaseName, UpdateCategory, UpdateClassification, DeploymentError, DeploymentErrorCode
```



### Devices pending reboot to complete update  


Devices with pending reboot to complete update.  

```query
WaaSDeploymentStatus
| where DetailedStatus == "Reboot pending"
| summarize arg_max(TimeGenerated, *) by ComputerID, UpdateClassification
| project Computer, ComputerID, DetailedStatus, ReleaseName, UpdateCategory, UpdateClassification, LastScan
```



### Devices with a Safeguard Hold  


This query shows the device data for all devices that are impacted by safeguard holds.  

```query
WaaSDeploymentStatus
| where DetailedStatus == "Safeguard Hold"
| summarize arg_max(TimeGenerated, *) by ComputerID, UpdateClassification
| project TimeGenerated, DetailedStatus, ComputerID, ReleaseName, UpdateCategory, UpdateClassification
```



### Target build distribution of devices with a safeguard hold  


Pie chart of target build distribution of devices impacted by safeguards.  

```query
WaaSDeploymentStatus
| where DetailedStatus == "Safeguard Hold"
| summarize count(ComputerID) by TargetBuild
| render piechart
```

