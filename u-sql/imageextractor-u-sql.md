---
title: "ImageExtractor (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-02"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b170d0e6-2f0a-455a-98d9-47ed8665d7f5
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ImageExtractor (U-SQL)
The `ImageExtractor` function from the `ImageCommon` assembly is used to extract data from images that will be consumed by other cognitive functions.  The current maximum size of a row is 4 MB so you will need to use images less than 4 MB in size when using `ImageExtractor`.


### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.

**Load images to a rowset variable**  
```
REFERENCE ASSEMBLY ImageCommon;   

@images =
    EXTRACT FileName string, 
            ImgData byte[]
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.ImageExtractor();

@result = 
    SELECT FileName FROM @images;

OUTPUT @result 
TO "/ReferenceGuide/Cognition/Vision/ImageExtractor_rv.txt" 
USING Outputters.Tsv();
```

**Load images to a table**<a name="loadImages"></a>  
This table will be referenced in various cognitive examples
```
REFERENCE ASSEMBLY ImageCommon;   

DROP TABLE IF EXISTS dbo.myImages;
CREATE TABLE dbo.myImages (
       INDEX clx_FileName CLUSTERED(FileName ASC) 
       DISTRIBUTED BY HASH (FileName)
) AS EXTRACT FileName   string,
            ImgData     byte[]
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.ImageExtractor();
```



### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)

