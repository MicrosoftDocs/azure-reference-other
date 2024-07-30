---
title: Example log table queries for WireData
description:  Example queries for WireData log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WireData table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Agents that provide wire data  


Agents providing wire data and sum of total bytes for each agent.  

```query
WireData
| summarize sum(TotalBytes) by Computer
```



### IP Addresses of the agents providing wire data  


IP Addresses of the agents providing wire data.  

```query
WireData
| summarize count() by LocalIP
```



### All Outbound communications by Remote IP Address  


All Outbound communications by Remote IP Address.  

```query
WireData
| where  Direction == "Outbound"
| summarize count() by RemoteIP
```



### Bytes sent by Application Protocol  


Bytes sent by Application Protocol.  

```query
WireData
| where Direction == "Outbound"
| summarize sum(SentBytes) by ApplicationProtocol
```



### Bytes received by Protocol Name  


Bytes received by Protocol Name (transport-level protocol, only some are recognized).  

```query
WireData
| where Direction == "Inbound"
| summarize sum(ReceivedBytes) by ProtocolName
```



### Total bytes by IP version  


Total bytes by IP version (IPv4 or IPv6).  

```query
WireData
| summarize sum(TotalBytes) by IPVersion
```



### Remote IP addresses that have communicated with agents on the subnet '10.0.0.0/8' (any direction)  


Remote IP addresses that have communicated with agents on the subnet '10.0.0.0/8' (any direction).  

```query
WireData  
| where LocalSubnet == "10.0.0.0/8" 
| summarize count() by RemoteIP
```



### Processes that initiated or received network traffic  


Processes that initiated or received network traffic.  

```query
WireData
| distinct ProcessName
```



### Amount of Network Traffic by Process  


Amount of Network Traffic (in Bytes) by Process.  

```query
WireData
| summarize sum(TotalBytes) by ProcessName
```

