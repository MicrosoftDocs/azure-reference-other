---
title: Example log table queries for AVSSyslog
description:  Example queries for AVSSyslog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AVSSyslog table


### Get DNS failures  


Gets 100 AVS failed DNS query logs. If you are receiving DNS query failures, check your DNS configuration.  

```query
AVSSyslog
| where AppName == "dnsmasq" // do some initial filtering to optimize 'has'
| where Message has "Failed DNS Query" // filter to only Failed DNS Query messages
| take 100
```



### Get distributed Firewall logs  


Gets 100 AVS distributed firewall logs.  

```query
AVSSyslog
| where AppName == "FIREWALL" or ProcId == "FIREWALL"
| take 100
```



### Get audit events for VM created  


Gets 100 AVS audit events for VM created events.  

```query
AVSSyslog
| where Message has "vmcreatedevent" 
| take 100
```



### Get audit events for VM deleted  


Gets 100 AVS audit events for VM deleted events.  

```query
AVSSyslog
| where Message has "vmremovedevent"
| take 100
```



### Get audit events for VM powered on  


Gets 100 AVS audits events for VM powered on events.  

```query
AVSSyslog
| where Message has "VmPowerStateChangedEvent" and Message has "poweredon"
| take 100
```



### Get audit events for VM disconnected  


Gets 100 AVS audit events for VM disconnected events.  

```query
AVSSyslog
| where Message has "vmdisconnectedevent"
| take 100
```



### Get audit events for VM rebooted  


Gets 100 AVS audit events for VM rebooted events.  

```query
AVSSyslog
| where Message has "VmGuestRebootEvent"
| take 100
```



### Get audit events for VM migrated  


Gets 100 AVS audit events for VM migrated events.  

```query
AVSSyslog
| where Message has "vmmigratedevent"
| take 100
```



### Get audit events for host added  


Gets 100 AVS audit events for host added events.  

```query
AVSSyslog
| where Message has "hostaddedevent"
| take 100
```



### Get audit events for host shutdown  


Gets 100 AVS audit events for host shutdown events.  

```query
AVSSyslog
| where Message has "hostshutdownevent"
| take 100
```



### Get audit events for host enter maintenance mode  


Gets 100 AVS audit events for host enter maintenance mode events.  

```query
AVSSyslog
| where Message has "The host has entered maintenance mode"
| take 100
```



### Get audit events for host exit maintenance mode  


Gets 100 AVS audit events for host exit maintenance mode events.  

```query
AVSSyslog
| where Message has "The host has exited maintenance mode"
| take 100
```



### Get audit events for host connected  


Gets 100 AVS audit events for host connected events.  

```query
AVSSyslog
| where Message has "hostconnectedevent"
| take 100
```



### Get audit events for host connection lost  


Gets 100 AVS audit events for host connections lost events.  

```query
AVSSyslog
| where Message has "lost connection to the host"
| take 100
```



### Get audit events for cluster  


Gets 100 AVS audit events for cluster events.  

```query
AVSSyslog
| where Message has "cluster" and Message has "event"
| take 100
```



### Get audit events count for NSX  


Gets the AVS audit events count for NSX.  

```query
AVSSyslog
| where Message has "nsx" and Message has "event"
| count
```



### Get audit events count for vCenter  


Gets the AVS audit events count for vCenter events.  

```query
AVSSyslog
| where Message has "vcenter" and Message has "event"
| count
```



### Get audit events for role added  


Gets 100 AVS audit events for role added events.  

```query
AVSSyslog
| where Message has "RoleAddedEvent"
| take 100
```



### Get AVS events with severity of Info  


Gets 100 AVS events by severity level equals Info. Swap it out with other severity level (Notice, Debug, Warning, Error) to get similar.  

```query
AVSSyslog
| where severity == "info"
| take 100
```

