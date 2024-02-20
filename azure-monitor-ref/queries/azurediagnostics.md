---
title: Example log table queries for AzureDiagnostics
description:  Example queries for AzureDiagnostics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureDiagnostics table


## Queries for microsoft.automation  

### Errors in automation jobs  

Find logs reporting errors in automation jobs from the last day.  

```query
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.AUTOMATION"  
| where StreamType_s == "Error" 
| project TimeGenerated, Category, JobId_g, OperationName, RunbookName_s, ResultDescription
```




### Find logs reporting errors in automation jobs from the last day  

List all the errors in the automation jobs.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.AUTOMATION" 
| where StreamType_s == "Error" 
| project TimeGenerated, Category, JobId_g, OperationName, RunbookName_s, ResultDescription, _ResourceId 
```




### Azure Automation jobs that are failed, suspended, or stopped  

List all the automation jobs that failed , suspended or stopped.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.AUTOMATION" and Category == "JobLogs" and (ResultType == "Failed" or ResultType == "Stopped" or ResultType == "Suspended") 
| project TimeGenerated , RunbookName_s , ResultType , _ResourceId , JobId_g
```




### Runbook completed successfully with errors  

List all jobs that completed with errors.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.AUTOMATION" and Category == "JobStreams" and StreamType_s == "Error" 
| project TimeGenerated , RunbookName_s , StreamType_s , _ResourceId , ResultDescription , JobId_g 
```




### View historical job status  

List all automation jobs.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.AUTOMATION" and Category == "JobLogs" and ResultType != "started"
| summarize AggregatedValue = count() by ResultType, bin(TimeGenerated, 1h) , RunbookName_s , JobId_g, _ResourceId
```




### Azure Automation jobs that are Completed  

List all automation jobs that got completed.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.AUTOMATION" and Category == "JobLogs" and ResultType == "Completed" 
| project TimeGenerated , RunbookName_s , ResultType , _ResourceId , JobId_g 
```



## Queries for microsoft.batch  

### Successful tasks per job  

Provides the number of successful tasks per job.  

```query
AzureDiagnostics
| where OperationName=="TaskCompleteEvent"
| where executionInfo_exitCode_d==0 // Your application may use an exit code other than 0 to denote a successful operation
| summarize successfulTasks=count(id_s) by jobId=jobId_s
```




### Failed tasks per job  

Lists failed tasks by parent job.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where OperationName=="TaskFailEvent"
| summarize failedTaskList=make_list(id_s) by jobId=jobId_s, ResourceId
```




### Task durations  

Gives the elapsed time of tasks in seconds, from task start to task complete.  

```query
AzureDiagnostics
| where OperationName=="TaskCompleteEvent"
| extend taskId=id_s, ElapsedTime=datetime_diff('second', executionInfo_endTime_t, executionInfo_startTime_t) // For longer running tasks, consider changing 'second' to 'minute' or 'hour'
| summarize taskList=make_list(taskId) by ElapsedTime
```




### Pool resizes  

List resize times by pool and result code (success or failure).  

```query
AzureDiagnostics
| where OperationName=="PoolResizeCompleteEvent"
| summarize operationTimes=make_list(startTime_s) by poolName=id_s, resultCode=resultCode_s
```




### Pool resize failures  

List pool resize failures by error code and time.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where OperationName=="PoolResizeCompleteEvent"
| where resultCode_s=="Failure" // Filter only on failed pool resizes
| summarize by poolName=id_s, resultCode=resultCode_s, resultMessage=resultMessage_s, operationTime=startTime_s, ResourceId
```



## Queries for microsoft.cdn  

### [Microsoft CDN (classic)] Requests per hour  

Render line chart showing total request per hour.  

```query
// Summarize number of requests per hour 
// Change bins resolution from 1hr to 5m to get real time results)
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog" 
| where isReceivedFromClient_b == "true"
| summarize RequestCount = count() by bin(TimeGenerated, 1h), Resource, _ResourceId
| render timechart
```




### [Microsoft CDN (classic)] Traffic by URL  

Show egress from CDN edge by URL.  

```query
// Change bins resolution from 1 hour to 5 minutes to get real time results)
// CDN edge response traffic by URL
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog" 
| where isReceivedFromClient_b == true
| summarize ResponseBytes = sum(toint(responseBytes_s)) by requestUri_s
```




### [Microsoft CDN (classic)] 4XX error rate by URL  

Show 4XX error rate by URL.  

```query
// Request errors rate by URL
// Count number of requests with error responses by URL. 
// Summarize number of requests by URL, and status codes are 4XX
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog" and isReceivedFromClient_b == true
| extend Is4XX = (toint(httpStatusCode_s ) >= 400 and toint(httpStatusCode_s ) < 500)
| summarize 4xxrate = (1.0 * countif(Is4XX)  / count()) * 100 by requestUri_s, bin(TimeGenerated, 1h), _ResourceId
```




### [Microsoft CDN (classic)] Request errors by user agent  

Count number of requests with error responses by user agent.  

```query
// Summarize number of requests per user agent and status codes >= 400
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog" 
| where isReceivedFromClient_b == true
| where toint(httpStatusCode_s) >= 400
| summarize RequestCount = count() by UserAgent = userAgent_s, StatusCode = httpStatusCode_s , Resource, _ResourceId
| order by RequestCount desc
```




### [Microsoft CDN (classic)] Top 10 URL request count  

Show top 10 URLs by request count.  

```query
// top URLs by request count
// Render line chart showing total requests per hour . 
// Summarize number of requests per hour 
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog" 
| where isReceivedFromClient_b == true
| summarize UserRequestCount = count() by requestUri_s
| order by UserRequestCount
| limit 10
```




### [Microsoft CDN (classic)] Unique IP request count  

Show Unique IP request count.  

```query
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write"and Category == "AzureCdnAccessLog"
| where isReceivedFromClient_b == true
| summarize dcount(clientIp_s) by bin(TimeGenerated, 1h)
| render timechart 
```




### [Microsoft CDN (classic)] Top 10 client IPs and HTTP versions  

Show top 10 client IPs and http versions.  

```query
// Top 10 client IPs and http versions 
// Show top 10 client IPs and http versions. 
// Summarize top 10 client ips and http versions
AzureDiagnostics
| where OperationName == "Microsoft.Cdn/Profiles/AccessLog/Write" and Category == "AzureCdnAccessLog"
| where isReceivedFromClient_b == true
| summarize RequestCount = count() by ClientIP = clientIp_s, HttpVersion = httpVersion_s, Resource
| top 10 by RequestCount 
| order by RequestCount desc
```




### [Azure Front Door Standard/Premium] Top 20 blocked clients by IP and rule  

Show top 20 blocked clients by IP and rule name.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorWebApplicationFirewallLog"
| where action_s == "Block"
| summarize RequestCount = count() by ClientIP = clientIP_s, UserAgent = userAgent_s, RuleName = ruleName_s,Resource
| top 20 by RequestCount 
| order by RequestCount desc
```




### [Azure Front Door Standard/Premium] Requests to origin by route  

