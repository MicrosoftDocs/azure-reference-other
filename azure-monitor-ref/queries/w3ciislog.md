---
title: Example log table queries for W3CIISLog
description:  Example queries for W3CIISLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the W3CIISLog table


### List IIS log entries  


Last 50 IIS log entries.  

```query
W3CIISLog
| top 50 by TimeGenerated desc 
```



### Display breakdown respond codes  


Display breakdown respond codes.  

```query
W3CIISLog 
| summarize count() by scStatus
```



### Maximum time taken for each page  


Find maximum time taken for each page.  

```query
W3CIISLog 
| summarize max(TimeTaken) by csUriStem
```



### Show 404 pages list  


Show 404 pages list.  

```query
W3CIISLog 
| where scStatus == 404
| summarize count() by csUriStem
| sort by count_ desc
```



### Average HTTP request time  


Average HTTP request time for HTTP method.  

```query
W3CIISLog 
| summarize avg(TimeTaken) by csMethod
```



### Servers with internal server error  


Show servers throwing internal server error.  

```query
W3CIISLog
| where scStatus == "500"  
| summarize count() by sComputerName
```



### Count IIS log entries by HTTP request method  


Count IIS log entries by HTTP request method.  

```query
W3CIISLog 
| summarize count() by csMethod
```



### Count IIS log entries by HTTP user agent  


Count IIS log entries by HTTP user agent.  

```query
W3CIISLog 
| summarize count() by csUserAgent
```



### Count IIS log entries by client IP address  


Count IIS log entries by client IP address.  

```query
W3CIISLog 
| summarize count() by cIP
```



### IIS log entries for client IP  


IIS log entries for a client IP.  

```query
W3CIISLog 
| where cIP == "192.168.0.1" // Enter Client IP here
| project csUriStem, scBytes, csBytes, TimeTaken, scStatus, TimeGenerated
| top 100 by TimeGenerated desc
```



### Count of IIS log entries by URL  


Count of IIS log entries by URL requested by client.  

```query
W3CIISLog 
| summarize count() by csUriStem
```



### Count of IIS log entries by host  


Count of IIS log entries by host requested by client.  

```query
W3CIISLog 
| summarize count() by csHost
```



### Total bytes traffic by client IP  


Total bytes sent and received by client IP address.  

```query
W3CIISLog 
| summarize BytesSent = sum(csBytes), BytesReceived = sum(scBytes) by cIP
```



### Bytes received by each IIS computer  


Total bytes received by each IIS computer.  

```query
W3CIISLog 
| summarize sum_csBytes = sum(csBytes) by Computer 
| top 500 by sum_csBytes desc
```



### Bytes responded to clients by each IIS server IP  


Total bytes responded to clients by each IIS server IP address.  

```query
W3CIISLog 
| summarize sum(scBytes) by sIP
```



### Average HTTP request time by client IP  


Average HTTP request time by client IP address.  

```query
W3CIISLog 
| summarize avg(TimeTaken) by cIP
```

