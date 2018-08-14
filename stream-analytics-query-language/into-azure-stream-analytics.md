---
title: "INTO (Azure Stream Analytics) | Microsoft Docs"
description: "INTO explicitly specifies an output stream, and is always associated with an SELECT expression."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 4e5d157c-f886-4f04-8894-8c0acdcaf847
caps.latest.revision: 7
ms.workload: data-services
ms.date: 05/03/2016
ms.author: mamccrea
---
# INTO (Azure Stream Analytics)
  INTO explicitly specifies an output stream, and is always associated with an SELECT expression.  If not specified, the default output stream is “output”.  
  
 **Syntax**  
  
```  
[ INTO <output_stream> ]  
  
```  
  
## Arguments  
 **ouput_stream**  
  
 Specifies the name of an output stream.  
  
## Limitations and Restrictions  
 You cannot use SELECT … INTO in a WITH clause. For example, INTO clause can only be used in the out-most subquery.  
  
  
## Example  
  
```SQL  
WITH WAVehicle AS (  
    SELECT TollId, EntryTime AS VehicleEntryTime, LicensePlate, State, Make, Model, VehicleType,    VehicleWeight, Toll, Tag  
    FROM TollTagEntry TIMESTAMP BY EntryTime  
    WHERE State = "WA"
)  
  
SELECT * INTO WAVehicleArchive FROM WAVehicle;  
  
SELECT DateAdd(minute,-3,System.TimeStamp) AS WinStartTime, System.TimeStamp AS WinEndTime, COUNT(*) INTO WAVehicleCount FROM WAVehicle GROUP BY TumblingWindow(minute, 3)  
  
```  
  
  