Count number of requests for each route and origin per minute. Summarize number of requests per minute for each route and origin.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| summarize RequestCount = count() by bin(TimeGenerated, 1m), Resource, RouteName = routingRuleName_s, originName = originName_s, ResourceId
```




### [Azure Front Door Standard/Premium] Request errors by user agent  

Count number of requests with error responses by user agent. Summarize number of requests per user agent and status codes >= 400.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| where toint(httpStatusCode_s) >= 400
| summarize RequestCount = count() by UserAgent = userAgent_s, StatusCode = httpStatusCode_s , Resource, ResourceId
| order by RequestCount desc
```




### [Azure Front Door Standard/Premium] Top 10 client IPs and http versions  

Show top 10 client IPs and http versions by request count.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| summarize RequestCount = count() by ClientIP = clientIp_s, HttpVersion = httpVersion_s, Resource
|top 10 by RequestCount 
| order by RequestCount desc
```




### [Azure Front Door Standard/Premium] Request errors by host and path  

Count number of requests with error responses by host and path. Summarize number of requests by host, path, and status codes >= 400.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| where toint(httpStatusCode_s) >= 400
| extend ParsedUrl = parseurl(requestUri_s)
| summarize RequestCount = count() by Host = tostring(ParsedUrl.Host), Path = tostring(ParsedUrl.Path), StatusCode = httpStatusCode_s, ResourceId
| order by RequestCount desc
```




### [Azure Front Door Standard/Premium] Firewall blocked request count per hour  

Count number of firewall blocked requests per hour. Summarize number of firewall blocked requests per hour by policy.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorWebApplicationFirewallLog"
| where action_s == "Block"
| summarize RequestCount = count() by bin(TimeGenerated, 1h), Policy = policy_s, PolicyMode = policyMode_s, Resource, ResourceId
| order by RequestCount desc

```




### [Azure Front Door Standard/Premium] Firewall request count by host, path, rule, and action  

Count firewall processed requests by host, path, rule, and action taken. Summarize request count by host, path, rule, and action.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorWebApplicationFirewallLog"
| extend ParsedUrl = parseurl(requestUri_s)
| summarize RequestCount = count() by Host = tostring(ParsedUrl.Host), Path = tostring(ParsedUrl.Path), RuleName = ruleName_s, Action = action_s, ResourceId
| order by RequestCount desc

```




### [Azure Front Door Standard/Premium] Requests per hour  

Render line chart showing total requests per hour for each FrontDoor resource.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorWebApplicationFirewallLog"
| summarize RequestCount = count() by bin(TimeGenerated, 1h), Resource, ResourceId
| render timechart 

```




### [Azure Front Door Standard/Premium] Top 10 URL request count  

Show top 10 URLs by request count.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| summarize UserRequestCount = count() by requestUri_s
| order by UserRequestCount
| limit 10

```




###  [Azure Front Door Standard/Premium] Top 10 URL request count   

 Show egress from AFD edge by URL. Change bins resolution from 1hr to 5m to get real time results.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| summarize ResponseBytes = sum(toint(responseBytes_s)) by requestUri_s

```




### [Azure Front Door Standard/Premium]  Unique IP request count  

Show unique IP request count.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.CDN" and Category == "FrontDoorAccessLog"
| summarize dcount(clientIp_s) by bin(TimeGenerated, 1h)
| render timechart

```



## Queries for microsoft.containerservice  

### Find In AzureDiagnostics  

Find in AzureDiagnostics to search for a specific value in the AzureDiagnostics table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureDiagnostics
| where ResourceProvider == "Microsoft.ContainerService"
| where * contains tostring(SearchValue)
| take 1000
```



## Queries for microsoft.dbformariadb  

### Execution time exceeding a threshold  

Identify queries that their run time exceeds 10 seconds.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMARIADB" 
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s, ResourceId 
| where query_time_d > 10 // You may change the time threshold
```




### Show the Slowest queries   

Identify top 5 slowest queries.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMARIADB" 
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s 
| top 5 by query_time_d desc
```




### Show Query's statistics  

Construct a summary statistics table by query.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMARIADB" 
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s 
| summarize count(), min(query_time_d), max(query_time_d), avg(query_time_d), stdev(query_time_d), percentile(query_time_d, 95) by LogicalServerName_s ,sql_text_s 
|  top 50  by percentile_query_time_d_95 desc
```




### Review audit log events in GENERAL class   

Identify general class events for your server.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMARIADB" 
| where Category == 'MySqlAuditLogs' and event_class_s == "general_log"
| project TimeGenerated, LogicalServerName_s, event_class_s, event_subclass_s, event_time_t, user_s , ip_s , sql_text_s 
| order by TimeGenerated asc
```




### Review audit log events in CONNECTION class   

Identify connection related events for your server.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMARIADB" 
| where Category == 'MySqlAuditLogs' and event_class_s == "connection_log"
| project TimeGenerated, LogicalServerName_s, event_class_s, event_subclass_s, event_time_t, user_s , ip_s , sql_text_s 
| order by TimeGenerated asc 
```



## Queries for microsoft.dbformysql  

### Execution time exceeding a threshold  

Identify queries that their run time exceeds 10 seconds.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORMYSQL"
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s, ResourceId 
| where query_time_d > 10 //You may change the time threshold 
```




### Show the Slowest queries   

Identify top 5 slowest queries.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORMYSQL" 
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s 
| top 5 by query_time_d desc
```




### Show Query's statistics  

Construct a summary statistics table by query.  

```query
AzureDiagnostics
| where ResourceProvider ==  "MICROSOFT.DBFORMYSQL"
| where Category == 'MySqlSlowLogs'
| project TimeGenerated, LogicalServerName_s, event_class_s, start_time_t , query_time_d, sql_text_s 
| summarize count(), min(query_time_d), max(query_time_d), avg(query_time_d), stdev(query_time_d), percentile(query_time_d, 95) by LogicalServerName_s ,sql_text_s 
|  top 50  by percentile_query_time_d_95 desc
```




### Review audit log events in GENERAL class   

Identify general class events for your server.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMYSQL"
| where Category == 'MySqlAuditLogs' and event_class_s == "general_log"
| project TimeGenerated, LogicalServerName_s, event_class_s, event_subclass_s, event_time_t, user_s , ip_s , sql_text_s 
| order by TimeGenerated asc
```




### Review audit log events in CONNECTION class   

Identify connection related events for your server.  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORMYSQL"
| where Category == 'MySqlAuditLogs' and event_class_s == "connection_log"
| project TimeGenerated, LogicalServerName_s, event_class_s, event_subclass_s, event_time_t, user_s , ip_s , sql_text_s 
| order by TimeGenerated asc 
```



## Queries for microsoft.dbforpostgresql  

### Autovacuum events  

Search for autovacuum events over the last 24 hours. It requires parameter 'log_autovacuum_min_duration' enabled.  

```query
AzureDiagnostics
| where TimeGenerated > ago(1d) 
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "automatic vacuum"

```




### Server restarts  

Search for server shut down and server ready events.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where TimeGenerated > ago(7d)
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "database system was shut down at" or Message contains "database system is ready to accept" 

```




### Find Errors  

Search for errors in the last 6 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where TimeGenerated > ago(6h)
| where Category == "PostgreSQLLogs"
| where  errorLevel_s contains "error" 

```




### Unauthorized connections  

Search for unauthorized (rejected) connection attempts.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "password authentication failed" or Message contains "no pg_hba.conf entry for host"
```




### Deadlocks  

Search for deadlock events.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "deadlock detected"
```




### Lock contention  

