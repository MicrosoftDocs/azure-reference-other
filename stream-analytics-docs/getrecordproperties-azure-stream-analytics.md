---
title: "GetRecordProperties (Azure Stream Analytics)"
description: "Returns a dataset with record property names and values."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# GetRecordProperties (Azure Stream Analytics)
  Returns a dataset with record property names and values. The result of the GetRecordProperties function must be used with the [CROSS APPLY](apply-azure-stream-analytics.md) operator.  
  
 ## Syntax  
  
```SQL   
GetRecordProperties ( column_reference )  
```  
  
## Arguments  
 **Column_reference**  
  
 Is the column reference expression to be evaluated. Column must be of type Record  
  
## Return Types  
 Returns a dataset with PropertyName and PropertyValue columns.  
  
## Examples  
  
```SQL  
SELECT   
    recordProperty.PropertyName,  
    recordProperty.PropertyValue  
FROM input as event  
CROSS APPLY GetRecordProperties(event.recordField) AS recordProperty  
```  
  

