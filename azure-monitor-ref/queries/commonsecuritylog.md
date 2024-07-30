---
title: Example log table queries for CommonSecurityLog
description:  Example queries for CommonSecurityLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CommonSecurityLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Palo Alto collector machine usage  


This query displays a descending list of all collector machines hostname according to the amount of events they are recieving from a Palo Alto appliance.  

```query
CommonSecurityLog
// Quering on the past 7 days
| where TimeGenerated > ago(7d)
// Quering only on incoming events from a Palo Alto appliance
| where DeviceProduct has 'PAN-OS'
| where DeviceVendor =~ 'Palo Alto Networks'
// Find the the collector machine with the highest usage
| summarize Count=count() by Computer
// Sort in a descending order- Most used Collector hostname comes first
| sort by Count desc
```



### Cisco ASA events type usage  


This query displays a descending list of the amount of events ingested for each DeviceEventClassID  

```query
CommonSecurityLog 
// Quering on the past 7 days
| where TimeGenerated > ago(7d)
// Only filter on Cisco ASA events
| where DeviceVendor == "Cisco" and DeviceProduct == "ASA"
// group events by their DeviceEventClassID value, which represents the Cisco message id
| summarize count_events=count() by DeviceEventClassID
// Sort in a descending order- most used DeviceEventClassID comes first
| sort by count_events desc
```



### Device events volume statistics  


Devices sending most events.  

```query
CommonSecurityLog
| top-nested 15 of DeviceVendor by Vendor=count(),
  top-nested 5 of DeviceProduct by Product=count(),
  top-nested 5 of DeviceVersion by Version=count()
```

