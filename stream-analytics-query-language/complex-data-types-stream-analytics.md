---
title: "Complex Data Types (Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-05-24"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 8f092502-b698-4576-b271-d43c1f88accc
caps.latest.revision: 10
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# Complex Data Types (Stream Analytics)
  Azure Stream Analytics supports processing events in CSV, JSON and Avro data formats.  
Both JSON and Avro may contain complex types such as nested objects (records) or arrays. Scenarios may contain  complex data types that jobs must run against. Generally they are categorized as Array data types and Record data types.  
  
## Array data types  
 Array data types are an ordered collection of values. Some typical operations on array values are detailed below. Note that these examples assume the  input events have “arrayField” property of array type.  
  
## Examples  
 Select array element at a specified index (selecting the first array element):  
  
```SQL 
SELECT   
    GetArrayElement(arrayField, 0) AS firstElement  
FROM input  
```  
  
 Select array length:  
  
```SQL  
SELECT   
    GetArrayLength(arrayField) AS arrayLength  
FROM input  
```  
  
 Select all array element as individual events ( the [APPLY &#40;Azure Stream Analytics&#41;](apply-azure-stream-analytics.md) operator together with the [GetArrayElements &#40;Azure Stream Analytics&#41;](getarrayelements-azure-stream-analytics.md) built-in function extract all array elements as individual events):  
  
```SQL  
SELECT   
    arrayElement.ArrayIndex,  
    arrayElement.ArrayValue  
FROM input as event  
CROSS APPLY GetArrayElements(event.arrayField) AS arrayElement  
```  
  
## Record data types  
 Record data types are used to represent JSON and Avro arrays when corresponding formats are used in the input data streams. . All examples assume a sample sensor which is reading input events in JSON format. Here is example of a single event:  
  
```json  
{  
    "DeviceId" : "12345",  
    "Location" : {"Lat": 47, "Long": 122 }  
  
    "SensorReadings" :  
    {  
        "Temperature" : 80,  
        "Humidity" : 70,  
        "CustomSensor01" : 5,  
        "CustomSensor02" : 99  
    }  
}  
```  
  
## Examples  
 Utilize dot notation to access nested fields. For example, this query selects the reported lat/long coordinates of the device:  
  
```SQL  
SELECT  
    DeviceID,  
    Location.Latitude,  
    Location.Longitude  
FROM input  
```  
  
 Use the [GetRecordPropertyValue &#40;Azure Stream Analytics&#41;](getrecordpropertyvalue-azure-stream-analytics.md) function if the property name is unknown. For example, imagine a  sample data stream needs to be joined with reference data containing thresholds for each device sensor:  
  
```SQL  
SELECT  
    input.DeviceID,  
    thresholds.SensorName  
FROM input  
JOIN thresholds  
ON  
    input.DeviceId = thresholds.DeviceId  
WHERE  
    GetRecordPropertyValue(input.SensorReading, thresholds.SensorName) > thresholds.Value  
```  
  
 To convert record fields into separate events use the [APPLY &#40;Azure Stream Analytics&#41;](apply-azure-stream-analytics.md) operator together with the [GetRecordProperties &#40;Azure Stream Analytics&#41;](getrecordproperties-azure-stream-analytics.md) function. For example, to convert a sample stream into a stream of events with individual sensor readings, this query could be used:  
  
```SQL  
SELECT   
    event.DeviceID,  
    sensorReading.PropertyName,  
    sensorReading.PropertyValue  
FROM input as event  
CROSS APPLY GetRecordProperties(event.SensorReadings) AS sensorReading  
```  
  
 SELECT may also utilize '*' to access all the properties of a nested record. Consider the following query:  
  
```SQL  
SELECT input.SensorReadings.*  
FROM input  
```  
  
 This would result in the following output:  
  
```json  
{  
    "Temperature" : 80,  
    "Humidity" : 70,  
    "CustomSensor01" : 5,  
    "CustomSensor022" : 99  
}  
```  
  
## See Also  
 [Data Types &#40;Azure Stream Analytics&#41;](data-types-azure-stream-analytics.md)  
  
  