---
title: "U-SQL Sampling Methods | Microsoft Docs"
ms.custom: ""
ms.date: "09/14/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8aae226c-d132-4f0a-88f6-54267bccd58d
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# U-SQL Sampling Methods

U-SQL supports data sampling natively in a few forms ("Samplers"). The `SAMPLE` [clause](sample-u-sql.md) syntax supports a few Samplers while requiring small edits to the script and the `SAMPLE` [expression](sample-expression-u-sql.md) syntax offers access to additional types of Samplers.

A particular use case for data sampling is that queries having aggregates can be executed more quickly (and possibly with fewer resources) over a sample of the input.  In such cases, the aggregates have to be scaled to compensate for sampling. For a sampled input rowset with weight column `w`, the table below shows how to modify aggregates. In each row, evaluating the expression on the right on the sampled input outputs in expectation the same value that would have been obtained by evaluating the aggregate on the left over the unsampled input.


Original aggregate  | Modified expression  
---------|---------
SUM(X)     |  SUM(w*X)       
COUNT(*)    | SUM(w)
AVG(X)     | SUM(w*X)/ SUM(w)
COUNT(DISTINCT X)     |  w * COUNT(DISTINCT X) if UNIVERSE sample on X        

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable, `@data`.  

**Dataset**   
```sql
@data = 
    SELECT * FROM 
        ( VALUES
        ("02143",   30,     100,  "Smith"),
        ("98052",   25,     50,   "Andersen"),
        ("02139",   30,     75,   "Todd"),
        ("02139",   25,     60,   "Roberts"),
        ("61801",   23,     80,   "Sanders")
        ) AS T(ZipCode, Age, Salary, LastName);
```

**Using SUM with and without a Data Sample**   
```sql
@trueAnswer = 
    SELECT ZipCode, SUM(Salary) AS SalarySum 
    FROM @data 
    GROUP BY ZipCode;

@sampledAnswer = 
    SELECT ZipCode, SUM(w*Salary) AS SampledSalarySum 
    FROM (SAMPLE @data UNIFORM (0.4) WITH WEIGHT AS w) AS ds 
    GROUP BY ZipCode;

OUTPUT @trueAnswer
TO "/ReferenceGuide/QSE/Sample/trueAnswer.txt"
USING Outputters.Tsv();

OUTPUT @sampledAnswer
TO "/ReferenceGuide/QSE/Sample/sampledAnswer.txt"
USING Outputters.Tsv();

```


### See Also  
* [SAMPLE (U-SQL)](sample-u-sql.md)
* [SAMPLE Expression (U-SQL)](sample-expression-u-sql.md)
