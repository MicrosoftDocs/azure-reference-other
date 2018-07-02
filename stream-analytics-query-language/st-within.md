---
title: ST_WITHIN (Azure Stream Analytics) | Microsoft Docs
description: Returns 1 if a geography is within another, if not it will return 0.
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 05edb3f8-64a6-44cb-8e43-f0a47222f2aa
caps.latest.revision: 2
ms.workload: data-services
ms.date: 02/01/2017
---
# ST_WITHIN (Azure Stream Analytics)
  Returns 1 if a geography is within another, if not it will return 0.  
  
 **Syntax**  
  
```  
ST_WITHIN (geography, polygon)  
```  
  
## Argument  
 **Geography**  
  
 The geography that could be inside the polygon. Can be either a point or a polygon.  
  
 **Polygon**  
  
 The polygon that could contain the geography.  
  
## Return Type  
 Returns 1 if either a point or polygon is within another polygon, if not it will return 0.  
  
## Example  
  
```SQL  
SELECT  
     ST_WITHIN(input.deliveryDestination, input.warehouse)  
FROM input  
  
```  
  
### Input Example  
  
|deliveryDestination|warehouse|  
|-------------------------|---------------|  
|{“type”:”Point”, “coordinates”: [76.6, 10.1]}|{“type”:”Polygon”, “coordinates”: [[ [0.0, 0.0], [10.0, 0.0], [10.0, 10.0], [0.0, 10.0], [0.0, 0.0] ]]}|  
|{“type”:”Point”, “coordinates”: [15.0, 15.0]}|{“type”:”Polygon”, “coordinates”: [[ [10.0, 10.0], [20.0, 10.0], [20.0, 20.0], [10.0, 20.0], [10.0, 10.0] ]]}|  
  
### Output Example  
 0  
  
 1  
  
## See Also  
