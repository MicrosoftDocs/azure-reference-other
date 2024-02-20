---
title: Example log table queries for requests
description:  Example queries for requests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the requests table


### Response time trend  


Chart request duration over the last 12 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
requests
| where timestamp > ago(12h) 
| summarize avgRequestDuration=avg(duration) by bin(timestamp, 10m) // use a time grain of 10 minutes
| render timechart
```



### Request count trend  


Chart Request count over the last day.  

```query
// To create an alert for this query, click '+ New alert rule'
requests
| summarize totalCount=sum(itemCount) by bin(timestamp, 30m)
| render timechart
```



### Response time buckets  


Show how many requests are in each performance-bucket.  

```query
requests
| summarize requestCount=sum(itemCount), avgDuration=avg(duration) by performanceBucket
| order by avgDuration asc // sort by average request duration
| project-away avgDuration // no need to display avgDuration, we used it only for sorting results
| render barchart
```



### Operations performance  


Calculate request count and duration by operations.  

```query
// To create an alert for this query, click '+ New alert rule'
requests
| summarize RequestsCount=sum(itemCount), AverageDuration=avg(duration), percentiles(duration, 50, 95, 99) by operation_Name // you can replace 'operation_Name' with another value to segment by a different property
| order by RequestsCount desc // order from highest to lower (descending)
```



### Top 10 countries by traffic  


Chart the amount of requests from the top 10 countries.  

```query
requests
| summarize CountByCountry=count() by client_CountryOrRegion
| top 10 by CountByCountry
| render piechart
```



### Failed requests – top 10  


What are the 3 slowest pages, and how slow are they?  

```query
requests
| where success == false
| summarize failedCount=sum(itemCount) by name
| top 10 by failedCount desc
| render barchart
```



### Failed operations  


Calculate how many times operations failed, and how many users were impacted.  

```query
// To create an alert for this query, click '+ New alert rule'
requests
| where success == false
| summarize failedCount=sum(itemCount), impactedUsers=dcount(user_Id) by operation_Name
| order by failedCount desc
```



### Exceptions causing request failures  


Find which exceptions led to failed requests in the past hour.  

```query
requests
| where timestamp > ago(1h) and success == false
| join kind= inner (
exceptions
| where timestamp > ago(1h)
) on operation_Id
| project exceptionType = type, failedMethod = method, requestName = name, requestDuration = duration
```

