---
title: "ARRAY_AGG (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: eaa77b64-5264-4d25-81b9-3646e4687800
caps.latest.revision: 11
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ARRAY_AGG (U-SQL)
The ARRAY_AGG aggregator creates a new [SQL.ARRAY](complex-built-in-u-sql-types.md) value per group that will contain the values of group as its items.  ARRAY_AGG is not preserving order of values inside a group. If an array needs to be ordered, a LINQ OrderBy can be used.  ARRAY_AGG and [EXPLODE](explode-u-sql.md) are conceptually inverse operations. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
ARRAY_AGG_Expression :=                                                                                  
      'ARRAY_AGG' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**   
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. The type of the expression has to be a [built-in U-SQL type](built-in-u-sql-types.md), including [SQL.MAP](complex-built-in-u-sql-types.md) or [SQL.ARRAY](complex-built-in-u-sql-types.md). 

### Return Type 
[SQL.ARRAY](complex-built-in-u-sql-types.md)\<T\> where T is the type of the input expression. 

### Usage in Windowing Expression
This aggregator cannot be used in a [windowing expression](over-expression-u-sql.md). 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

 
**A. ARRAY_AGG**   
This example aggregates the phone numbers as one group per employee.
```
@employees = 
    SELECT * FROM 
        ( VALUES
        ("Noah",   "cell:030-0074321"),
        ("Noah",   "office:030-0076545"),
        ("Sophia", "cell:(5) 555-4729"),
        ("Sophia", "office:(5) 555-3745"),
        ("Liam",   "cell:(5) 555-3932"),
        ("Amy",    "cell:(171) 555-7788"),
        ("Amy",    "office:(171) 555-6750"), 
        ("Amy",    "home:(425) 555-6238"),
        ("Justin", "cell:0921-12 34 65"),
        ("Justin", "office:0921-12 34 67"),
        ("Emma",   (string)null),
        ("Jacob",  ""),
        ("Olivia", "cell:88.60.15.31"),
        ("Olivia", "office:88.60.15.32"),
        ("Mason",  "cell:(91) 555 22 82"),
        ("Mason",  "office:(91) 555 91 99"), 
        ("Mason",  "home:(425) 555-2819"),
        ("Ava",    "cell:91.24.45.40"),
        ("Ava",    "office:91.24.45.41"),
        ("Ethan",  "cell:(604) 555-4729"),
        ("Ethan",  "office:(604) 555-3745"),
        ("David",  "cell:(171) 555-1212"),
        ("Andrew", "cell:(1) 135-5555"),
        ("Andrew", "office:(1) 135-4892"),
        ("Jennie", "cell:(5) 555-3392"),
        ("Jennie", "office:(5) 555-7293")
        ) AS T(EmpName, PhoneNumber);
        
@result =
    SELECT EmpName,
           string.Join(", ", ARRAY_AGG(PhoneNumber)) AS PhoneNumbers
    FROM @employees
    WHERE !string.IsNullOrEmpty(PhoneNumber)
    GROUP BY EmpName;

OUTPUT @result
TO "/Output/ReferenceGuide/Aggregate/array_agg/exampleA.csv"
USING Outputters.Csv();
```

**B. EXPLODE - bonus example**  
This example does not use `ARRAY_AGG`; however, it illustrates how to reverse the outcome from the above example using [EXPLODE](explode-u-sql.md).
```
@result =
    SELECT EmpName,
           new SQL.ARRAY<string>(PhoneNumbers.Split(',')) AS PhoneNumbersArray
    FROM @result;

@exploded =
    SELECT EmpName,
           PhoneNumber.Trim() AS PhoneNumber
    FROM @result
    CROSS APPLY 
    EXPLODE(PhoneNumbersArray) AS r(PhoneNumber);

OUTPUT @exploded
TO "/Output/ReferenceGuide/Aggregate/array_agg/exampleB.csv"
USING Outputters.Csv();
```

**C. ARRAY_AGG - additional example**   
This example deals with a common many-to-many relationship. Here, a film can have more than one producer and you would like to have all producers listed in one record. The following query will aggregate all producers.   
This example provides an alternative solution to [Using User Defined Aggregator - genericAggregator B](extending-u-sql-expressions-with-user-code.md#genericAggB).
```
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
           string.Join(", ", ARRAY_AGG(p.Producer)) AS Producers
    FROM @films AS f
         JOIN
             @films_producers AS fp
         ON f.FilmID == fp.FilmID
         JOIN
             @producers AS p
         ON p.ProducerID == fp.ProducerID
    GROUP BY f.Title;

OUTPUT @result
TO "/Output/ReferenceGuide/Aggregate/array_agg/exampleC.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)   
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md) 
* [EXPLODE (U-SQL)](explode-u-sql.md) 
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
