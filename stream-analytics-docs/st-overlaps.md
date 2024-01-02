---
title: ST_OVERLAPS (Azure Stream Analytics)
description: Returns 1 if a geography overlaps with another. If geographies do not overlap or one is within another, it will return 0.
applies_to: 
  - "Azure"

ms.service: stream-analytics
ms.topic: reference
ms.date: 02/01/2017
---
# ST_OVERLAPS (Azure Stream Analytics)
  Returns 1 if a geography overlaps with another. If geographies do not overlap or one is within another, it will return 0.  
  
 ## Syntax  
  
```SQL   
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
|{"type":"Polygon", "coordinates": [ [0.0, 0.0], [10.0, 0.0], [10.0, 10.0], [0.0, 10.0], [0.0, 0.0] ]}|{"type":"Polygon", "coordinates": [ [30.0, 30.0], [40.0, 30.0], [40.0, 40.0], [30.0, 40.0], [30.0, 30.0] ]}|  
|{"type":"Polygon", "coordinates": [ [0.0, 0.0], [20.0, 0.0], [20.0, 20.0], [0.0, 20.0], [0.0, 0.0] ]}|{"type":"Polygon", "coordinates": [ [10.0, 10.0], [40.0, 10.0], [40.0, 40.0], [40.0, 20.0], [40.0, 40.0] ]}|  
  
### Output Example  
 0  
  
 1  
  
## See Also  

* [GeoSpatial Functions](geospatial-functions.md)
* [CreateLineString](createlinestring.md)
* [CreatePoint](createpoint.md)
* [CreatePolygon](createpolygon.md)
* [ST_DISTANCE](st-distance.md)
* [ST_INTERSECTS](st-intersects.md)
* [ST_WITHIN](st-within.md)
  
