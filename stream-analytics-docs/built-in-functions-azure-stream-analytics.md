---
title: "Built-in Functions (Azure Stream Analytics) | Microsoft Docs"
description: "Lists the built-in functions supported by Stream Analytics Query Language"
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 975c1684-866c-4e9d-adc3-5f5d97227c8b
caps.latest.revision: 15
ms.workload: data-services
ms.date: 06/07/2019
ms.author: mamccrea
---

# Built-in Functions (Azure Stream Analytics)

Azure Stream Analytics provides some built-in functions. The categories of built-in functions are:  
  
## Types of Functions  
  
|Function Category|Description|  
|-----------------------|-----------------|  
|[Aggregate Functions](aggregate-functions-azure-stream-analytics.md)|Operate on a collection of values but return a single, summarizing value.|  
|[Analytic Functions](analytic-functions-azure-stream-analytics.md)|Return a value based on defined constraints.|  
|[Array Functions](array-functions-stream-analytics.md)|Returns information from an array.|
|[GeoSpatial Functions](geospatial-functions.md)|Perform specialized GeoSpatial functions.|  
|[Input Metadata Functions](input-metadata-functions.md)|Query the metadata of property in the data input.|
|[Record Functions](record-functions-azure-stream-analytics.md)|Returns record properties or values.|
|[Windowing Functions](windowing-azure-stream-analytics.md)|Perform operations on events within a time window.| 
|[Scalar Functions](built-in-functions-azure-stream-analytics.md#BKMK_ScalarFunctions)|Operate on a single value and then return a single value. Scalar functions can be used wherever an expression is valid.|  
  
##  <a name="BKMK_ScalarFunctions"></a> Scalar Functions  
 A scalar function operates on a single value and then return a single value. Scalar functions can be used wherever an expression is valid.  
  
 The categories of scalar functions are:  
  
|Function Category|Description|  
|-----------------------|-----------------|  
| [Conversion Functions](conversion-functions-azure-stream-analytics.md)| These functions allow you to cast data into different formats. |
| [Date and Time Functions](date-and-time-functions-azure-stream-analytics.md)| These functions allow you to perform operations on DateTime formats. |
| [Mathematical Functions](mathematical-functions-azure-stream-analytics.md)| Represent the scalar functions that perform a calculation, usually based on input values that are provided as arguments, and return a numeric value. |
| [String Functions](string-functions-azure-stream-analytics.md)| These functions allow you to convert strings to upper or lower case. |
  
## See Also  
 [Data Types](data-types-azure-stream-analytics.md)   
 [Query Language Elements](query-language-elements-azure-stream-analytics.md)   
 [Time Management](time-management-azure-stream-analytics.md)  
  
  