Search for lock contention. It requires log_lock_waits=ON and depends on deadlock_timeout setting.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Message contains "still waiting for ShareLock on transaction" 
```




### Audit logs  

Get all audit logs. It requires audit logs to be enabled [https://docs.microsoft.com/azure/postgresql/concepts-audit].  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "AUDIT:"
```




### Audit logs for table(s) and event type(s)  

Search for audit logs for a specific table and event type DDL. Other event types are READ, WRITE, FUNCTION, MISC. It requires audit logs enabled. [https://docs.microsoft.com/azure/postgresql/concepts-audit].  

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.DBFORPOSTGRESQL" 
| where Category == "PostgreSQLLogs"
| where Message contains "AUDIT:" 
| where Message contains "table name" and Message contains "DDL"
```




### Queries with execution time exceeding a threshold  

Identify queries that take longer than 10 seconds. The query store normalizes actual queries to aggregate similar queries. By default, entries are aggregated every 15 mins. Query utilizes mean execution time every 15 mins and other query statistics such as max, min can be used as appropriate.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreRuntimeStatistics"
| where user_id_s != "10" //exclude azure system user
| project TimeGenerated, LogicalServerName_s, event_type_s , mean_time_s , db_id_s , start_time_s , query_id_s, _ResourceId
| where todouble(mean_time_s) > 0 // You may change the time threshold
```




### Slowest queries  

Identify top 5 slowest queries.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreRuntimeStatistics"
| where user_id_s != "10" //exclude azure system user
| summarize avg(todouble(mean_time_s)) by event_class_s , db_id_s ,query_id_s
| top 5 by avg_mean_time_s desc

```




### Query statistics  

Construct a summary statistics table by query.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreRuntimeStatistics"
| where user_id_s != "10" //exclude azure system user
| summarize sum(toint(calls_s)), min(todouble(min_time_s)),max(todouble(max_time_s)),avg(todouble(mean_time_s)),percentile(todouble(mean_time_s),95) by  db_id_s ,query_id_s
| order by percentile_mean_time_s_95 desc nulls last 
```




### Execution count trends  

Execution trend by query aggregated by 15 minute-intervals.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreRuntimeStatistics"
| where user_id_s != "10" //exclude azure system user
| summarize sum(toint(calls_s)) by  tostring(query_id_s), bin(TimeGenerated, 15m), ResourceId
| render timechart 
```




### Top wait events  

Identify top 5 wait events by queries.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreWaitStatistics"
| where user_id_s != "10" //exclude azure system user
| where query_id_s != 0
| summarize sum(toint(calls_s)) by event_s, query_id_s, bin(TimeGenerated, 15m)
| top 5 by sum_calls_s desc nulls last
```




### Wait event trends  

Display wait event trends over time.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DBFORPOSTGRESQL"
| where Category == "QueryStoreWaitStatistics"
| where user_id_s != "10" //exclude azure system user
| extend query_id_s = tostring(query_id_s)
| summarize sum(toint(calls_s)) by event_s, query_id_s, bin(TimeGenerated, 15m), ResourceId // You may change the time threshold 
| render timechart
```



## Queries for microsoft.devices  

### Connectvity errors  

Identify device connection errors.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where Category == "Connections" and Level == "Error"
```




### Devices with most throttling errors  

Identify devices that made the most requests resulting in throttling errors.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where ResultType == "429001"
| extend DeviceId = tostring(parse_json(properties_s).deviceId)
| summarize count() by DeviceId, Category , _ResourceId
| order by count_ desc
```




### Dead endpoints  

Identify dead or unhealthy endpoints by the number times the issue was reported, as well as the reason why.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where Category == "Routes" and OperationName in ("endpointDead", "endpointUnhealthy")
| extend parsed_json = parse_json(properties_s)
| extend Endpoint   = tostring(parsed_json.endpointName), Reason =tostring(parsed_json.details) 
| summarize count() by Endpoint, OperationName, Reason, _ResourceId
| order by count_ desc
```




### Error summary  

Count of errors across all operations by type.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where Level == "Error"
| summarize count() by ResultType, ResultDescription, Category, _ResourceId
```




### Recently connected devices  

List of devices that IoT Hub saw connect in the specified time period.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where Category == "Connections" and OperationName == "deviceConnect"
| extend DeviceId = tostring(parse_json(properties_s).deviceId)
| summarize max(TimeGenerated) by DeviceId, _ResourceId
```




### SDK version of devices  

List of devices and their SDK versions.  

```query
// this query works on device connection or when your device uses device to cloud twin operations
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.DEVICES" and ResourceType == "IOTHUBS"
| where Category == "Connections" or  Category == "D2CTwinOperations"
| extend parsed_json = parse_json(properties_s) 
| extend SDKVersion = tostring(parsed_json.sdkVersion) , DeviceId = tostring(parsed_json.deviceId)
| distinct DeviceId, SDKVersion, TimeGenerated, _ResourceId
```



## Queries for microsoft.documentdb  

### Consumed RU/s in last 24 hours  

Identify consumed RU/s on Cosmos databases and collections.  

```query
// To create an alert for this query, click '+ New alert rule'
//You can compare the RU/s consumption with your provisioned RU/s to determine if you should scale up or down RU/s based on your workload.
AzureDiagnostics
| where TimeGenerated >= ago(24hr)
| where Category == "DataPlaneRequests"
//| where collectionName_s == "CollectionToAnalyze" //Replace to target the query to a collection
| summarize ConsumedRUsPerMinute = sum(todouble(requestCharge_s)) by collectionName_s, _ResourceId, bin(TimeGenerated, 1m)
| project TimeGenerated , ConsumedRUsPerMinute , collectionName_s, _ResourceId
| render timechart
```




### Collections with throttles (429) in past 24 hours  

Identify collections and operations that have received 429 (throttles), which occur when consumed throughput (RU/s) exceeds provisioned throughput.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where TimeGenerated >= ago(24hr)
| where Category == "DataPlaneRequests"
| where statusCode_s == 429 
| summarize numberOfThrottles = count() by databaseName_s, collectionName_s, requestResourceType_s, _ResourceId, bin(TimeGenerated, 1hr)
| order by numberOfThrottles
```




### Top operations by consumed Request Units (RUs) in last 24 hours  

Identify top operations on Cosmos resources by count and consumed RU per operation.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where TimeGenerated >= ago(24h)
| where Category == "DataPlaneRequests"
| summarize numberOfOperations = count(), totalConsumedRU = sum(todouble(requestCharge_s)) by databaseName_s, collectionName_s, OperationName, requestResourceType_s, requestResourceId_s, _ResourceId
| extend averageRUPerOperation = totalConsumedRU / numberOfOperations 
| order by numberOfOperations
```




### Top logical partition keys by storage  

Identify largest logical partition key values. PartitionKeyStatistics will emit data for top logical partition keys by storage.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where Category == "PartitionKeyStatistics"
//| where collectionName_s == "CollectionToAnalyze" //Replace to target the query to a collection
| summarize arg_max(TimeGenerated, *) by databaseName_s, collectionName_s, partitionKey_s, _ResourceId //Get the latest storage size
| extend utilizationOf20GBLogicalPartition = sizeKb_d / 20000000 //20GB
| project TimeGenerated, databaseName_s , collectionName_s , partitionKey_s, sizeKb_d, utilizationOf20GBLogicalPartition, _ResourceId
```



## Queries for microsoft.eventhub  

### [Classic] Duration of Capture failure  

Summarizes the duaration of failure on Capture.  

```query
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.EVENTHUB\"
| where Category == \"ArchiveLogs\"
| summarize count() by \"failures\", \"durationInSeconds\", _ResourceId
```




### [Classic] Join request for client  

Summarized the status of join request for client.  

```query
AzureDiagnostics // Need to turn on the Capture for this 
| where ResourceProvider == \"MICROSOFT.EVENTHUB\"
|  project \"OperationName\"

```




### [Classic] Access to keyvault - key not found  

Summarizes the access to keyvault when key is not found.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.EVENTHUB\"
| where Category == \"Error\" and OperationName == \"wrapkey\"
| project Message, _ResourceId
```




### [Classic] Operation performed with keyvault  

Summarizes the operation performed with keyvault to disable or restore the key.  

```query
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.EVENTHUB\"
| where Category == \"info\" and OperationName == \"disable\" or OperationName == \"restore\"
| project Message
```




### Errors in the last 7 days  

This lists all the errors for the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d)
| where ResourceProvider =="MICROSOFT.EVENTHUB"
| where Category == "OperationalLogs"
| summarize count() by "EventName", _ResourceId
```




### Duration of Capture failure  

Summarizes the duaration of failure on Capture.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.EVENTHUB"
| where Category == "ArchiveLogs"
| summarize count() by "failures", "durationInSeconds", _ResourceId
```




