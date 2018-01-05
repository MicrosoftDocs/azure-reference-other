---
title: "CreatePoint | Microsoft Docs"
ms.custom: ""
ms.date: "2017-02-01"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b49facae-be27-4e6b-a2e8-299d6f9c41e4
caps.latest.revision: 4
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# CreatePoint
  Returns a GeoJSON Point record. The result of a CreatePoint can be used as input to other Geospatial functions.  
  
 **Syntax**  
  
```  
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
  
```  
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

  
  