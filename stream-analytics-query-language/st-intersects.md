---
title: "ST_INTERSECTS | Microsoft Docs"
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
ms.assetid: 2ba05fc9-aef9-4f0f-92f8-10d8dbc166a7
caps.latest.revision: 2
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# ST_INTERSECTS
  Returns 1 if a geography intersects with another. If geographies do not intersect it will return 0.  
  
 **Syntax**  
  
```  
ST_INTERSECTS (lineStringA, lineStringB)  
```  
  
## Argument  
 **LineStringA**  
  
 The LineString that could intersect with LineStringB.  
  
 **LineStringB**  
  
 The LineString that could intersect with LineStringA.  
  
## Return Type  
 Returns 1 if a LineString intersects with another LineString, if not it will return 0.  
  
## Example  
  
```  
SELECT  
     ST_INTERSECTS(input.pavedRoad, input.dirtRoad)  
FROM input  
  
```  
  
### Input Example  
  
|datacenterArea|stormArea|  
|--------------------|---------------|  
|{“type”:”LineString”, “coordinates”: [ [-10.0, 0.0], [0.0, 0.0], [10.0, 0.0] ]}|{“type”:”LineString”, “coordinates”: [ [0.0, 10.0], [0.0, 0.0], [0.0, -10.0] ]}|  
|{“type”:”LineString”, “coordinates”: [ [-10.0, 0.0], [0.0, 0.0], [10.0, 0.0] ]}|{“type”:”LineString”, “coordinates”: [ [-10.0, 10.0], [0.0, 10.0], [10.0, 10.0] ]}|  
  
### Output Example  
 1  
  
 0  
  
## See Also  

  
  