---
title: "Extending U-SQL Expressions with User-Code | Microsoft Docs"
ms.custom: ""
ms.date: "10/03/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 21c135a1-328e-4717-882d-95d5bab15932
caps.latest.revision: 36
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# Extending U-SQL Expressions with User-Code
One of the major values of U-SQL is how easy it is to add user-specific code written in C#. Since U-SQL’s type system is based on C# and the U-SQL scalar expression language on the instances of these types is the C# expression language, it is very easy to use the power of the C# language in U-SQL.  
  
There are several ways how C# code can be used to extend U-SQL expressions:  

-   **Inline C# Expressions**  
Inline C# expressions often makes sense if a small set of C# methods need to be applied to process one of the scalar values. E.g., a string type method or a math function.  

-   **User-Defined Aggregators**  
Write user-defined aggregators in a C# assembly and reference them in the U-SQL script.  By providing user-defined aggregators, custom aggregation logic can be plugged into U-SQL’s processing of aggregation with a [GROUP BY](group-by-and-having-clauses-u-sql.md) clause. 

-    **User-Defined Functions**  
Writing user-defined functions in a C# assembly and referencing them in the U-SQL script is preferred for more complex functions if the logic of the function requires the full power of C# beyond its expression language, such as procedural logic or recursion.   
 
-   **User-Defined Operators**  
Write user-defined operators in a C# assembly and reference them in the U-SQL script.  User-defined Operators (UDO) are U-SQL’s custom-coded rowset operators. They are written in C# and provide the ability to generate, process and consume rowsets.  

## User-Defined Code Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

