---
title: "ST_OVERLAPS | Microsoft Docs"
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
ms.assetid: d34676f9-ab12-4d2d-9a2e-5ba411ca1ec9
caps.latest.revision: 2
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# ST_OVERLAPS
  Returns 1 if a geography overlaps with another. If geographies do not overlap or one is within another, it will return 0.  
  
 **Syntax**  
  
```  
ST_OVERLAPS (polygonA, polygonB)  
```  
  
## Argument  
 **PolygonA**  
  
 The polygon that could overlap with polygonB.  
  
 **PolygonB**  
  
 The polygon that could overlap with polygonA.  
  
## Return Type  
 Returns 1 if a polygon overlaps with another polygon, if not it will return 0.  
  
## Example  
  
```SQL  
SELECT  
     ST_OVERLAPS(input.datacenterArea, input.stormArea)  
FROM input  
  
```  
  
### Input Example  
  
|datacenterArea|stormArea|  
|--------------------|---------------|  
|{“type”:”Polygon”, “coordinates”: [ [0.0, 0.0], [10.0, 0.0], [10.0, 10.0], [0.0, 10.0], [0.0, 0.0] ]}|{“type”:”Polygon”, “coordinates”: [ [30.0, 30.0], [40.0, 30.0], [40.0, 40.0], [30.0, 40.0], [30.0, 30.0] ]}|  
|{“type”:”Polygon”, “coordinates”: [ [0.0, 0.0], [20.0, 0.0], [20.0, 20.0], [0.0, 20.0], [0.0, 0.0] ]}|{“type”:”Polygon”, “coordinates”: [ [10.0, 10.0], [40.0, 10.0], [40.0, 40.0], [40.0, 20.0], [40.0, 40.0] ]}|  
  
### Output Example  
 0  
  
 1  
  
## See Also  

  