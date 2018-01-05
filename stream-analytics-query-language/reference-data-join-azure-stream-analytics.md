---
title: "Reference Data JOIN (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: ed2104b6-1afd-41e2-a3e4-5b817d766686
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# Reference Data JOIN (Azure Stream Analytics)
  In a usual scenario, we use an event processing engine to compute streaming data with very low latency. In many cases users need to correlate persisted historical data or a slow changing dataset (aka. reference data) with the real-time event stream to make smarter decisions about the system. For example, join my event stream to a static dataset which maps IP Addresses to locations. This is the only JOIN supported in Stream Analytics where a temporal bound is not necessary.  
  
## Example  
 If a commercial vehicle is registered with the Toll Company, they can pass through the toll booth without being stopped for inspection. We will use a commercial vehicle registration lookup table to identify all commercial vehicles with expired registration.  
  
```  
SELECT I1.EntryTime, I1.LicensePlate, I1.TollId, R.RegistrationId  
FROM Input1 I1 TIMESTAMP BY EntryTime  
JOIN Registration R  
ON I1.LicensePlate = R.LicensePlate  
WHERE R.Expired = ‘1’  
  
```  
  
> [!NOTE]  
>  Using Reference Data JOIN requires that an input source for Reference Data is defined.  
  
  