---
title: "CreatePolygon | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: dea81560-3db1-49d9-bf56-736d81948944
caps.latest.revision: 4
ms.workload: data-services
ms.date: 03/22/2017
ms.author: sngun
---
# CreatePolygon
  Returns a GeoJSON Polygon record. The result of a CreatePolygon can be used as input to other Geospatial functions. The order of points must follow right-hand ring orientation, an easy way to check if the polygon orientation is correct is to imagine yourself walking from one point to the other in order of declaration, the inside of the polygon needs to be on your left side all the time.  
  
 Be aware that when declaring polygons:  
  
-   A polygon with left-hand ring orientation will generate a geography that encompass the entire globe minus the polygon you declared.  
  
-   Polygons cannot have holes.  
  
-   Polygons cannot have less than 3 points.  
  
-   First and last points declared must be equal to close the loop  
  
 **Syntax**  
  
```  
CreatePolygon (points)  
```  
  
## Argument  
 **Points**  
  
 A list of GeoJSON record points.  
  
## Return Type  
 Returns a GeoJSON polygon record with Polygon as type and an array of points as coordinates.  
  
## Example  
  
```SQL  
 SELECT  
     CreatePolygon(CreatePoint(input.latitude, input.longitude), CreatePoint(10.0, 10.0), CreatePoint(10.5, 10.5), CreatePoint(input.latitude, input.longitude))  
FROM input  
  
```  
  
### Input Example  
  
|latitude|longitude|  
|--------------|---------------|  
|3.0|-10.2|  
|-87.33|20.2321|  
  
### Output Example  
 {"type" : "Polygon", "coordinates" : [[ [-10.2, 3.0], [10.0, 10.0], [10.5, 10.5], [-10.2, 3.0] ]]}
 
 {"type" : "Polygon", "coordinates" : [[ [20.2321, -87.33], [10.0, 10.0], [10.5, 10.5], [20.2321, -87.33] ]]}

  
## See Also  

  
  