### Join request for client  

Summarized the status of join request for client.  

```query
AzureDiagnostics // Need to turn on the Capture for this 
| where ResourceProvider == "MICROSOFT.EVENTHUB"
|  project "OperationName"
```




### Access to keyvault - key not found  

Summarizes the access to keyvault when key is not found.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.EVENTHUB" 
| where Category == "Error" and OperationName == "wrapkey"
| project Message, ResourceId
```




### Operation performed with keyvault  

Summarizes the operation performed with keyvault to disable or restore the key.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.EVENTHUB"
| where Category == "info" and OperationName == "disable" or OperationName == "restore"
| project Message
```



## Queries for microsoft.keyvault  

### [Classic] How active has this KeyVault been?  

[Classic] Line chart showing trend of KeyVault requests volume, per operation over time.  

```query
// KeyVault diagnostic currently stores logs in AzureDiagnostics table which stores logs for multiple services. 
// Filter on ResourceProvider for logs specific to a service.
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.KEYVAULT" 
| summarize count() by bin(TimeGenerated, 1h), OperationName // Aggregate by hour
| render timechart
```




### [Classic] Who is calling this KeyVault?  

[Classic] List of callers identified by their IP address with their request count.   

```query
// KeyVault diagnostic currently stores logs in AzureDiagnostics table which stores logs for multiple services. 
// Filter on ResourceProvider for logs specific to a service.
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.KEYVAULT"
| summarize count() by CallerIPAddress
```




### [Classic] Are there any slow requests?  

[Classic] List of KeyVault requests that took longer than 1sec.  

```query
// To create an alert for this query, click '+ New alert rule'
let threshold=1000; // let operator defines a constant that can be further used in the query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.KEYVAULT" 
| where DurationMs > threshold
| summarize count() by OperationName, _ResourceId
```




### [Classic] How fast is this KeyVault serving requests?  

[Classic] Line chart showing trend of request duration over time using different aggregations.   

```query
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.KEYVAULT" 
| summarize avg(DurationMs) by requestUri_s, bin(TimeGenerated, 1h) // requestUri_s contains the URI of the request
| render timechart
```




### [Classic] Are there any failures?  

[Classic] Count of failed KeyVault requests by status code.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider =="MICROSOFT.KEYVAULT" 
| where httpStatusCode_d >= 300 and not(OperationName == "Authentication" and httpStatusCode_d == 401)
| summarize count() by requestUri_s, ResultSignature, _ResourceId
// ResultSignature contains HTTP status, e.g. "OK" or "Forbidden"
// httpStatusCode_d contains HTTP status code returned by the request (e.g.  200, 300 or 401)
// requestUri_s contains the URI of the request
```




### [Classic] What changes occurred last month?  

[Classic] Lists all update and patch requests from the last 30 days.  

```query
// KeyVault diagnostic currently stores logs in AzureDiagnostics table which stores logs for multiple services. 
// Filter on ResourceProvider for logs specific to a service.
AzureDiagnostics
| where TimeGenerated > ago(30d) // Time range specified in the query. Overrides time picker in portal.
| where ResourceProvider =="MICROSOFT.KEYVAULT" 
| where OperationName == "VaultPut" or OperationName == "VaultPatch"
| sort by TimeGenerated desc
```




### [Classic] List all input deserialization errors  

[Classic] Shows errors caused due to malformed events that could not be deserialized by the job.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.KEYVAULT" and parse_json(properties_s).DataErrorType in ("InputDeserializerError.InvalidData", "InputDeserializerError.TypeConversionError", "InputDeserializerError.MissingColumns", "InputDeserializerError.InvalidHeader", "InputDeserializerError.InvalidCompressionType")
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### [Classic] Find In AzureDiagnostics  

[Classic] Find in AzureDiagnostics to search for a specific value in the AzureDiagnostics table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.KEYVAULT"
| where * contains tostring(SearchValue)
| take 1000
```



## Queries for microsoft.logic  

### Total billable executions  

Total billable executions by operation name.  

```query
// Total billable executions
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.LOGIC"
| where Category == "WorkflowRuntime" 
| where OperationName has "workflowTriggerStarted" or OperationName has "workflowActionStarted" 
| summarize dcount(resource_runId_s) by OperationName, resource_workflowName_s
```




### Logic App execution distribution by workflows  

Hourly timechart for Logic App execution, distribution by workflows.  

```query
// Hourly Time chart for Logic App execution distribution by workflows
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.LOGIC"
| where Category == "WorkflowRuntime"
| where OperationName has "workflowRunStarted"
| summarize dcount(resource_runId_s) by bin(TimeGenerated, 1h), resource_workflowName_s
| render timechart 
```




### Logic App execution distribution by status  

Completed executions by workflow,status and error.  

```query
//logic app execution status summary
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.LOGIC"
| where OperationName has "workflowRunCompleted"
| summarize dcount(resource_runId_s) by resource_workflowName_s, status_s, error_code_s
| project LogicAppName = resource_workflowName_s , NumberOfExecutions = dcount_resource_runId_s , RunStatus = status_s , Error = error_code_s 
```




### Triggered failures count  

Show Action/Trigger failures for all Logic App executions by Resource name.  

```query
// To create an alert for this query, click '+ New alert rule'
//Action/Trigger failures for all Logic App executions
AzureDiagnostics
| where ResourceProvider  == "MICROSOFT.LOGIC"  
| where Category == "WorkflowRuntime" 
| where status_s == "Failed" 
| where OperationName has "workflowActionCompleted" or OperationName has "workflowTriggerCompleted" 
| extend ResourceName = coalesce(resource_actionName_s, resource_triggerName_s) 
| extend ResourceCategory = substring(OperationName, 34, strlen(OperationName) - 43) | summarize dcount(resource_runId_s) by code_s, ResourceName, resource_workflowName_s, ResourceCategory, _ResourceId
| project ResourceCategory, ResourceName , FailureCount = dcount_resource_runId_s , ErrorCode = code_s, LogicAppName = resource_workflowName_s, _ResourceId 
| order by FailureCount desc 
```



