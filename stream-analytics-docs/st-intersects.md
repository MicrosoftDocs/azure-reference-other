---
title: ST_INTERSECTS
description: Returns 1 if a geography intersects with another. If geographies do not intersect it will return 0. 
applies_to: 
  - "Azure"

ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# ST_INTERSECTS
  Returns 1 if a geography intersects with another. If geographies do not intersect it will return 0.  
  
 ## Syntax  
  
```SQL   
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
  
```SQL  
SELECT  
     ST_INTERSECTS(input.pavedRoad, input.dirtRoad)  
FROM input  
  
```  
  
### Input Example  
  
|datacenterArea|stormArea|  
|--------------------|---------------|  
|{"type":"LineString", "coordinates": [ [-10.0, 0.0], [0.0, 0.0], [10.0, 0.0] ]}|{"type":"LineString", "coordinates": [ [0.0, 10.0], [0.0, 0.0], [0.0, -10.0] ]}|  
|{"type":"LineString", "coordinates": [ [-10.0, 0.0], [0.0, 0.0], [10.0, 0.0] ]}|{"type":"LineString", "coordinates": [ [-10.0, 10.0], [0.0, 10.0], [10.0, 10.0] ]}|  
  
### Output Example  
 1  
  
 0  
  
## See Also  

* [GeoSpatial Functions](geospatial-functions.md)
* [CreateLineString](createlinestring.md)
* [CreatePoint](createpoint.md)
* [CreatePolygon](createpolygon.md)
* [ST_DISTANCE](st-distance.md)
* [ST_OVERLAPS](st-overlaps.md)
* [ST_WITHIN](st-within.md)
  
