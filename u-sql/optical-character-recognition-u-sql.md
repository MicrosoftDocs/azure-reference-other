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
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Optical Character Recognition (U-SQL)
Optical character recognition (OCR) functions analyze images to detect embedded text. There are two ways in U-SQL to detect text from an image:

* OcrApplier
* OcrExtractor 

> [!IMPORTANT]  
> Use an Extractor rather than an Applier when you have images larger than 4 MB.

The extractor allows to perform the OCR processing directly on files, thus avoiding the 4 MB file size limit. As a trade-off, the scale is limited by the scale of operating on file sets (up to 10000s of files) compared to millions of rows with the applier. The applier and extractor also allow identifying several text fragments in an image with their bounding box.


## OcrApplier 
### Arguments
<pre>
public OcrApplier(
    string imgCol = "ImgData", 
    string txtCol = "Text") 
</pre>

For each JPEG image provided as a byte array in the column with the default name ImgData, it returns one row per detected string in the file with additional information about the detected string's bounding box (columns: `RectX`, `RectY`, `Width`, `Height` all of type `float`).



## OcrExtractor
### Arguments
<pre>
Cognition.Vision.OcrExtractor(
    string txtCol = "Text")
</pre>

For each JPEG file it gets applied to, this U-SQL extractor returns one row per detected string in the file (column `Text` of type `string`) with additional information about the detected string's bounding box (columns: `RectX`, `RectY`, `Width`, `Height` all of type `float`).

All columns have to be specified in the EXTRACT clause.


## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.


### A.	OcrApplier
**Detect text using Applier**  
The following script creates a rowset of all detected strings and their bounding boxes from an input rowset called `@images` that contains the JPEG images in the column image:
```sql
REFERENCE ASSEMBLY ImageCommon;
REFERENCE ASSEMBLY ImageOcr;

@images =
  EXTRACT FileName string,
          image byte[]
  FROM @"/Samples/Images/{FileName}.jpg"
  USING new Cognition.Vision.ImageExtractor();

@ocrs_from_applier =
  SELECT FileName,
         ocr.Text,
         ocr.RectX,
         ocr.RectY,
         ocr.Width,
         ocr.Height
         // , ocr.*
  FROM @images 
  CROSS APPLY USING
             new Cognition.Vision.OcrApplier(imgCol : "image") AS
              ocr(
                RectX float, RectY float, Width float, Height float, 
                Text string);

OUTPUT @ocrs_from_applier 
TO "/ReferenceGuide/Cognition/OCR/ocr_applier.csv"
USING Outputters.Csv(outputHeader : true);
```

### B.	OcrExtractor
**Detect text using Extractor**  
The following statement creates a rowset of all detected strings and their bounding boxes from all JPEG files with the file extension .JPG in the specified directory. It uses a different column name for the number of faces in the image column.
```sql
REFERENCE ASSEMBLY ImageCommon;
REFERENCE ASSEMBLY ImageOcr;

@ocrs_from_extractor =
  EXTRACT FileName string, 
          RectX float,
          RectY float,
          Width float,
          Height float,
          Text string
  FROM @"/Samples/Images/{FileName}.jpg"
  USING new Cognition.Vision.OcrExtractor(txtCol : "Text");

OUTPUT @ocrs_from_extractor 
TO "/ReferenceGuide/Cognition/OCR/ocr_extractor.csv"
USING Outputters.Csv(outputHeader : true);
```


## See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* [ImageExtractor (U-SQL)](imageextractor-u-sql.md)

 
