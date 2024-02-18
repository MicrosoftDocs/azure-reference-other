---
title: Example log table queries for ACSCallRecordingSummary
description:  Example queries for ACSCallRecordingSummary log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallRecordingSummary table


### Call Recording duration histogram  


Produces a histogram of call recording durations in seconds.  

```query
ACSCallRecordingSummary
| distinct RecordingId, RecordingLength
// Count call duration bins (60 second intervals)
| summarize duration_counts=count() by bin(RecordingLength, 6000)
| order by RecordingLength asc
| render columnchart with (xcolumn = RecordingLength, title="Recording duration histogram")
```



### Call Recording duration percentiles  


Calculates the average call recording duration in seconds, as well as the 50%, 90%, and 99% call duration percentiles.  

```query
ACSCallRecordingSummary
// Get the distinct combinations of RecordingId, RecordingLength
| distinct RecordingId, RecordingLength
// Calculate average and percentiles (50%, 90%, and 99%) of call durations (in seconds)
| summarize avg(RecordingLength), percentiles(RecordingLength, 50, 90, 99)
```



### Call Recording's end reason ratio  


Produces a pie chart of the proportion of call recording's end reason.  

```query
ACSCallRecordingSummary
// Count distinct calls (dcount(CorrelationId)) per call type
| summarize call_types=dcount(RecordingId) by RecordingEndReason
| render piechart title="Recording End Reason Ratio"
```



### Daily Call Recordings  


Produces a histogram of recordings made per day in the last week.  

```query
ACSCallRecordingSummary
// To filter out recordings made over a week ago, uncomment the next line
// | where TimeGenerated > ago(7d)
// Get the distinct combinations of RecordingId and CallStartTime
| distinct RecordingId, TimeGenerated
// Adds a new column with the call start day
| extend day = floor(TimeGenerated, 1d)
// Count the number of calls per day
| summarize event_count=count() by day
| sort by day asc
| render columnchart title="Number of recordings per day"
```



### Hourly Call Recordings  


Produces a histogram of recordings made per hour in the last day.  

```query
    ACSCallRecordingSummary
    // To filter out recordings made over a day ago, uncomment the next line
    | where TimeGenerated > ago(1d)
    // Get the distinct combinations of RecordingId and TimeGenerated
    | distinct RecordingId, TimeGenerated
    // Adds a new column with the call start hour
    | extend hour = floor(TimeGenerated, 1h)
    // Count the number of calls per hour
    | summarize event_count=count() by hour
    | sort by hour asc
    | render columnchart title="Number of recordings per hour in last day"
```



### Call Recording's mode ratio  


Produces a pie chart of the proportion of recording modes (content/format types).  

```query
ACSCallRecordingSummary
| summarize count() by ContentType, FormatType
| extend ContentFormat = strcat(ContentType, "/", FormatType)
| project ContentFormat, count_
| render piechart title="Recording by mode (content/format types)"
```

