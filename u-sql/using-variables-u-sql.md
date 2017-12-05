---
title: "Using Variables (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/27/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 91666d8a-fbcc-494a-9f31-4770d1c880f3
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Using Variables (U-SQL)

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Use scalar variables**  
You can use scalar variables as well to make your script maintenance easier. 
```
DECLARE @in  string = "/Samples/Data/SearchLog.tsv";
DECLARE @out string = "/output/SearchLog-scalar-variables.csv";

@searchlog =
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int?,
            Urls            string,
            ClickedUrls     string
    FROM @in
    USING Extractors.Tsv();

OUTPUT @searchlog   
    TO @out
    USING Outputters.Csv();
```

### See Also
* [DECLARE Variables (U-SQL)](declare-variables-u-sql.md)  