---
title: "INTO (Azure Stream Analytics) | Microsoft Docs"
description: "INTO explicitly specifies an output stream, and is always associated with an SELECT expression or specifies the shards count in an upstream step."
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

## INTO (Output Stream)
INTO explicitly specifies an output stream, and is always associated with an SELECT expression.  If not specified, the default output stream is “output”.
  
 ## Syntax  
  
```SQL   
[ INTO <output_stream> ]  

```  
  
## Arguments  
 **output_stream**  
  
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
  
## INTO (Shard Count)
INTO explicitly specifies the number of shards in an input step when specifying a partitioning scheme (PARTITION BY). If partition count is not specified, the number of shards is carried over if the PARTITION BY is the same or two otherwise.

INTO is a hint to the system, and may be ignored should the system determine the explicit specification is not beneficial.

## Syntax  
  
```SQL  
[ INTO <shard_count> ]  

```  

## Arguments  
 **shard_count**  
  
 Specifies the number of shards in the upstream step.  
  
## Limitations and Restrictions  
 Shard count must be greater than 1. When joining several streams, the partition count of all inputs must be the same.
  
## Example  
  
```SQL  
WITH Step1 AS (
    SELECT * 
    FROM input 
    PARTITION BY DeviceId
    INTO 10
)

SELECT * INTO [output] FROM Step1 PARTITION BY DeviceId
  
```  

