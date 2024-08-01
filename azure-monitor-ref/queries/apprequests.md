---
title: Example log table queries for AppRequests
description:  Example queries for AppRequests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppRequests table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Response time trend  


Chart request duration over the last 12 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
AppRequests
| where TimeGenerated > ago(12h) 
| summarize avgRequestDuration=avg(DurationMs) by bin(TimeGenerated, 10m), _ResourceId // use a time grain of 10 minutes
| render timechart
```



### Request count trend  


Chart Request count over the last day.  

```query
// To create an alert for this query, click '+ New alert rule'
AppRequests
| summarize totalCount=sum(ItemCount) by bin(TimeGenerated, 30m), _ResourceId
| render timechart
```



### Response time buckets  


Show how many requests are in each performance-bucket.  

```query
AppRequests
| summarize requestCount=sum(ItemCount), avgDuration=avg(DurationMs) by PerformanceBucket
| order by avgDuration asc // sort by average request duration
| project-away avgDuration // no need to display avgDuration, we used it only for sorting results
| render barchart
```



### Operations performance  


Calculate request count and duration by operations.  

```query
// To create an alert for this query, click '+ New alert rule'
AppRequests
| summarize RequestsCount=sum(ItemCount), AverageDuration=avg(DurationMs), percentiles(DurationMs, 50, 95, 99) by OperationName, _ResourceId // you can replace 'OperationName' with another value to segment by a different property
| order by RequestsCount desc // order from highest to lower (descending)
```



### Top 10 countries by traffic  


Chart the amount of requests from the top 10 countries.  

```query
AppRequests
| summarize CountByCountry=count() by ClientCountryOrRegion
| top 10 by CountByCountry
| render piechart
```



### Failed requests – top 10  


What are the 3 slowest pages, and how slow are they?  

```query
AppRequests
| where Success == false
| summarize failedCount=sum(ItemCount) by Name
| top 10 by failedCount desc
| render barchart
```



### Failed operations  


Calculate how many times operations failed, and how many users were impacted.  

```query
// To create an alert for this query, click '+ New alert rule'
AppRequests
| where Success == false
| summarize failedCount=sum(ItemCount), impactedUsers=dcount(UserId) by OperationName, _ResourceId
| order by failedCount desc
```



### Exceptions causing request failures  


Find which exceptions led to failed requests in the past hour.  

```query
AppRequests
| where TimeGenerated > ago(1h) and Success == false
| join kind= inner (
AppExceptions
| where TimeGenerated > ago(1h)
) on OperationId
| project exceptionType = Type, failedMethod = Method, requestName = Name, requestDuration = DurationMs, _ResourceId
```