## Queries for microsoft.network  

### Requests per hour  

Count of the incoming requests on the Application Gateway.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess"
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```




### Non-SSL requests per hour  

Count of the Non-SSL requests on the Application Gateway.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess" and sslEnabled_s == "off"
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```




### Failed requests per hour  

Count of requests to which Application Gateway responded with an error.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess" and httpStatus_d > 399
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```




### Errors by user agent  

Number of errors by user agent.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess" and httpStatus_d > 399
| summarize AggregatedValue = count() by userAgent_s, _ResourceId
| sort by AggregatedValue desc
```




### Errors by URI  

Number of errors by URI.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess" and httpStatus_d > 399
| summarize AggregatedValue = count() by requestUri_s, _ResourceId
| sort by AggregatedValue desc
```




### Top 10 Client IPs  

Count of requests per client IP.  

```query
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess"
| summarize AggregatedValue = count() by clientIP_s
| top 10 by AggregatedValue
```




### Top HTTP versions  

Count of request per HTTP version.  

```query
AzureDiagnostics
| where ResourceType == "APPLICATIONGATEWAYS" and OperationName == "ApplicationGatewayAccess"
| summarize AggregatedValue = count() by httpVersion_s
| top 10 by AggregatedValue
```




### Network security events  

Find Network security events reporting blocked incoming traffic.  

```query
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.NETWORK"  
| where Category == "NetworkSecurityGroupEvent"  
| where direction_s == "In" and type_s == "block"
```




### Requests per hour  

Render line chart showing total requests per hour for each FrontDoor resource.  

```query
// Summarize number of requests per hour for each FrontDoor resource
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorAccessLog"
| summarize RequestCount = count() by bin(TimeGenerated, 1h), Resource, ResourceId
| render timechart 
```




### Forwarded backend requests by routing rule  

Count number of requests for each routing rule and backend host per minute.  

```query
// Summarize number of requests per minute for each routing rule and backend host
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorAccessLog"
| summarize RequestCount = count() by bin(TimeGenerated, 1m), Resource, RoutingRuleName = routingRuleName_s, BackendHostname = backendHostname_s, ResourceId
```




### Request errors by host and path  

Count number of requests with error responses by host and path.  

```query
// Summarize number of requests by host, path, and status codes >= 400
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorAccessLog"
| where toint(httpStatusCode_s) >= 400
| extend ParsedUrl = parseurl(requestUri_s)
| summarize RequestCount = count() by Host = tostring(ParsedUrl.Host), Path = tostring(ParsedUrl.Path), StatusCode = httpStatusCode_s, ResourceId
| order by RequestCount desc 
```




### Request errors by user agent  

Count number of requests with error responses by user agent.  

```query
// Summarize number of requests per user agent and status codes >= 400
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorAccessLog"
| where toint(httpStatusCode_s) >= 400
| summarize RequestCount = count() by UserAgent = userAgent_s, StatusCode = httpStatusCode_s , Resource, ResourceId
| order by RequestCount desc 
```




### Top 10 client IPs and http versions  

Show top 10 client IPs and http versions.  

```query
// Summarize top 10 client ips and http versions
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorAccessLog"
| summarize RequestCount = count() by ClientIP = clientIp_s, HttpVersion = httpVersion_s, Resource
| top 10 by RequestCount 
| order by RequestCount desc
```




### Firewall blocked request count per hour  

Count number of firewall blocked requests per hour.  

```query
// Summarize number of firewall blocked requests per hour by policy
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorWebApplicationFirewallLog"
| where action_s == "Block"
| summarize RequestCount = count() by bin(TimeGenerated, 1h), Policy = policy_s, PolicyMode = policyMode_s, Resource, ResourceId
| order by RequestCount desc
```




### Top 20 blocked clients by IP and rule  

Show top 20 blocked clients by IP and rule name.  

```query
// Summarize top 20 blocked clients by IP and rule
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorWebApplicationFirewallLog"
| where action_s == "Block"
| summarize RequestCount = count() by ClientIP = clientIP_s, UserAgent = userAgent_s, RuleName = ruleName_s ,Resource
| top 20 by RequestCount 
| order by RequestCount desc
```




### Firewall request count by host, path, rule, and action  

Count firewall processed requests by host, path, rule, and action taken.  

```query
// Summarize request count by host, path, rule, and action
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.NETWORK" and Category == "FrontdoorWebApplicationFirewallLog"
| extend ParsedUrl = parseurl(requestUri_s)
| summarize RequestCount = count() by Host = tostring(ParsedUrl.Host), Path = tostring(ParsedUrl.Path), RuleName = ruleName_s, Action = action_s, ResourceId
| order by RequestCount desc
```




### Application rule log data  

Parses the application rule log data.  

```query
AzureDiagnostics
| where Category == "AzureFirewallApplicationRule"
//this first parse statement is valid for all entries as they all start with this format
| parse msg_s with Protocol " request from " SourceIP ":" SourcePort:int * 
//Parse action as this is the same for all log lines 
| parse kind=regex flags=U msg_s with * ". Action\\: " Action "\\."
// case1: Action: A. Reason: R.
| parse kind=regex flags=U msg_s with "\\. Reason\\: " Reason "\\."
//case 2a: to FQDN:PORT Url: U. Action: A. Policy: P. Rule Collection Group: RCG. Rule Collection: RC. Rule: R.
| parse msg_s with * "to " FQDN ":" TargetPort:int * "." *
//Parse policy if present
| parse msg_s with * ". Policy: " Policy ". Rule Collection Group: " RuleCollectionGroup "." *
| parse msg_s with * " Rule Collection: " RuleCollection ". Rule: " Rule
//case 2.b: Web Category: WC.
| parse Rule with * ". Web Category: " WebCategory
//case 3: No rule matched. Proceeding with default action"
| extend DefaultRule = iff(msg_s contains "No rule matched. Proceeding with default action", true, false)
| extend 
SourcePort = tostring(SourcePort),
TargetPort = tostring(TargetPort)
| extend 
 Action = case(Action == "","N/A", case(DefaultRule, "Deny" ,Action)),
 FQDN = case(FQDN == "", "N/A", FQDN),
 TargetPort = case(TargetPort == "", "N/A", tostring(TargetPort)),
 Policy = case(RuleCollection contains ":", split(RuleCollection, ":")[0] ,case(Policy == "", "N/A", Policy)),
 RuleCollectionGroup = case(RuleCollection contains ":", split(RuleCollection, ":")[1], case(RuleCollectionGroup == "", "N/A", RuleCollectionGroup)),
 RuleCollection = case(RuleCollection contains ":", split(RuleCollection, ":")[2], case(RuleCollection == "", "N/A", RuleCollection)),
 WebCategory = case(WebCategory == "", "N/A", WebCategory),
 Rule = case(Rule == "" , "N/A", case(WebCategory == "N/A", Rule, split(Rule, '.')[0])),
 Reason = case(Reason == "", case(DefaultRule, "No rule matched - default action", "N/A"), Reason )
