---
title: "ST_DISTANCE | Microsoft Docs"
ms.custom: ""
ms.date: "2017-02-01"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 80550bf3-96a8-47a2-8287-181e1992008c
caps.latest.revision: 2
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# ST_DISTANCE
  Returns the distance between two points in meters. If used with Polygons will return 0.  
  
 **Syntax**  
  
```  
ST_DISTANCE ( pointA, pointB )  
```  
  
## Argument  
 **PointA**  
  
 The point to measure distance from.  
  
 **PointB**  
  
 The point to measure distance to.  
  
## Return Type  
 Returns the distance between two points in meters.  
  
## Example  
  
```  
SELECT  
     ST_DISTANCE(input.car1Position, input.car2Position)  
FROM input  
  
```  
  
### Input Example  
  
|carPosition|warehouse|  
|-----------------|---------------|  
|{“type”:”Point”, “coordinates”: [-5.0, -5.0]}|{“type”:”Point”, “coordinates”: [0.0, 0.0]}|  
  
### Output Example  
 784028.74077501823  
  
## See Also  

  