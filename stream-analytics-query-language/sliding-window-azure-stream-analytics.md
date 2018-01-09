---
title: "Sliding Window (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-02-23"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cd42711f-1064-41d9-8165-58d5da25008f
caps.latest.revision: 13
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# Sliding Window (Azure Stream Analytics)
  When using a sliding window, the system is asked to logically consider all possible windows of a given length. As the number of such windows would be infinite, Azure Stream Analytics instead outputs events only for those points in time when the content of the window actually changes, in other words when an event entered or exits the window.  
  
 For instance, consider an event stream consisting of the following events:  
  
|Timestamp|Name|  
|---------------|----------|  
|34|A|  
|38|B|  
|42|C|  
  
 Using sliding window of length 5 will produce events for windows ending at the following times:  
  
-   **34** - because A entered the window  
  
-   **38** - because B entered the window  
  
-   **39** - because A exited the window  
  
-   **42** - because C entered the window  
  
-   **43** - because B exited the window  
  
 No event is produced at time 47 (when C exits the window), since aggregates cannot be computed over empty windows.  
  
 **Syntax**  
  
```  
SLIDINGWINDOW ( timeunit  , windowsize )   
SLIDINGWINDOW ( Duration( timeunit  , windowsize ) )  
  
```  
  
> [!NOTE]  
>  The Sliding Window can be used in the above two ways. To allow consistency with the Hopping Window, the Duration function can also be used with all types of windows to specify the window size.  
  
## Arguments  
 **timeunit**  
  
 Is the unit of time for the windowsize. The following table lists all valid timeunit arguments.  
  
|Timeunit|Abbreviations|  
|--------------|-------------------|  
|day|dd, d|  
|hour|hh|  
|minute|mi, n|  
|second|ss, s|  
|millisecond|ms|  
|microsecond|mcs|  
  
 **windowsize**  
  
 A big integer which describes the size of the window.  
  
 The maximum size of the window in all cases is 7 days.  
  
## Examples  
 This example finds all toll booths which have served more than 3 vehicles in the last 5 minutes:  
  
```SQL  
SELECT DateAdd(minute,-5,System.TimeStamp) AS WinStartTime, System.TimeStamp AS WinEndTime, TollId, COUNT(*)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, SlidingWindow(minute, 5)  
HAVING COUNT(*) > 3  
  
```  
  
  