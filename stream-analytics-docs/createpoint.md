---
title: CreatePoint
description: Returns a GeoJSON Point record. The result of a CreatePoint can be used as input to other Geospatial functions.
applies_to: 
  - "Azure"

ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# CreatePoint
  Returns a GeoJSON Point record. The result of a CreatePoint can be used as input to other Geospatial functions.  
  
 ## Syntax  
  
```SQL   
CreatePoint (latitude, longitude)  
```  
  
## Argument  
 **Latitude**  
  
 Is the latitude of a geographic point, value must be float.  
  
 **Longitude**  
  
 Is the longitude of a geographic point, value must be float.  
  
## Return Type  
 Returns a GeoJSON point record with Point as type and an array with latitude and longitude as coordinates.  
  
## Example  
  
```SQL  
 SELECT  
     CreatePoint(input.latitude, input.longitude)  
FROM input  
  
```  
  
### Input Example  
  
|latitude|longitude|  
|--------------|---------------|  
|3.0|-10.2|  
|-87.33|20.2321|  
  
### Output Example  
 {"type" : "Point", "coordinates" : [-10.2, 3.0]}  
  
 {"type" : "Point", "coordinates" : [20.2321, -87.33]}  
  
## See Also  

* [GeoSpatial Functions](geospatial-functions.md)
* [CreateLineString](createlinestring.md)
* [CreatePolygon](createpolygon.md)
* [ST_DISTANCE](st-distance.md)
* [ST_OVERLAPS](st-overlaps.md)
* [ST_INTERSECTS](st-intersects.md)
* [ST_WITHIN](st-within.md)
  
