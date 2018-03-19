---
title: "U-SQL Functions | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3bf4aae8-c521-434d-9f86-e097ec833e03
caps.latest.revision: 21
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# U-SQL Functions
U-SQL supports scalar functions and table-valued functions. Functions generally take 0 to n arguments and will return a value as a result. While they should be deterministic and side-effect free to not negatively affect U-SQL’s declarative semantics, there is no guarantee that all functions will satisfy this requirement. For more details refer to the function categories below.  
  
Scalar functions – as their names imply – return values that are instances of a type that is not a table type. Currently U-SQL scalar functions fit into three categories: [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf) written in C#, general C# functions from [system provided assemblies](u-sql-assemblies.md), and [built-in U-SQL functions](built-in-functions-u-sql.md).  
  
[U-SQL table-valued functions](u-sql-table-valued-functions.md)  return tables and are written in U-SQL.  

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

<a name="dt_TryParse_USQL">**Function dt_TryParse_USQL**</a>  
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file. See usage in next section, **below**.

```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace ReferenceGuide_Examples
{
    public class MyClass
    {
        public static DateTime? dt_TryParse_USQL(string dateString)
        {
            DateTime dateValue;

            if (DateTime.TryParse(dateString, out dateValue))
                return dateValue;
            else
                return null;
        }
    }
}
```
 
**Using Function dt_TryParse_USQL**  
Using above code-behind and calling function.  Function consumes a string and attempts to convert the string to a DateTime value using DateTime.TryParse.  Using the Code-Behind **above**. 
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   "2/16/2008"),
        (2, "Sophia", "2/16/2008 12:15:12 PM"),
        (3, "Liam",   "16/02/2008 12:15:12"),
        (4, "Amy",    "2017-01-11T16:52:07"),
        (5, "Justin", "")
        ) AS T(EmpID, EmpName, StartDate);

@result = 
    SELECT  
        EmpID,
        EmpName,
        ReferenceGuide_Examples.MyClass.dt_TryParse_USQL(StartDate) AS validated_StartDate
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Functions/dt_TryParse_USQL.csv"
USING Outputters.Csv(outputHeader: true);
```
 
**Using inline function expression**   
Similar as above except here the function is defined inline.
```sql
@result = 
    SELECT
        EmpID,
        EmpName,
        (
            (Func<string, DateTime?>)
            (dateString =>  // input_paramater
                { 
                    DateTime dateValue;
                    return DateTime.TryParse(dateString, out dateValue) ? (DateTime?)dateValue : (DateTime?)null;
                }
             )
        ) (StartDate) AS validated_StartDate
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Functions/inlineFunctionExpression.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="getFiscalPeriod">**Function GetFiscalPeriod**</a>    
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using System;

namespace ReferenceGuide_Examples
{
    public class MyClass
    {
        public static string GetFiscalPeriod(DateTime dt)
        {
            int FiscalMonth = 0;
            if (dt.Month < 7)
            {
                FiscalMonth = dt.Month + 6;
            }
            else
            {
                FiscalMonth = dt.Month - 6;
            }

            int FiscalQuarter = 0;
            if (FiscalMonth >= 1 && FiscalMonth <= 3)
            {
                FiscalQuarter = 1;
            }
            if (FiscalMonth >= 4 && FiscalMonth <= 6)
            {
                FiscalQuarter = 2;
            }
            if (FiscalMonth >= 7 && FiscalMonth <= 9)
            {
                FiscalQuarter = 3;
            }
            if (FiscalMonth >= 10 && FiscalMonth <= 12)
            {
                FiscalQuarter = 4;
            }

            return "Q" + FiscalQuarter.ToString() + ":P" + FiscalMonth.ToString();
        }
    }
}
```

**Using Function GetFiscalPeriod**  
Using above code-behind and calling function.  Function calculates the fiscal month and quarter and returns a string value based on the passed DateTime value.  For additional information, see [U-SQL Programmability Guide: User-Defined Function](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#in-line-c-function-expressions).
```sql
@result = 
    SELECT 
        ReferenceGuide_Examples.MyClass.GetFiscalPeriod(DateTime.Now) AS dd
    FROM 
        (VALUES 
        (1)
        ) AS T(dummyTable);

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Functions/GetFiscalPeriod.txt"
USING Outputters.Tsv();
```

### See Also
* [U-SQL Table-valued Functions](u-sql-table-valued-functions.md)  
* [CREATE FUNCTION (U-SQL): Table-valued Function](create-function-u-sql-table-valued-function.md)   
* [DROP FUNCTION (U-SQL)](drop-function-u-sql.md)   
* [Table-Valued Function Expression (U-SQL)](table-valued-function-expression-u-sql.md) 
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)   
* [U-SQL Programmability Guide: User-Defined Functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)


  

