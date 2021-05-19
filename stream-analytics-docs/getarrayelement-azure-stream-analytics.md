---
title: GetArrayElement (Azure Stream Analytics)
description: Returns the array element at the specified index. Useful for parsing arrays and nested objects in JSON and AVRO data.
applies_to: 
  - "Azure"

ms.service: stream-analytics
ms.topic: reference
ms.date: 05/17/2018
---

# GetArrayElement (Azure Stream Analytics)
Returns the array element at the specified index. This function is useful for parsing arrays and nested objects in JSON and AVRO formatted input event data. For more examples, see [Parsing JSON and AVRO data](/azure/stream-analytics/stream-analytics-parsing-json). If you need to return all nested elements in an array, use [GetArrayElements](getarrayelements-azure-stream-analytics.md) instead.
  
 ## Syntax  
  
```sql   
GetArrayElement ( array_expression, bigint_expression )  
```  
  
## Arguments  
 **array_expression**  
  
 Is the array expression to be evaluated as a source array. array_expression can be a column of type Array or result of another function call.  
  
 **bigint_expression**  
  
 Is the bigint expression to be evaluated as array index. The ordinal position in the array of elements, starting at 0.
  
### Return Types  
 Return type is determined by the array element type and can be any of the [supported types.](data-types-azure-stream-analytics.md)  
  
### Examples  

#### Sample data

```json
[
{
    "DeviceId" : "123",
    "SensorReadings" :
    {
        "Temperature" : 80,
        "Humidity" : 70,
        "CustomSensor": [1,1,0]
    }
},
{
    "DeviceId" : "631",
    "SensorReadings" :
    {
        "Temperature" : 81,
        "Humidity" : 69,
        "CustomSensor": [0,1,0]
    }
}
]
```

The sample dataset above is an array of two records. When used as [local input](/azure/stream-analytics/visual-studio-code-local-run) in a JSON file, the top-level array is interpreted for the generation of rows/events by Azure Stream Analytics. There is no need to take it into consideration in the query syntax.

At the individual record level, there are two properties with different [types](data-types-azure-stream-analytics.md). `DeviceId` is of type **nvarchar(max)**, `SensorReadings` is of type **record** (object). [GetType](gettype-azure-stream-analytics.md) can be used to determine the type when necessary.

`SensorReadings` has three properties: two are of type **bigint**: `Temperature` and `Humidity`, and `CustomSensor` is of type **array** (of **bigint**). If this array was more complex (itself containing records or arrays), a combination of [GetArrayElements](getarrayelements-azure-stream-analytics.md) (plural) and [GetRecordPropertyValue](getrecordpropertyvalue-azure-stream-analytics.md) could be used.

#### Queries

This query returns fields at the root of the record (`DeviceId`), nested fields using the [dot notation](/azure/stream-analytics/stream-analytics-parsing-json#access-nested-fields-in-known-schema) (`Temperature`,`Humidity`), including an **array** (`CustomSensor`), and finally, the first and second elements of that array via **GetArrayElement** (index 0 and 1):

```sql  
SELECT   
    i.DeviceId,
    i.SensorReadings.Temperature,
    i.SensorReadings.Humidity,
    i.SensorReadings.CustomSensor as CustomSensorArray,
    GetArrayElement(i.SensorReadings.CustomSensor,0) AS FirstCustomSensorValue,
    GetArrayElement(i.SensorReadings.CustomSensor,1) AS SecondCustomSensorValue
FROM input i
```

Returns the following output:

|DeviceId|Temperature|Humidity|CustomSensorArray|FirstCustomSensorValue|SecondCustomSensorValue|
|---|---|---|---|---|---|
|631|81|69|0,1,0|0|1|
|123|80|70|1,1,0|1|1|

Use [CROSS APPLY](apply-azure-stream-analytics.md) to unfold the array:

```sql  
SELECT   
    i.DeviceId,
    CustomerSensorValue.ArrayValue AS CustomerSensorValue
FROM input AS i
CROSS APPLY GetArrayElements(i.SensorReadings.CustomSensor) AS CustomerSensorValue
``` 

Returns the following output:

|DeviceId|CustomerSensorValue|
|---|---|
|631|0|
|631|1|
|631|0|
|123|0|
|123|1|
|123|1|

From there, you can easily aggregate the content if necessary:

```sql
SELECT   
    i.DeviceId,
    SUM(CustomerSensorValue.ArrayValue) AS CustomerSensorTotal 
FROM input AS i
CROSS APPLY GetArrayElements(i.SensorReadings.CustomSensor) AS CustomerSensorValue 
GROUP BY i.DeviceId, TumblingWindow(minute, 1)
```

|DeviceId|CustomerSensorTotal|
|---|---|
|123|2|
|631|1|

 ## See also 
- [GetArrayElements](getarrayelements-azure-stream-analytics.md)
- [CROSS APPLY](apply-azure-stream-analytics.md)
- [Parsing JSON and AVRO](/azure/stream-analytics/stream-analytics-parsing-json)
