---
title: ST_WITHIN (Azure Stream Analytics)
description: Returns 1 if a geography is within another, if not it will return 0.
applies_to: 
  - "Azure"

ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# ST_WITHIN (Azure Stream Analytics)
  Returns 1 if a geography is within another, if not it will return 0.  
  
 ## Syntax  
  
```SQL   
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
|{"type":"Point", "coordinates": [76.6, 10.1]}|{"type":"Polygon", "coordinates": [[ [0.0, 0.0], [10.0, 0.0], [10.0, 10.0], [0.0, 10.0], [0.0, 0.0] ]]}|  
|{"type":"Point", "coordinates": [15.0, 15.0]}|{"type":"Polygon", "coordinates": [[ [10.0, 10.0], [20.0, 10.0], [20.0, 20.0], [10.0, 20.0], [10.0, 10.0] ]]}|  
  
### Output Example  
 0  
  
 1  
  
## See Also  

* [GeoSpatial Functions](geospatial-functions.md)
* [CreateLineString](createlinestring.md)
* [CreatePoint](createpoint.md)
* [CreatePolygon](createpolygon.md)
* [ST_DISTANCE](st-distance.md)
* [ST_OVERLAPS](st-overlaps.md)
* [ST_INTERSECTS](st-intersects.md)
