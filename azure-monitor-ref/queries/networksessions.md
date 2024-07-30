---
title: Example log table queries for NetworkSessions
description:  Example queries for NetworkSessions log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the NetworkSessions table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Get traffic to non standard ports  


This query identifies source IP addresses sending connection requests over multiple ports. This could be an indication of adversary attempts to list available services. References: MITRE Network Service Scanning (T1046)  

```query
// This query identifies source IP addresses sending connection requests over multiple ports.
// This could be an indication of adversary attempts to list available services.
// References: MITRE Network Service Scanning (T1046)
let threshold=5;
// Used to filter commonly used ports in your org
let commonPorts=dynamic([443, 53, 389, 80, 0, 880, 8888, 8080]);
NetworkSessions
 | where isnotempty(DstPortNumber) and not(ipv4_is_private(DstIpAddr) ) 
 // filter out IANA ephemeral or negotiated ports as per https://en.wikipedia.org/wiki/Ephemeral_port
 | where DstPortNumber !between (toint(49512) .. toint(65535)) 
     and DstPortNumber !in (commonPorts)
 | where EventResult == "Failure" 
 | summarize PortCount=dcount(DstPortNumber) by SrcIpAddr, bin(TimeGenerated, 2m)
 | where PortCount > threshold
```



### High volume traffic to uncommon domains  


This query identifies domains receiving uncommon amount of data volume. This could be an indication of adversary attempts to steal and exfiltrate data.  

```query
// This query identifies domains receiving uncommon about of data volume.
// This could be an indication of adversary attempts to steal and exfiltrate data.
let isInternal = (url_hostname:string){url_hostname endswith ".local" or url_hostname endswith ".lan" or url_hostname endswith ".home"};
    // used to exclude internal traffic
let top1M =  (externaldata (Position:int, Domain:string) [@"http://s3-us-west-1.amazonaws.com/umbrella-static/top-1m.csv.zip"]  with (format="csv", zipPattern="*.csv"));
    // fetch the alexa top 1M domains
let top2ndLevelDomain=top1M
    | extend Domain = tolower(extract("([^.]*).{0,7}$", 1, Domain)) 
    | distinct Domain;
let rareDomainTraffic = NetworkSessions
    | where isnotempty(UrlHostname) and not(isInternal(UrlHostname))
    | extend SndLevelDomain=tolower(extract("([^.]*).{0,7}$", 1, UrlHostname))
    | where SndLevelDomain !in (top2ndLevelDomain)
    | summarize BytesSent=sum(SrcBytes) by SndLevelDomain, UrlHostname;
rareDomainTraffic | summarize TotalBytes=sum(BytesSent) by SndLevelDomain
| join kind=innerunique
    rareDomainTraffic
        on SndLevelDomain
| sort by TotalBytes desc 
```

