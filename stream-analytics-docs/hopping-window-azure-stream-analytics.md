---
title: "Hopping Window"
description: "Describes the Hopping window concept in Azure Stream Analytics."
applies_to: 
  - "Azure"

ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Hopping Window
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

  Unlike [tumbling windows](tumbling-window-azure-stream-analytics.md), hopping windows model scheduled overlapping windows. A hopping window specification consist of three parameters: the *timeunit*, the *windowsize* (how long each window lasts) and the *hopsize* (by how much each window moves forward relative to the previous one). Additionally, *offsetsize* may be used as an optional fourth parameter.  Note that a tumbling window is simply a hopping window whose ‘hop’ is equal to its ‘size’.  
  
 The following illustration shows a stream with a series of events. Each box represents a hopping window and the events that are counted as part of that window, assuming that the ‘hop’ is 5, and the ‘size’ is 10.  
  
 ![Stream Analytics hopping window diagram](media/hopping-window-azure-stream-analytics/streamanalytics-hoppingwindow.png "Stream Analytics hopping window diagram")  
  
 ## Syntax  
  
```SQL
{HOPPINGWINDOW | HOPPING} ( timeunit  , windowsize , hopsize, [offsetsize] )
{HOPPINGWINDOW | HOPPING} ( Duration( timeunit  , windowsize ) , Hop (timeunit  , windowsize ), [Offset(timeunit  , offsetsize)])  
  
```
  
> [!NOTE]  
>  The Hopping Window can be used in the above two ways. If the windowsize and the hopsize has the same timeunit, you can use it without the Duration and Hop functions. The Duration function can also be used with other types of windows to specify the window size.  
  
## Arguments  
 **timeunit**  
  
 Is the unit of time for the *windowsize* or the *hopsize*. The following table lists all valid *timeunit* arguments.  
  
|Timeunit|Abbreviations|  
|--------------|-------------------|  
|day|dd, d|  
|hour|hh|  
|minute|mi, n|  
|second|ss, s|  
|millisecond|ms|  
|microsecond|mcs|  
  
 **windowsize**  
  
 A big integer which describes the size of the window. The windowsize is static and cannot be changed dynamically at runtime.  
  
 The maximum size of the window in all cases is 7 days.  
  
 **hopsize**  
  
 A big integer which describes the size of the Hop. 
  
 **offsetsize**  
  
 By default, hopping windows are inclusive in the end of the window and exclusive in the beginning – for example 12:05 PM – 1:05 PM window will include events that happened exactly at 1:05 PM, but will not include events that happened at 12:05:PM (these event will be part of 12:00 PM – 01:00 PM window).    
 The Offset parameter can be used to change behavior and include the events in the beginning of the window and exclude the ones that happened in the end.  
  
  
## Examples  
  
```SQL  
SELECT System.Timestamp() AS WindowEnd, TollId, COUNT(*)  
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, HoppingWindow(Duration(hour, 1), Hop(minute, 5), Offset(millisecond, -1))  
  
```  
 
 ## Time consideration
Every window operation outputs event at the end of the window (in the case of hopping windows, this happens at every hop size). The windows of Azure Stream Analytics are opened at the window start time and closed at the window end time. For example, if you have a 5 minute window from 12:00 AM to 12:05 AM all events with timestamp greater than 12:00 AM and up to timestamp 12:05 AM inclusive will be included within this window. The output of the window will be a single event based on the aggregate function used with a timestamp equal to the window end time. The timestamp of the output event of the window can be projected in the SELECT statement using the System.Timestamp() property using an alias.
  
