---
title: "AsEnumerable (Method Syntax in U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# AsEnumerable (Method Syntax in U-SQL)
Returns the input typed as [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
**Basic Example**  
The AsEnumerable\<TSource>(IEnumerable<TSource>) method has no effect other than to change the compile-time type of source from a type that implements IEnumerable\<T> to IEnumerable\<T> itself.  
The illustration below is specifically designed to be executed in Visual Studio with IntelliSense enabled.  
In the first declaration, add a dot (".") immediatly after "()", and before the semi-colon.  Note that IntelliSense will present property "Count",
as well as the Enumerable Method "Count".  
In the second declaration, add a dot (".") immediatly after "()", and before the semi-colon.  Note that the property "Count" is no loger visible and only the Enumerable Method can be selected.  
Try again and note the behaviour with the string method "Contains" and the enumberable method "Contains."
```sql
DECLARE @TimeZoneInfo1 = TimeZoneInfo.GetSystemTimeZones()  ;
DECLARE @TimeZoneInfo2 = TimeZoneInfo.GetSystemTimeZones().AsEnumerable()  ;
```

## See Also
* [Enumerable.AsEnumerable (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.AsEnumerable)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
