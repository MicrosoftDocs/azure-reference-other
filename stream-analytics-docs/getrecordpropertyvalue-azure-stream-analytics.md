---
title: "GetRecordPropertyValue (Azure Stream Analytics)"
description: "Returns the record value associated with the specified property. "
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# GetRecordPropertyValue (Azure Stream Analytics)
  Returns the record value associated with the specified property.  
  
 ## Syntax  
  
```SQL   
GetRecordPropertyValue ( record_expression, string_expression )  
```  
  
## Arguments  
 **record_expression**  
  
 Is the record expression to be evaluated as a source record. record_expression can be a column of type Record or result of another function call.  
  
 **string_expression**  
  
 Is the string expression to be evaluated as a record property name.  
  
## Return Types  
 Return type is determined by the record property type and can be any of the [supported types](data-types-azure-stream-analytics.md).  
  
## Examples  
 In this code example, “thresholds” is a reference data name defined on the inputs tab.  
  
```SQL  
SELECT   
    input.DeviceID,  
    thresholds.SensorName  
FROM input  
JOIN thresholds   
ON  
    input.DeviceId = thresholds.DeviceId  
WHERE  
    GetRecordPropertyValue(input.SensorReadings, thresholds.SensorName) > thresholds.Value  
```  
  
 Note that you can use dot notation to access record property fields.  
  
```SQL  
SELECT   
    recordColumn.NestedFieldName1.NestedFieldName2  
FROM input  
  
```  
  
## See also
- [Parsing JSON and AVRO data](/azure/stream-analytics/stream-analytics-parsing-json)
