---
title: "C# Function Variables (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-05-18"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# C&#35; Function Variables (U-SQL)
C# function variables provide parameterization of C# expressions and a more light-weight approach of adding functional abstractions to your U-SQL script. The function variables (or "named lambdas") can be shared with others via the use of [U-SQL packages](u-sql-packages.md).

## Syntax
<pre>
Scalar_Variable_Assignment :=
    'DECLARE' <a href="#user_var">User_Variable</a> [Variable_Type] = <a href="#csharp_exp">csharp_expression</a>.

<a href="#var_type">Variable_Type</a> := 
    <a href="built-in-u-sql-types.md">Built_in_Type</a> | dotnet_type.
</pre>
<br />

 
## Semantics of Syntax Elements  
- <a name="user_var"></a>**`User_Variable`**  
Specifies the name of the variable. User variables start with a single `@` sign.

- <a name="var_type"></a>**`Variable_Type`**  
Optional and specifies the variable's type. It can be any valid U-SQL [built-in type](built-in-u-sql-types.md) or .Net type, including function types (`Func<>`) and user defined types. If it is not specified, the type is inferred from the expression.

- <a name="csharp_exp"></a>**`csharp_expression`**  
Any valid C# expression. If the variable type is a function type, it can be a lambda expression or a lambda expression containing a C# block. If the expression's result type is not consistent with the specified variable type, a compile time error is raised. 

## Limitation
A function variable inside a [U-SQL package](u-sql-packages.md) currently can not refer to another variable.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

 

**Basic Example**   
The following script uses a function variable to analyze tweets.
```sql 
DECLARE @get_mentions Func<string,SqlArray<string>> = 
         (tweet) => new SqlArray<string>(
                        tweet.Split(new char[]{' ', ',', '.', ':', '!', ';', '"', '“'}).Where(x => x.StartsWith("@"))
                    );

@data = 
    SELECT * FROM 
        ( VALUES
        ("11/12/2015", "23:51", "MikeDoesBigData", "@ctesta_oneill No questions on #U-SQL yet? :) Enjoy the weekend!"),
        ("01/12/2015", "19:55", "MikeDoesBigData", "@MarkTabNet @Azure @sqlpass Cool :) #U-SQL"),
        ("01/12/2015", "02:27", "MikeDoesBigData", "@ctesta_oneill Sure. Just fire away :)"),
        ("06/11/2015", "06:25", "MikeDoesBigData", "@memsql Cosmos rocks :)"),
        ("06/11/2015", "01:49", "OliverAsmus", "@jamie_dixon @MikeDoesBigData That would make sense too"),
        ("05/11/2015", "23:16", "OliverAsmus", "@MikeDoesBigData That helps...thank you!"),
        ("06/11/2015", "23:19", "jamie_dixon", "@MikeDoesBigData you never showed up for the F# ML workshop!"),
        ("16/09/2013", "07:55", "GiessweinWeb", "@SQLServerMike Hi do you know http://t.co/yIJvQ6KXD8 ?"),
        ("21/03/2013", "21:37", "mwinkle", "@SQLServerMike kudos sir!")
        ) AS T(date, time, author, tweet);

// Extract mentions
@mentions = 
    SELECT @get_mentions(tweet) AS mentions 
    FROM @data;

@mentions = 
    SELECT m.Substring(1) AS m, 
           "mention" AS category
    FROM @mentions CROSS APPLY EXPLODE(mentions) AS T(m)
    WHERE m != "@";

// Count mentions 
@result = 
    SELECT m.ToLowerInvariant() AS mention, 
           COUNT( * ) AS mentioncount
    FROM @mentions
    GROUP BY m.ToLowerInvariant();

OUTPUT @result
TO "/ReferenceGuide/Variables/FunctionVariables/MyTwitterAnalysis.csv"
ORDER BY mentioncount DESC
USING Outputters.Csv(outputHeader:true);
``` 

**Advanced Example**  
The following scripts show how the function variable can consist of more complex C# expressions, how they can invoke each other and be part of [U-SQL packages](u-sql-packages.md). In particular, the example shows how to package the [TryParse](https://msdn.microsoft.com/library/system.datetime.tryparse(v=vs.110).aspx) expression into a single function.

First, a package is created with the function variables @EnumerateToFloor and @TryParseDateTime.  Then the package is imported and the two functions are used.

```sql  
//First, create package and then comment this code block  
 DROP PACKAGE IF EXISTS MyFunctions;

 CREATE PACKAGE MyFunctions() AS
 BEGIN
   EXPORT @EnumerateToFloor Func<int,double,IEnumerable<int>> = 
          (x, y) => Enumerable.Range(x, (int) Math.Floor(y));

   EXPORT @TryParseDateTime Func<string, DateTime?> = 
          (d) => {
                   DateTime dt; 
                   var b = DateTime.TryParse(d, out dt); 
                   return b ? (DateTime?) dt : (DateTime?) null;
                 };
 END;



// Second, uncomment this section once the package has been created
/*
IMPORT PACKAGE MyFunctions() AS myfns;

// Using @EnumerateToFloor
 @data1 = 
   SELECT * 
   FROM (VALUES(1, (float)456, (float)5.2)) AS T(id, revenueamount, BillingFrequency);

 @result = 
   SELECT *
   FROM @data1 
   CROSS APPLY EXPLODE (myfns.@EnumerateToFloor(1, BillingFrequency)) AS q(Quartile);

OUTPUT @result
TO "/ReferenceGuide/Variables/FunctionVariables/EnumerateToFloor.csv"
USING Outputters.Csv(outputHeader : true);


 // Using @TryParseDateTime
 @data2 =
   SELECT myfns.@TryParseDateTime(c_date_str) AS c_date
   FROM (VALUES
         ("2018-01-01T01:02:03"),
         ("12/13/2017"),
         ("invalid")
        ) AS T(c_date_str);

OUTPUT @data2
TO "/ReferenceGuide/Variables/FunctionVariables/TryParseDateTime.csv"
USING Outputters.Csv(outputHeader : true);
*/
```


## See Also 
* [DECLARE Variables (U-SQL)](declare-variables-u-sql.md)
* [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md) 
* [Lambda Expressions (C# Programming Guide)](https://docs.microsoft.com/dotnet/csharp/programming-guide/statements-expressions-operators/lambda-expressions)
