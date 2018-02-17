---
title: "Optical Character Recognition (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2eca988e-a262-46e3-9878-0d4afbf714f5
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Optical Character Recognition (U-SQL)
`OcrExtractor` cognitive function detects and extract text in an image.  It analyze images to detect embedded text and generate character streams.

<table><th align="left">Arguments</th><tr><td><pre>
OcrExtractor(                                                                                            
     string imgCol = "ImgData", 
     string txtCol = "Text")
</pre></td></tr></table>

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.
- The examples utillize the table `myImages` from the example [Load images to a table](imageextractor-u-sql.md#loadImages).

**Extract text from the image using OCR Extractor**
```sql
REFERENCE ASSEMBLY ImageCommon; 
REFERENCE ASSEMBLY ImageOcr;

@ocrs =
    PROCESS dbo.myImages
    PRODUCE FileName,
            Text string
    READONLY FileName
    USING new Cognition.Vision.OcrExtractor();

OUTPUT @ocrs
TO "/ReferenceGuide/Cognition/Vision/OcrExtractor.txt"
USING Outputters.Tsv(outputHeader: true);
```


### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* [ImageExtractor (U-SQL)](imageextractor-u-sql.md) 