| project TimeGenerated, msg_s, Protocol, SourceIP, SourcePort, FQDN, TargetPort, Action, Policy, RuleCollectionGroup, RuleCollection, Rule, Reason ,WebCategory
```




### Network rule log data  

Parses the network rule log data.  

```query
AzureDiagnostics
| where Category == "AzureFirewallNetworkRule"
| where OperationName == "AzureFirewallNatRuleLog" or OperationName == "AzureFirewallNetworkRuleLog"
//case 1: for records that look like this:
//PROTO request from IP:PORT to IP:PORT.
| parse msg_s with Protocol " request from " SourceIP ":" SourcePortInt:int " to " TargetIP ":" TargetPortInt:int *
//case 1a: for regular network rules
| parse kind=regex flags=U msg_s with * ". Action\\: " Action1a "\\."
//case 1b: for NAT rules
//TCP request from IP:PORT to IP:PORT was DNAT'ed to IP:PORT
| parse msg_s with * " was " Action1b:string " to " TranslatedDestination:string ":" TranslatedPort:int *
//Parse rule data if present
| parse msg_s with * ". Policy: " Policy ". Rule Collection Group: " RuleCollectionGroup "." *
| parse msg_s with * " Rule Collection: "  RuleCollection ". Rule: " Rule 
//case 2: for ICMP records
//ICMP request from 10.0.2.4 to 10.0.3.4. Action: Allow
| parse msg_s with Protocol2 " request from " SourceIP2 " to " TargetIP2 ". Action: " Action2
| extend
SourcePort = tostring(SourcePortInt),
TargetPort = tostring(TargetPortInt)
| extend 
    Action = case(Action1a == "", case(Action1b == "",Action2,Action1b), split(Action1a,".")[0]),
    Protocol = case(Protocol == "", Protocol2, Protocol),
    SourceIP = case(SourceIP == "", SourceIP2, SourceIP),
    TargetIP = case(TargetIP == "", TargetIP2, TargetIP),
    //ICMP records don't have port information
    SourcePort = case(SourcePort == "", "N/A", SourcePort),
    TargetPort = case(TargetPort == "", "N/A", TargetPort),
    //Regular network rules don't have a DNAT destination
    TranslatedDestination = case(TranslatedDestination == "", "N/A", TranslatedDestination), 
    TranslatedPort = case(isnull(TranslatedPort), "N/A", tostring(TranslatedPort)),
    //Rule information
    Policy = case(Policy == "", "N/A", Policy),
    RuleCollectionGroup = case(RuleCollectionGroup == "", "N/A", RuleCollectionGroup ),
    RuleCollection = case(RuleCollection == "", "N/A", RuleCollection ),
    Rule = case(Rule == "", "N/A", Rule)
| project TimeGenerated, msg_s, Protocol, SourceIP,SourcePort,TargetIP,TargetPort,Action, TranslatedDestination, TranslatedPort, Policy, RuleCollectionGroup, RuleCollection, Rule
```




### Threat Intelligence rule log data  

Parses the Threat Intelligence rule log data.  

```query
AzureDiagnostics
| where OperationName  == "AzureFirewallThreatIntelLog"
| parse msg_s with Protocol " request from " SourceIP ":" SourcePortInt:int " to " TargetIP ":" TargetPortInt:int *
| parse msg_s with * ". Action: " Action "." Message
| parse msg_s with Protocol2 " request from " SourceIP2 " to " TargetIP2 ". Action: " Action2
| extend SourcePort = tostring(SourcePortInt),TargetPort = tostring(TargetPortInt)
| extend Protocol = case(Protocol == "", Protocol2, Protocol),SourceIP = case(SourceIP == "", SourceIP2, SourceIP),TargetIP = case(TargetIP == "", TargetIP2, TargetIP),SourcePort = case(SourcePort == "", "N/A", SourcePort),TargetPort = case(TargetPort == "", "N/A", TargetPort)
| sort by TimeGenerated desc 
| project TimeGenerated, msg_s, Protocol, SourceIP,SourcePort,TargetIP,TargetPort,Action,Message
```




### Azure Firewall log data  

Start from this query if you want to parse the logs from network rules, application rules, NAT rules, IDS, threat intelligence and more to understand why certain traffic was allowed or denied. This query will show the last 100 log records but by adding simple filter statements at the end of the query the results can be tweaked.  

```query
// Parses the azure firewall rule log data. 
// Includes network rules, application rules, threat intelligence, ips/ids, ...
AzureDiagnostics
| where Category == "AzureFirewallNetworkRule" or Category == "AzureFirewallApplicationRule"
//optionally apply filters to only look at a certain type of log data
//| where OperationName == "AzureFirewallNetworkRuleLog"
//| where OperationName == "AzureFirewallNatRuleLog"
//| where OperationName == "AzureFirewallApplicationRuleLog"
//| where OperationName == "AzureFirewallIDSLog"
//| where OperationName == "AzureFirewallThreatIntelLog"
| extend msg_original = msg_s
// normalize data so it's eassier to parse later
| extend msg_s = replace(@'. Action: Deny. Reason: SNI TLS extension was missing.', @' to no_data:no_data. Action: Deny. Rule Collection: default behavior. Rule: SNI TLS extension missing', msg_s)
| extend msg_s = replace(@'No rule matched. Proceeding with default action', @'Rule Collection: default behavior. Rule: no rule matched', msg_s)
// extract web category, then remove it from further parsing
| parse msg_s with * " Web Category: " WebCategory
| extend msg_s = replace(@'(. Web Category:).*','', msg_s)
// extract RuleCollection and Rule information, then remove it from further parsing
| parse msg_s with * ". Rule Collection: " RuleCollection ". Rule: " Rule
| extend msg_s = replace(@'(. Rule Collection:).*','', msg_s)
// extract Rule Collection Group information, then remove it from further parsing
| parse msg_s with * ". Rule Collection Group: " RuleCollectionGroup
| extend msg_s = replace(@'(. Rule Collection Group:).*','', msg_s)
// extract Policy information, then remove it from further parsing
| parse msg_s with * ". Policy: " Policy
| extend msg_s = replace(@'(. Policy:).*','', msg_s)
// extract IDS fields, for now it's always add the end, then remove it from further parsing
| parse msg_s with * ". Signature: " IDSSignatureIDInt ". IDS: " IDSSignatureDescription ". Priority: " IDSPriorityInt ". Classification: " IDSClassification
| extend msg_s = replace(@'(. Signature:).*','', msg_s)
// extra NAT info, then remove it from further parsing
| parse msg_s with * " was DNAT'ed to " NatDestination
| extend msg_s = replace(@"( was DNAT'ed to ).*",". Action: DNAT", msg_s)
// extract Threat Intellingence info, then remove it from further parsing
| parse msg_s with * ". ThreatIntel: " ThreatIntel
| extend msg_s = replace(@'(. ThreatIntel:).*','', msg_s)
// extract URL, then remove it from further parsing
| extend URL = extract(@"(Url: )(.*)(\. Action)",2,msg_s)
| extend msg_s=replace(@"(Url: .*)(Action)",@"\2",msg_s)
// parse remaining "simple" fields
| parse msg_s with Protocol " request from " SourceIP " to " Target ". Action: " Action
| extend 
    SourceIP = iif(SourceIP contains ":",strcat_array(split(SourceIP,":",0),""),SourceIP),
    SourcePort = iif(SourceIP contains ":",strcat_array(split(SourceIP,":",1),""),""),
    Target = iif(Target contains ":",strcat_array(split(Target,":",0),""),Target),
    TargetPort = iif(SourceIP contains ":",strcat_array(split(Target,":",1),""),""),
    Action = iif(Action contains ".",strcat_array(split(Action,".",0),""),Action),
    Policy = case(RuleCollection contains ":", split(RuleCollection, ":")[0] ,Policy),
    RuleCollectionGroup = case(RuleCollection contains ":", split(RuleCollection, ":")[1], RuleCollectionGroup),
    RuleCollection = case(RuleCollection contains ":", split(RuleCollection, ":")[2], RuleCollection),
    IDSSignatureID = tostring(IDSSignatureIDInt),
    IDSPriority = tostring(IDSPriorityInt)
