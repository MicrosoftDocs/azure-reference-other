---
title: "Windows (Azure Stream Analytics) | Microsoft Docs"
description: "Describes the Windows concept in Azure Stream Analytics."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.service: stream-analytics
ms.topic: reference
ms.assetid: aff805fa-3490-49a9-81b2-ddcaac4debaf
ms.workload: data-services
ms.date: 05/01/2019
ms.author: mamccrea
---

# Windows (Azure Stream Analytics)

Windowing provides a way to aggregate events over various time intervals depending on specific window definitions. There are four kinds of temporal windows to choose from: [Tumbling](tumbling-window-azure-stream-analytics.md), [Hopping](hopping-window-azure-stream-analytics.md), [Sliding](sliding-window-azure-stream-analytics.md), and [Session](session-window-azure-stream-analytics.md).

The **Windows()** function extends this concept to simultaneously compute results of multiple different window definitions. The **Windows()** function allows you to specify more than one window definition. The query logic is computed for each of these window definitions, and the result is a union of all window results.

Since the result of the **Windows()** function contains a combination of multiple windows, you need to distinguish between the different results. This is done by assigning an identity to each window which can be accessed using the system function **System.Window().Id**. **System.Windows()** returns a record with the Id as its field.

There are two ways to define Windows:

* Assign unique identities using the **Window()** function, **Window ( ID , window_definition )**, where ID is an identity of **window_definition** and is a unique **varchar(max)** value within the Windows construct.

* Without identities, in which case **System.Window().Id** results in null value.
  
 ## Syntax  
  
```SQL   
| Windows ( window_definition, … ) 
| Windows ( Window ( id , window_definition ), … ) 
 
window_definition = 
| HoppingWindow ( … 
| TumblingWindow ( … 
| SlidingWindow ( … 
| SessionWindow ( … 
| Hopping ( … 
| Tumbling ( … 
| Sliding ( … 
| Session ( …  
  
```  
  
> [!NOTE]  
>  The **Windows** constructs cannot be nested. Identities must either be given to all window definitions or given to none. 

There are shortened window definition names, like "Tumbling", which can be used in **Windows()** to avoid repetition of the word "window" like in `Windows(Window('MyWindow', TumblingWindow(…`. The shortened names can also be used outside of the Windows construct.

It is not an error to use **System.Window().Id** without the Windows construct, but its value will be null because no identity was given to the window.

If window definitions are specified using the **Window()** function, then all window definitions must use the **Window()** function and all IDs must be unique. Null is not allowed.
  
## System.Window() function

The **System.Window()** function can only be used in the **SELECT** clause of the **GROUP BY** statement to retrieve metadata about the grouping time window.

The function returns a value of type **Record** containing a single field **Id**, which holds the identity of the window the event belongs to.
  
## Examples  
  
Create a window with a 5 minute hop and create output every 10 minutes. The full output will be outputted at 60 minutes.

```SQL  
SELECT 
System.Window().Id, 
TollId, 
COUNT(*) 
FROM Input TIMESTAMP BY EntryTime 
GROUP BY 
TollId, 
Windows( 
            HoppingWindow(minute, 10, 5), 
            HoppingWindow(minute, 20, 5), 
            HoppingWindow(minute, 30, 5), 
            HoppingWindow(minute, 40, 5), 
            HoppingWindow(minute, 50, 5), 
            HoppingWindow(minute, 60, 5))  
  
```  
  
Create windows with a 1 minute hop and four different durations – 1 min, 15 min, 30 min and 60 min.

```SQL
SELECT 
        System.Window().Id, 
        TollId, 
        COUNT(*) 
FROM Input TIMESTAMP BY EntryTime 
GROUP BY 
        TollId, 
        Windows( 
            Window('1 min', TumblingWindow(minute, 1)), 
            Window('15 min', HoppingWindow(minute, 15, 1)), 
            Window('30 min', HoppingWindow(minute, 30, 1)), 
            Window('60 min', HoppingWindow(minute, 60, 1))) 
```

Create windows of different sizes and filter results based on the window duration specified in the Reference table.

```SQL
WITH HoppinWindowResults 
( 
    SELECT 
        System.Window().Id, 
        TollId, 
        COUNT(*) 
    FROM Input TIMESTAMP BY EntryTime 
    GROUP BY 
        TollId, 
        Windows( 
            Window('H10', Hopping(minute, 10, 5)), 
            Window('H20', Hopping(minute, 20, 5)), 
            Window('H30', Hopping(minute, 30, 5)), 
            Window('H40', Hopping(minute, 40, 5)), 
            Window('H50', Hopping(minute, 50, 5)), 
            Window('H60', Hopping(minute, 60, 5))) 
) 
 
SELECT HoppingWindowResults.* 
FROM HoppingWindowResults 
JOIN ReferenceTable ON  
    HoppingWindowResults.TollId = ReferenceTable.TollId 
    AND HoppingWindowResults.Id = ReferenceTable.windowId  

```