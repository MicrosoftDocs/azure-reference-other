---
title: ST_DISTANCE (Azure Stream Analytics)
description: Returns the distance between two points in meters. If used with Polygons will return 0.
applies_to: 
  - "Azure"
ms.service: stream-analytics
ms.topic: reference
ms.date: 09/13/2019
---

# ST_DISTANCE  (Azure Stream Analytics)

Returns the geodesic distance between two points in meters. Cartesian distances require projection calculations and are not supported, but they can be implemented in user defined functions. If used with Polygons will return 0.  
  
 ## Syntax  
  
```SQL   
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
  
```SQL  
SELECT  
     ST_DISTANCE(input.carPosition, input.warehouse)  
FROM input  
  
```  
  
### Input Example  
  
|carPosition|warehouse|  
|-----------------|---------------|  
|{"type":"Point", "coordinates": [-5.0, -5.0]}|{"type":"Point", "coordinates": [0.0, 0.0]}|  
  
### Output Example  
 784028.74077501823  
  
## See Also  

* [GeoSpatial Functions](geospatial-functions.md)
* [CreateLineString](createlinestring.md)
* [CreatePoint](createpoint.md)
* [CreatePolygon](createpolygon.md)
* [ST_OVERLAPS](st-overlaps.md)
* [ST_INTERSECTS](st-intersects.md)
* [ST_WITHIN](st-within.md)