| project msg_original,TimeGenerated,Protocol,SourceIP,SourcePort,Target,TargetPort,URL,Action, NatDestination, OperationName,ThreatIntel,IDSSignatureID,IDSSignatureDescription,IDSPriority,IDSClassification,Policy,RuleCollectionGroup,RuleCollection,Rule,WebCategory
| order by TimeGenerated
| limit 100
```




### Azure Firewall DNS proxy log data  

Start from this query if you want to understand the Firewall DNS proxy log data. This query will show the last 100 log records but by adding simple filter statements at the end of the query the results can be tweaked.  

```query
// DNS proxy log data 
// Parses the DNS proxy log data. 
AzureDiagnostics
| where Category == "AzureFirewallDnsProxy"
| parse msg_s with "DNS Request: " SourceIP ":" SourcePortInt:int " - " QueryID:int " " RequestType " " RequestClass " " hostname ". " protocol " " details
| extend
    ResponseDuration = extract("[0-9]*.?[0-9]+s$", 0, msg_s),
    SourcePort = tostring(SourcePortInt),
    QueryID =  tostring(QueryID)
| project TimeGenerated,SourceIP,hostname,RequestType,ResponseDuration,details,msg_s
| order by TimeGenerated
| limit 100
```




### BGP route table  

BPG route table learned over last 12 hours.  

```query
AzureDiagnostics
| where TimeGenerated > ago(12h)
| where ResourceType == "EXPRESSROUTECIRCUITS"
| project TimeGenerated , ResourceType , network_s , path_s , OperationName
```




### BGP informational messages  

BGP informational messages by level, resource type and network.  

```query
AzureDiagnostics
| where Level == "Informational"
| project TimeGenerated , ResourceId, Level, ResourceType , network_s , path_s
```




### Endpoints with monitoring Status down  

Find the reason why the monitoring status of Azure Traffic Manager endpoints is down.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceType == "TRAFFICMANAGERPROFILES"  and Category  == "ProbeHealthStatusEvents"
| where Status_s == "Down"
| project TimeGenerated, EndpointName_s, Status_s, ResultDescription, SubscriptionId , _ResourceId
```




### Successful P2S connections  

Successful P2S connections in the last 12 hours.  

```query
AzureDiagnostics 
| where TimeGenerated > ago(12h)
| where Category == "P2SDiagnosticLog" and Message has "Connection successful"
| project TimeGenerated, Resource ,Message
```




### Failed P2S connections  

Failed P2S connections in the last 12 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where TimeGenerated > ago(12h)
| where Category == "P2SDiagnosticLog" and Message has "Connection failed"
| project TimeGenerated, Resource ,Message
```




### Gateway configuration changes  

Successful gateway configuration changes made by administrator during the last 24 hours.  

```query
AzureDiagnostics
| where TimeGenerated > ago(24h)
| where Category == "GatewayDiagnosticLog" and operationStatus_s == "Success" and configuration_ConnectionTrafficType_s == "Internet"
| project TimeGenerated, Resource, OperationName, Message, operationStatus_s
```




### S2S tunnel connet/disconnect events  

S2S tunnel connet/disconnect events during the last 24 hours.  

```query
AzureDiagnostics 
| where TimeGenerated > ago(24h)
| where Category == "TunnelDiagnosticLog" and (status_s == "Connected" or status_s == "Disconnected")
| project TimeGenerated, Resource , status_s, remoteIP_s, stateChangeReason_s
```




### BGP route updates  

BGP route updates over the last 24 hours.  

```query
AzureDiagnostics
| where TimeGenerated > ago(24h)
| where Category == "RouteDiagnosticLog" and OperationName == "BgpRouteUpdate"
```




### Show logs from AzureDiagnostics table  

Lists the latest logs in AzureDiagnostics table, sorted by time (latest first).  

```query
AzureDiagnostics
| top 10 by TimeGenerated
```



## Queries for microsoft.recoveryservices  

### Failed backup jobs  

Find logs reported failed backup jobs from the last day.  

```query
AzureDiagnostics  
| where ResourceProvider == "MICROSOFT.RECOVERYSERVICES" and Category == "AzureBackupReport"  
| where OperationName == "Job" and JobOperation_s == "Backup" and JobStatus_s == "Failed" 
| project TimeGenerated, JobUniqueId_g, JobStartDateTime_s, JobOperation_s, JobOperationSubType_s, JobStatus_s , JobFailureCode_s, JobDurationInSecs_s , AdHocOrScheduledJob_s
```



## Queries for microsoft.servicebus  

### [Classic] List Management operations  

This lists all the management calls.  

```query
AzureDiagnostics
| where ResourceProvider ==\"MICROSOFT.SERVICEBUS\"
| where Category == \"OperationalLogs\"
| summarize count() by EventName_s, _ResourceId
```




### [Classic] Error Summary  

Summarizes all the errors encountered.  

```query
AzureDiagnostics
| where ResourceProvider ==\"MICROSOFT.SERVICEBUS\"
| where Category == \"Error\"
| summarize count() by EventName_s, _ResourceId
```




### [Classic] Keyvault access attempt - key not found  

Summarizes the access to keyvault when key is not found.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.SERVICEBUS\"
| where Category == \"Error\" and OperationName == \"wrapkey\"
| project Message, _ResourceId

```




### [Classic] AutoDeleted entities  

Summary of all the entities that have been auto-deleted.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.SERVICEBUS\"
| where Category == \"OperationalLogs\"
| where EventName_s startswith \"AutoDelete\"
| summarize count() by EventName_s, _ResourceId
```




### [Classic] Keyvault performed operational  

Summarizes the operation performed with keyvault to disable or restore the key.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == \"MICROSOFT.SERVICEBUS\"
| where (Category == \"info\" and (OperationName == \"disable\" or OperationName == \"restore\"))
| project Message, _ResourceId
```




### Management operations in the last 7 days  

This lists all the management calls for the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d)
| where ResourceProvider =="MICROSOFT.SERVICEBUS"
| where Category == "OperationalLogs"
| summarize count() by EventName_s, _ResourceId
```




### Errors summary  

Summarizes all the errors seen in the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d)
| where ResourceProvider =="MICROSOFT.SERVICEBUS"
| where Category == "Error" 
| summarize count() by EventName_s, _ResourceId
```




### Keyvault access attempt - key not found  

