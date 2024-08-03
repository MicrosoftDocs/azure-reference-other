---
title: "WITH (Azure Stream Analytics)"
description: "Specifies a temporary named result set which can be referenced by a FROM clause in the query."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# WITH (Azure Stream Analytics)
  Specifies a temporary named result set which can be referenced by a FROM clause in the query. This is defined within the execution scope of a single SELECT statement.  
  
> [!NOTE]  
>  The WITH clause has a special use with respect to scaling out your queries. For more information, see [Scale Azure Stream Analytics jobs](/azure/stream-analytics/stream-analytics-scale-jobs)  
  
 ## Syntax  
  
```SQL   
WITH   
  
<result_set_name1> AS  
  ( SELECT_query_definition1 ),  
  
[<result_set_name2> AS  
  ( SELECT_query_definition2 )  
[...n]  ]  
  
```  
  
## Arguments  
 **result_set_name**  
  
This is the name of the temporary result-set which can be referenced by a FROM clause of a SELECT statement. This name must be different from the name of any other result_set_name defined within the scope of the query.   
  
  
 **SELECT_query_definition**  
  
 Specifies a SELECT statement whose result set populates the result_set_name.  
  
## Example  
  
```SQL  
WITH   
NormalReadings AS  
(  
  SELECT *  
  FROM Sensor  
  WHERE Reading < 100 AND Reading > 0  
),  
Averages AS  
(  
  SELECT SensorId, AVG(Reading) as AvgNormalReading  
  FROM NormalReadings  
  GROUP BY SensorId, TumblingWindow(minute, 1)  
),  
BadAverages AS  
(  
  SELECT *  
  FROM Averages  
  WHERE AvgNormalReadings < 10  
)  
  
SELECT * INTO outputAlerts FROM BadAverages  
SELECT * INTO outputLog FROM NormalReadings  
  
  
```  
  
  
