---
title: "Emotion Extraction (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-03"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c426dba2-3b23-498d-ba07-c04e82feffbb
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Emotion Extraction (U-SQL)
Cognitive emotion functions detect one or more human faces in an image and get back face rectangles for where in the image the faces are, along with face attributes like emotion. There are two ways in U-SQL to extract emotions from the image:
 
* EmotionApplier
* EmotionExtractor

> [!IMPORTANT]
> Use an Extractor rather than an Applier when you have images larger than 4 MB.

## EmotionApplier
<table><th>Arguments</th><tr><td><pre>
EmotionApplier(                                                                                          
    string imgCol = "ImgData",
    string numCol   = "NumFaces", 
    string indexCol = "FaceIndex", 
    string emtCol   = "Emotion", 
    string confCol  = "Confidence") 
</pre></td></tr></table>

For each JPEG image provided as a byte array in the column with the default name `ImgData`, it returns one row per face detected in the file (column `FaceIndex` of type int) with additional information about the detected face's bounding box (columns `RectX`, `RectY`, `Width`, `Height` all of type float), its recognized emotion (column `Emotion` of type string), the confidence value (column `Confidence` of type float) and the overall number of faces detected in the image (column `NumFaces` of type int). 

## EmotionExtractor
<table><th>Arguments</th><tr><td><pre>
EmotionExtractor(                                                                                        
    string numCol   = "NumFaces", 
    string indexCol = "FaceIndex", 
    string emtCol   = "Emotion", 
    string confCol  = "Confidence") 
</pre></td></tr></table>

For each JPEG file it gets applied to, this U-SQL extractor returns one row per face detected in the file (column `FaceIndex` of type int) with additional information about the detected face's bounding box (columns `RectX`, `RectY`, `Width`, `Height` all of type float), its recognized emotion (column `Emotion` of type string), the confidence value (column `Confidence` of type float) and the overall number of faces detected in the image (column `NumFaces` of type int). 


### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.


### A.	EmotionApplier
**Extract tags from the image using Image tagging Applier**
```
REFERENCE ASSEMBLY ImageCommon;       
REFERENCE ASSEMBLY ImageEmotion;

// Load images
@images =
    EXTRACT FileName string, 
            ImgData byte[]
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.ImageExtractor();

@emotions_from_applier =
    SELECT FileName,
        Details.NumFaces,
        Details.FaceIndex,
        Details.RectX, Details.RectY, Details.Width, Details.Height,
        Details.Emotion,
        Details.Confidence
    FROM @images 
    CROSS APPLY
        USING new Cognition.Vision.EmotionApplier() AS Details(
            NumFaces int, 
            FaceIndex int, 
            RectX float, RectY float, Width float, Height float, 
            Emotion string, 
            Confidence float);

OUTPUT @emotions_from_applier
TO "/ReferenceGuide/Cognition/Vision/EmotionApplier.txt"
USING Outputters.Tsv(outputHeader: true);
```


### B.	EmotionExtractor
**Extract face and recognize facial expression using Emotion Extractor**
```
REFERENCE ASSEMBLY ImageCommon;      
REFERENCE ASSEMBLY ImageEmotion;

@emotions_from_extractor =
    EXTRACT FileName string, 
            NumFaces int, 
            FaceIndex int, 
            RectX float, RectY float, Width float, Height float, 
            Emotion string, 
            Confidence float
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.EmotionExtractor();

OUTPUT @emotions_from_extractor
TO "/ReferenceGuide/Cognition/Vision/EmotionExtractor.txt"
USING Outputters.Tsv(outputHeader: true);
```


### See Also
* [Built-in U-SQL System Objects and Extensions](../USQL/built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](../USQL/extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md)
* [ImageExtractor (U-SQL)](../USQL/imageextractor-u-sql.md)