Summarizes the access to keyvault when key is not found.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.SERVICEBUS" 
| where Category == "Error" and OperationName == "wrapkey"
| project Message, _ResourceId
```




### AutoDeleted entities  

Summary of all the entities that have been auto-deleted.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.SERVICEBUS"
| where Category == "OperationalLogs"
| where EventName_s startswith "AutoDelete"
| summarize count() by EventName_s, _ResourceId
```




### Keyvault performed operational  

Summarizes the operation performed with keyvault to disable or restore the key.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.SERVICEBUS"
| where (Category == "info" and (OperationName == "disable" or OperationName == "restore"))
| project Message, _ResourceId
```



## Queries for microsoft.sql  

### Storage on managed instances above 90%  

Display all managed instances with storage utilization above 90%.  

```query
// To create an alert for this query, click '+ New alert rule'
let storage_percentage_threshold = 90;
AzureDiagnostics
| where Category =="ResourceUsageStats"
| summarize (TimeGenerated, calculated_storage_percentage) = arg_max(TimeGenerated, todouble(storage_space_used_mb_s) *100 / todouble (reserved_storage_mb_s))
   by _ResourceId
| where calculated_storage_percentage > storage_percentage_threshold
```




### CPU utilization treshold above 95% on managed instances  

Display all managed instances with CPU treshold being over 95% of treshold.  

```query
// To create an alert for this query, click '+ New alert rule'
let cpu_percentage_threshold = 95;
let time_threshold = ago(1h);
AzureDiagnostics
| where Category == "ResourceUsageStats" and TimeGenerated > time_threshold
| summarize avg_cpu = max(todouble(avg_cpu_percent_s)) by _ResourceId
| where avg_cpu > cpu_percentage_threshold
```




### Display all active intelligent insights  

Display all active performance issues detected by intelligent insights. Please note that SQLInsights log needs to be enabled for each database monitored.  

```query
AzureDiagnostics
| where Category == "SQLInsights" and status_s == "Active"
| distinct rootCauseAnalysis_s
```




### Wait stats  

Wait stats over the last hour, by Logical Server and Database.  

```query
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.SQL"
| where TimeGenerated >= ago(60min)
| parse _ResourceId with * "/microsoft.sql/servers/" LogicalServerName "/databases/" DatabaseName
| summarize Total_count_60mins = sum(delta_waiting_tasks_count_d) by LogicalServerName, DatabaseName, wait_type_s
```



## Queries for microsoft.streamanalytics  

### List all input data errors  

Shows all errors that occurred while processing the data from inputs.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics 
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).Type == "DataError" 
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all input deserialization errors  

Shows errors caused due to malformed events that could not be deserialized by the job.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType in ("InputDeserializerError.InvalidData", "InputDeserializerError.TypeConversionError", "InputDeserializerError.MissingColumns", "InputDeserializerError.InvalidHeader", "InputDeserializerError.InvalidCompressionType")
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all InvalidInputTimeStamp errors  

Shows errors caused due to events where value of the TIMESTAMP BY expression can't be converted to datetime.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and  parse_json(properties_s).DataErrorType == "InvalidInputTimeStamp"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all InvalidInputTimeStampKey errors  

Shows errors caused due to events where value of the TIMESTAMP BY OVER timestampColumn is NULL.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and  parse_json(properties_s).DataErrorType == "InvalidInputTimeStampKey"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Events that arrived late  

Shows errors due to events where difference between application time and arrival time is greater than the late arrival policy.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and  parse_json(properties_s).DataErrorType == "LateInputEvent"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Events that arrived early  

Shows errors due to events where difference between Application time and Arrival time is greater than 5 minutes.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "EarlyInputEvent"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Events that arrived out of order  

Shows errors due to events that arrive out of order according to the out-of-order policy.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "OutOfOrderEvent"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### All output data errors  

Shows all errors that occurred while writing the results of the query to the outputs in your job.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType in ("OutputDataConversionError.RequiredColumnMissing", "OutputDataConversionError.ColumnNameInvalid", "OutputDataConversionError.TypeConversionError", "OutputDataConversionError.RecordExceededSizeLimit", "OutputDataConversionError.DuplicateKey")
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all RequiredColumnMissing errors  

Shows all errors where the output record produced by your job has a missing column.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "OutputDataConversionError.RequiredColumnMissing"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all ColumnNameInvalid errors  

Shows errors where the output record produced by your job has a column name that doesn't map to a column in your output.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "OutputDataConversionError.ColumnNameInvalid"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all TypeConversionError errors  

Shows errors where the output record produced by your job has a column can't be converted to a valid type in the output.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "OutputDataConversionError.TypeConversionError"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all RecordExceededSizeLimit errors  

Shows errors where the size of the output record produced by your job is greater than the supported output size.   

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and  parse_json(properties_s).DataErrorType == "OutputDataConversionError.RecordExceededSizeLimit"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### List all DuplicateKey errors  

Shows errors where the output record produced by job contains a column with the same name as a System column.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).DataErrorType == "OutputDataConversionError.DuplicateKey"
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### All logs with level "Error"  

Shows all logs that are likely to have negatively impacted your job.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and Level == "Error" 
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Operations that have "Failed"  

Shows all operations on your job that have resulted in a failure.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and status_s == "Failed" 
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Output Throttling logs (Cosmos DB, Power BI, Event Hubs)  

Shows all instances where writing to one of your outputs was throttled by the destination service.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).Type in ("DocumentDbOutputAdapterWriteThrottlingError", "EventHubOutputAdapterEventHubThrottlingError", "PowerBIServiceThrottlingError", "PowerBIServiceThrottlingError")
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Transient input and output errors  

Shows all errors related to input and output that are intermittent in nature.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).Type in ("AzureFunctionOutputAdapterTransientError", "BlobInputAdapterTransientError", "DataLakeOutputAdapterTransientError", "DocumentDbOutputAdapterTransientError", "EdgeHubOutputAdapterEdgeHubTransientError", "EventHubBasedInputInvalidOperationTransientError", "EventHubBasedInputOperationCanceledTransientError", "EventHubBasedInputTimeoutTransientError", "EventHubBasedInputTransientError", "EventHubOutputAdapterEventHubTransientError", "InputProcessorTransientFailure", "OutputProcessorTransientError", "ReferenceDataInputAdapterTransientError", "ServiceBusOutputAdapterTransientError", "TableOutputAdapterTransientError")
| project TimeGenerated, Resource, Region_s, OperationName, properties_s, Level, _ResourceId
```




### Summary of all data errors in the last 7 days  

Summary of all data errors in the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d) //last 7 days
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and parse_json(properties_s).Type == "DataError"
| extend DataErrorType = tostring(parse_json(properties_s).DataErrorType)
| summarize Count=count(), sampleEvent=any(properties_s)  by DataErrorType, JobName=Resource
```




### Summary of all errors in the last 7 days  

Summary of all errors in the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d) //last 7 days
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS"
| extend ErrorType = tostring(parse_json(properties_s).Type)
| summarize Count=count(), sampleEvent=any(properties_s)  by ErrorType, JobName=Resource
```




### Summary of 'Failed' operations in the last 7 days  

Summary of 'Failed' operations in the last 7 days.  

```query
AzureDiagnostics
| where TimeGenerated > ago(7d) //last 7 days
| where ResourceProvider == "MICROSOFT.STREAMANALYTICS" and status_s == "Failed" 
| summarize Count=count(), sampleEvent=any(properties_s) by JobName=Resource  
```