|The following provides examples of implementing user-defined code:|
|---|
|[Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](#usingAssemblies)|
|Inline C# Expressions<br />&emsp;&#9679;&emsp;[Using Round](#usingRound)<br />&emsp;&#9679;&emsp;[Contains](csharp-functions-and-operators-u-sql.md#Contains)|
|User-Defined Aggregators<br />&emsp;&#9679;&emsp;[SampleAggregate](#smpAgg)<br />&emsp;&#9679;&emsp;[genericAggregator](#genericAgg)|
|User-Defined Functions<br />&emsp;&#9679;&emsp;[dt_TryParse_USQL](u-sql-functions.md#dt_TryParse_USQL)<br />&emsp;&#9679;&emsp;[GetFiscalPeriod](u-sql-functions.md#getFiscalPeriod)<br />&emsp;&#9679;&emsp;[ReadStringMap/WriteQuotedStringMap](complex-built-in-u-sql-types.md#ReadStringMap)<br />&emsp;&#9679;&emsp;[HasOfficePhone](#hop)|
|User-Defined Operators<br />&emsp;&#9679;&emsp;Extractors<br />&emsp;&emsp;&emsp;&#9675;&emsp;[SampleExtractor](extract-expression-u-sql.md#SampleExtractor)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[DriverExtractor](extract-expression-u-sql.md#DriverExtractor)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[FlexExtractor](extract-expression-u-sql.md#FlexExtractor)<br />&emsp;&#9679;&emsp;Outputters<br />&emsp;&emsp;&emsp;&#9675;&emsp;[HTMLOutputter](output-statement-u-sql.md#HTMLOutputter)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[DriverOutputter](output-statement-u-sql.md#DriverOutputter)<br />&emsp;&#9679;&emsp;Appliers<br />&emsp;&emsp;&emsp;&#9675;&emsp;[ParserApplier](u-sql-using-apply-with-an-applier-udo.md#ParserApplier)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[IntegerRangeApplier](https://github.com/Azure-Samples/usql-tutorial-samples/tree/master/IntegerRangeApplier)<br />&emsp;&#9679;&emsp;Processors<br />&emsp;&emsp;&emsp;&#9675;&emsp;[FullAddressProcessor](process-expression-u-sql.md#FullAddressProcessor)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[CountryName](process-expression-u-sql.md#CountryName)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[NameProcessor](#NameProcessor)<br />&emsp;&#9679;&emsp;Reducers<br />&emsp;&emsp;&emsp;&#9675;&emsp;[RangeReducer](reduce-expression-u-sql.md#RangeReducer)<br />&emsp;&emsp;&emsp;&#9675;&emsp;[SalesReducer](reduce-expression-u-sql.md#SalesReducer)<br />&emsp;&#9679;&emsp;Combiners<br />&emsp;&emsp;&emsp;&#9675;&emsp;[CombinerEX](combine-expression-u-sql.md#combinerEX)<p>                                                                                                                                                                                                       </p>|

## Using Assemblies <a name="usingAssemblies"></a>  
### Code-Behind vs. Assembly Registration Walkthrough 
For user-defined functions, aggregators and operators, the C# assembly will have to be loaded into the U-SQL metadata catalog either through the use of Code-Behind or Assembly registration.  The main advantage of Code-Behind is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  Some of the disadvantages is that  the code gets uploaded for every script submission and the functionality cannot be shared with others.  For a deeper discussion of Code-Behind versus Assembly registration, see [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/) and [U-SQL Programmability Guide: Using Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1).

The following provides a walkthrough of using a simple function with both Code-Behind and Assembly registration.  The walkthrough assumes you have an existing U-SQL Project.

### Setup
Both methods share the dataset and function defined below.
#### DataSet   

```sql
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB;

DROP TABLE IF EXISTS dbo.simpleTable;
CREATE TABLE dbo.simpleTable
(
    EmpID int,
    EmpName string,
    DeptID int,
    Salary int,
    StartDate DateTime,
    PhoneNumbers string,
    INDEX clx_EmpID CLUSTERED(EmpID)
    DISTRIBUTED BY HASH (EmpID) 
);

INSERT dbo.simpleTable
VALUES
(1, "Noah",   100, 10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
(3, "Liam",   100, 30000, new DateTime(2014,09,14), "cell:(5) 555-3932"),
(6, "Emma",   200, 8000,  new DateTime(2014,03,08), (string)null),
(7, "Jacob",  200, 8000,  new DateTime(2014,09,02), ""),
(8, "Olivia", 200, 8000,  new DateTime(2013,12,11), "office:88.60.15.32"),
(9, "Mason",  300, 50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819");
```

#### Function
```csharp
namespace myFirstNamespace
{
    public class myFirstClass
    {
        public static string myFirstFunction(string s)
        {
            return s + s;
        }
    }
};
```

### Method 1. Using Code-Behind 
In Visual Studio, add a new U-SQL script to your existing U-SQL Project.  From Solution Explorer, open the new usql.cs file associated with your new U-SQL script.  Replace the entire contents with the function defined above. Close the usql.cs file.  Add the code below to your new U-SQL script to call the function.
```sql
@result =
    SELECT EmpName,
           myFirstNamespace.myFirstClass.myFirstFunction(EmpName) AS myFirstFunction_CB
    FROM TestReferenceDB.dbo.simpleTable;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Assemblies/myFirstFunction_CB.txt"
USING Outputters.Tsv();
```

### Method 2. Assembly Registration   
#### A. Compile Assembly   
In Visual Studio, add a new `Class Library (For U-SQL Application)` to your existing solution and name it `myFirstAssembly`.   File `Class1.cs` should be open after you create `myFirstAssembly`.  Replace the entire contents of `Class1.cs` with the function defined earlier above and then close the file.  In Solution Explorer, right-click `myFirstAssembly` and select `Build`.

#### B. Register Assembly 
In Visual Studio, add a new U-SQL script to your existing U-SQL Project and execute the code below to register the assembly, `myFirstAssembly.dll`.
```sql
USE DATABASE TestReferenceDB;
DROP ASSEMBLY IF EXISTS myFirstAssembly;

// modify with your actual path to myFirstAssembly.dll
CREATE ASSEMBLY myFirstAssembly
FROM @"<your path>\myFirstAssembly\bin\Debug\myFirstAssembly.dll";
```  

#### C. Reference Assembly 
Use `REFERENCE ASSEMBLY` to reference the new assembly.  The code below provides three different methods for calling the function, `myFirstFunction`.  
```sql
USE DATABASE TestReferenceDB;

/************* Method 1 *************/
REFERENCE ASSEMBLY myFirstAssembly;

@result =
    SELECT "Method 1" AS Method,
            EmpName,
            myFirstNamespace.myFirstClass.myFirstFunction(EmpName) AS myFirstFunction_AR
    FROM TestReferenceDB.dbo.simpleTable;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Assemblies/myFirstFunction_AR1.txt"
USING Outputters.Tsv();


/************* Method 2 *************/
REFERENCE ASSEMBLY myFirstAssembly;
USING  myFirstNamespace;

@result =
    SELECT "Method 2" AS Method,
            EmpName,
            myFirstClass.myFirstFunction(EmpName) AS myFirstFunction_AR
    FROM TestReferenceDB.dbo.simpleTable;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Assemblies/myFirstFunction_AR2.txt"
USING Outputters.Tsv();


/************* Method 3 *************/
REFERENCE ASSEMBLY myFirstAssembly;
USING xx = myFirstNamespace.myFirstClass;

@result =
    SELECT "Method 3" AS Method,
            EmpName,
            xx.myFirstFunction(EmpName) AS myFirstFunction_AR
    FROM TestReferenceDB.dbo.simpleTable;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Assemblies/myFirstFunction_AR3.txt"
USING Outputters.Tsv();
```
---  
   

<a name="usingRound">**Inline C# Expression - Using Round**</a>  
Example using [Round](https://msdn.microsoft.com/library/system.math.round(v=vs.110).aspx).  See also, [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md).

```sql
@departments = 
    SELECT * FROM 
        ( VALUES
        ("Newton",  23.00m),
        ("Susan",   25.1234m),
        ("Emma",    25.9999m),
        ("Bradley", 25.9900m)
        ) AS T(Cutomer, Balance);

@result =
    SELECT Cutomer,
            Math.Round(Balance, 2) AS Balance
    FROM @departments;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/MathMethods/Round.txt"
USING Outputters.Tsv();
```
---

<a name="smpAgg">**User Defined Aggregator - SampleAggregate**</a>   
Slightly modified example taken from [Azure/usql/Examples/Extensibility-Simple-Examples](https://github.com/Azure/usql/tree/master/Examples/Extensibility-Simple-Examples/Extensibility-Simple-Examples). c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1)
 .cs file.  See usage in next section, **below**.

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
    //User defined aggregate to calculate the total balance by adding or subtracting based on whether its credit or debit
    public class SampleAggregate : IAggregate<string, int, int>
    {
        int balance;

        public override void Init()
        {
            balance = 0;
        }

        public override void Accumulate(string transaction, int amount)
        {
            if (transaction == "Credit")
            {
                balance += amount;
            }
            if (transaction == "Debit")
            {
                balance -= amount;
            }
        }

        public override int Terminate()
        {
            return balance;
        }
    }
}
```

**Using User Defined Aggregator - SampleAggregate**  
The user defined aggregator calculates a balance.  If the transaction type is "Debit", subtract from the balance, if the transaction type is "Credit", add to the balance.  Using the Code-Behind **above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 

```sql
@transactions =
    SELECT * FROM 
        ( VALUES
        ("Bob",     "Credit", 2000),
        ("Olivia",  "Credit", 5000),
        ("Bob",     "Debit",  30),
        ("Olivia",  "Debit",  50),
        ("Bob",     "Debit",  20)           
        ) AS T(customer, transaction, amount);

@balance =
    SELECT  customer,
            AGG<ReferenceGuide_Examples.SampleAggregate>(transaction, amount) AS balance
    FROM @transactions
    GROUP BY customer;

OUTPUT @balance
TO "/Output/ReferenceGuide/Concepts/UserCode/AggregatorA.txt"
USING Outputters.Csv();
```

<a name="genericAgg">**User Defined Aggregator - genericAggregator**</a>   
A basic aggregator that uses generic names to illustrate that the names of the parameters need not match the names of the passed values.
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using Microsoft.Analytics.Interfaces;

namespace ReferenceGuide_Examples
{
    public class genericAggregator : IAggregate<string, string, string>
    {
        string AggregatedValue;

        public override void Init()
        {
            AggregatedValue = "";
        }

        public override void Accumulate(string ValueToAgg, string GroupByValue)
        {
            AggregatedValue += ValueToAgg + ",";
        }

        public override string Terminate()
        {
            // remove last comma
            return AggregatedValue.Substring(0, AggregatedValue.Length - 1);
        }
    }
}
```

<a name="genericAggA">**Using User Defined Aggregator - genericAggregator A**</a>  
`PhoneType` and `PhoneNumber` are aggregated for each `EmpName`.  This example provides an alternative solution to an example from [MAP_AGG (U-SQL)](map-agg-u-sql.md).  Using the Code-Behind **above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 

```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        ("Noah",   "cell",   "030-0074321"),
        ("Noah",   "office", "030-0076545"),
        ("Sophia", "cell",   "(5) 555-4729"),
        ("Sophia", "office", "(5) 555-3745"),
        ("Liam",   "cell",   "(5) 555-3932"),
        ("Amy",    "cell",   "(171) 555-7788"),
        ("Amy",    "office", "(171) 555-6750"), 
        ("Amy",    "home",   "(425) 555-6238"),
        ("Justin", "cell",   "0921-12 34 65"),
        ("Justin", "office", "0921-12 34 67"),
        ("Emma",   (string)null, (string)null),
        ("Jacob",  "", ""),
        ("Olivia", "cell",   "88.60.15.31"),
        ("Olivia", "office", "88.60.15.32"),
        ("Mason",  "cell",   "(91) 555 22 82"),
        ("Mason",  "office", "(91) 555 91 99"), 
        ("Mason",  "home",   "(425) 555-2819"),
        ("Ava",    "cell",   "91.24.45.40"),
        ("Ava",    "office", "91.24.45.41"),
        ("Ethan",  "cell",   "(604) 555-4729"),
        ("Ethan",  "office", "(604) 555-3745"),
        ("David",  "cell",   "(171) 555-1212"),
        ("Andrew", "cell",   "(1) 135-5555"),
        ("Andrew", "office", "(1) 135-4892"),
        ("Jennie", "cell",   "(5) 555-3392"),
        ("Jennie", "office", "(5) 555-7293")
        ) AS T(EmpName, PhoneType, PhoneNumber);

@result =
    SELECT  EmpName, 
            AGG<ReferenceGuide_Examples.genericAggregator>(PhoneType + ": " + PhoneNumber, EmpName) AS aggregatedList
    FROM @employees
    WHERE !string.IsNullOrWhiteSpace(PhoneType)
    GROUP BY EmpName;

OUTPUT @result 
TO "/Output/ReferenceGuide/Concepts/UserCode/UDA/genericAggregatorA.txt"
ORDER BY EmpName ASC
USING Outputters.Text();
```

<a name="genericAggB">**Using User Defined Aggregator - genericAggregator B**</a>  
`Producer` is aggregated for each `Title`.  This example provides an alternative solution to an example from [ARRAY_AGG (U-SQL)](array-agg-u-sql.md).  Using the Code-Behind **further above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 

```sql
@films = 
    SELECT * FROM 
        ( VALUES
        (1, "A Good Year"),
        (2, "American Gangster"),
        (3, "Robin Hood"),
        (4, "The Counselor")
        ) AS T(FilmID, Title);

@producers = 
    SELECT * FROM 
        ( VALUES
        (1, "Ridley Scott"),
        (2, "Brian Grazer"),
        (3, "Russell Crowe"),
        (4, "Nick Wechsler"),
        (5, "Steve Schwartz"),
        (6, "Paula Mae Schwartz")
        ) AS T(ProducerID, Producer);

@films_producers = 
    SELECT * FROM 
        ( VALUES
        (1, 1),
        (2, 1),
        (2, 2),
        (3, 1),
        (3, 2),
        (3, 3),
        (4, 1),
        (4, 4),
        (4, 5),
        (4, 6)
        ) AS T(FilmID, ProducerID);

@result =
    SELECT f.Title,
           COUNT( * ) AS ProducerCount,        
           AGG<ReferenceGuide_Examples.genericAggregator>(p.Producer, f.Title) AS aggregatedList
    FROM @films AS f
         JOIN
             @films_producers AS fp
         ON f.FilmID == fp.FilmID
         JOIN
             @producers AS p
         ON p.ProducerID == fp.ProducerID
    GROUP BY  f.Title;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/UserCode/UDA/genericAggregatorB.csv"
USING Outputters.Csv();
```
---

<a name="hop">**User Defined Function - HasOfficePhone**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file. See also, [U-SQL Functions](u-sql-functions.md).  See usage in next section, **below**.

```csharp
namespace ReferenceGuide_Examples
{
    public class SampleFunction
    {
        public static bool HasOfficePhone(string phonenumbers)
        {
            if (string.IsNullOrEmpty(phonenumbers))
            {
                return false;
            }
            else
            { 
                return phonenumbers.Contains("office:");
            }
        }
    }
}
```

**Using User Defined Function - HasOfficePhone**   
User defined function to see if employee has an office phone.  Using the Code-Behind **above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 

```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14), "cell:(5) 555-3932"),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08), (string)null),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02), ""),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11), "office:88.60.15.32"),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819")
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);

@has_office_phone =
    SELECT EmpName,
           ReferenceGuide_Examples.SampleFunction.HasOfficePhone(PhoneNumbers) AS has_office_phone
    FROM @employees;

OUTPUT @has_office_phone
TO "/Output/ReferenceGuide/DDL/Functions/has_office_phone.txt"
USING Outputters.Csv();
```
---

<a name="NameProcessor">**User Defined Operator - NameProcessor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

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
    //Sample Processor to generate First Initial and last name
    [SqlUserDefinedProcessor]
    public class NameProcessor : IProcessor
    {
        // IRow Process(IRow input, IUpdatableRow output)
        // 
        // Actual implementatoin of the user-defined processor. Overwrites the Process method of IProcessor.
        public override IRow Process(IRow input, IUpdatableRow output)
        {
            string first_name = input.Get<string>("first_name");
            string last_name = input.Get<string>("last_name");
            string name = first_name.Substring(0, 1) + "." + last_name;
            output.Set<string>("name", name);
            return output.AsReadOnly();
        }
    }
}
```

**User Defined Operator - Using NameProcessor**  
Processor tranforms first_name and last_name to take the form first_name_Initial.last_name.  Using the Code-Behind **above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 
```sql
@drivers = 
    SELECT * FROM 
        ( VALUES
        (1, "Maria",     "Anders",   "12209",    "Germany"),
        (3, "Antonio",   "Moreno",   "5023",     "Mexico"),
        (4, "Thomas",    "Hardy",    "WA1 1DP",  "UK"),
        (5, "Christina", "Berglund", "S-958 22", "Sweden"),
        (8, "Martín",    "Sommer",   "28023",    "Spain")
        ) AS T(id, first_name, last_name, zipcode, country);

@drivers_processed =
    PROCESS @drivers
    PRODUCE name string,
            id int,
            zipcode string,
            country string
    READONLY id, zipcode, country
    REQUIRED first_name, last_name
    USING new ReferenceGuide_Examples.NameProcessor();

OUTPUT @drivers_processed
TO "/Output/ReferenceGuide/StatementsAndExpressions/PrimaryRowsetExpressions/Process/drivers_processed.txt"
USING Outputters.Tsv(quoting:false);
```

### See Also  
* [U-SQL Assemblies ](u-sql-assemblies.md)   
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)  
* [Tutorial: Get started with extending U-SQL with Python](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-python-extensions)  
* [Tutorial: Get started with extending U-SQL with R](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-r-extensions)   
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* U-SQL C# Developer’s Guide (Coming soon)  





