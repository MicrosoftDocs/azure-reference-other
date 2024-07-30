---
title: Example log table queries for ABSBotRequests
description:  Example queries for ABSBotRequests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ABSBotRequests table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Clients To Direct Line Channel  


Logs of Clients to Direct Line channel requests.  

```query
// All the API calls that clients make to Direct Line channel
// e.g. Generate a Token, Refresh a Token, Post an Activity, Get Activities, GetAttachments, etc.
// You can adjust the limit value to the number of logs you would like to retrieve.
ABSBotRequests
| where OperationName contains "ClientToDirectLine"
| sort by TimeGenerated desc
| limit 100
```



### Bot To Channels  


Logs of requests from the Bot to channels.  

```query
// This shows logs of requests sent by the bot to Azure Bot Service channels.
// You can adjust the limit value to the number of logs you would like to retrieve.
ABSBotRequests
| where OperationName contains "BotToChannel"
| sort by TimeGenerated desc
| limit 100
```



### Channels To Bot  


Logs of requests from Channels to the bot.  

```query
// This query retrieves logs of requests sent from Azure Bot Service channels to the bot.
// You can adjust the limit value to the number of logs you would like to retrieve.
ABSBotRequests
| where OperationName contains "ChannelToBot"
| sort by TimeGenerated desc
| limit 100
```



### Requests From Facebook To Azure Bot Service  


Logs of requests from Facebook to Azure Bot Service Facebook Channel.  

```query
// To retrieve logs for another channel, replace FacebookToChannel with the respective channel request operation name 
// e.g. SlackToChannel, KikToChannel, GroupmeToChannel, LineToChannel, SMSToChannel, TelegramToChannel and EmailToChannel.
ABSBotRequests
| where OperationName contains "FacebookToChannel"
| sort by TimeGenerated desc
```



### Requests From Azure Bot Service To Facebook API  


Logs of requests from Azure Bot Service Facebook Channel to Facebook API.  

```query
// To retrieve logs for another channel, replace ChannelToFacebookAPI with the respective channel request operation name 
// e.g. ChannelToSlackAPI, ChannelToGroupmeAPI, ChannelToKikAPI, ChannelToLineAPI, ChannelToSMSAPI, ChannelToTelegramAPI and ChannelToEmailAPI.
ABSBotRequests
| where OperationName contains "ChannelToFacebookAPI"
| sort by TimeGenerated desc
```



### Activities Sent from Clients to Direct Line  


Logs of requests to send activities from a client to Direct Line channel.  

```query
// This query displays logs of requests sent from a client such as WebChat to Direct Line channel.
// Replace 'SendAnActivity:ClientToDirectLine' with any operation name whose logs you would like to retrieve.
ABSBotRequests
| where OperationName == 'SendAnActivity:ClientToDirectLine'
| sort by TimeGenerated desc
```



### Direct Line Channel Logs  


Retrieve logs associated with Direct Line channel.  

```query
// This query retrieves logs of requests related to Direct Line channel.
ABSBotRequests
| where Channel == "directline"
| sort by TimeGenerated desc
```



### Failed Requests  


List of logs of unsuccessful requests.  

```query
// Retrieve all logs of requests that have not been successful within a selected time range.
ABSBotRequests
| where ResultCode < 200 or ResultCode >= 300
| sort by TimeGenerated desc
```



### Direct Line Channel Response Codes Line Chart  


Line Chart showing Direct Line channel requests response codes.  

```query
// This query displays a Line Chart showing requests related to Direct Line channel.
ABSBotRequests
| where Channel == "directline"
| summarize Number_Of_Requests = count() by tostring(ResultCode), bin(TimeGenerated, 5m)
| render timechart
```



### Requests Duration Line Chart  


Line Chart showing requests response times/duration per operation.  

```query
// This query displays a Line Chart showing requests response duration per operation.
ABSBotRequests
| summarize DurationMs = avg(DurationMs)  by bin(TimeGenerated, 5m), OperationName
| render timechart
```



### Response Codes Line Chart  


Line Chart showing requests response status codes.  

```query
// Display a Line Chart of requests response status codes.
ABSBotRequests
| summarize Number_Of_Requests = count() by tostring(ResultCode), bin(TimeGenerated, 5m)
| render timechart
```



### Response Codes PieChart  


Pie Chart showing requests response status codes.  

```query
// Display a Pie Chart showing requests response status codes.
ABSBotRequests
| summarize count() by tostring(ResultCode)      
| render piechart
```



### Request Operations PieChart  


Pie Chart showing requests operations.  

```query
// Display a Pie Chart showing requests by operation name.
// This gives a perspective of the request operations percentage distribution in the selected time range.
ABSBotRequests
| summarize count() by tostring(OperationName)      
| render piechart
```

