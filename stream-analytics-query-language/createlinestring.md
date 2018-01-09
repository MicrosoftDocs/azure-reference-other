---
title: "CreateLineString | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c99c9464-d052-4aef-a176-6ee53c6dcab9
caps.latest.revision: 3
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# CreateLineString
  Returns a GeoJSON LineString record. The result of a CreateLineString can be used as input to other Geospatial functions.  
  
 Be aware that when declaring LineStrings:  
  
-   A LineStrings must have at least 2 points.  
  
-   The structure cannot overlap itself over an interval of two or more consecutive points.  
  
 **Syntax**  
  
```  
CreateLineString (points)  
```  
  
## Argument  
 **Points**  
  
 A list of GeoJSON record points.  
  
## Return Type  
 Returns a GeoJSON LineString record with LineString as type and an arrays of points as coordinates.  
  
## Example  
  
```SQL  
SELECT  
     CreateLineString(CreatePoint(input.latitude, input.longitude), CreatePoint(10.0, 10.0), CreatePoint(10.5, 10.5))  
FROM input  
  
```  
  
### Input Example  
  
|latitude|longitude|  
|--------------|---------------|  
|3.0|-10.2|  
|-87.33|20.2321|  
  
### Output Example  
 {"type" : "LineString", "coordinates" : [ [-10.2, 3.0], [10.0, 10.0], [10.5, 10.5] ]}

 {"type" : "LineString", "coordinates" : [ [20.2321, -87.33], [10.0, 10.0], [10.5, 10.5] ]}

  
## See Also  

  