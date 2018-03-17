---
title: "Face Detection (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bc7db2cd-b571-4253-a4e0-4bbd68904414
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# Face Detection (U-SQL)
Cognitive face detection functions detect one or more human faces in an image and return face rectangles for where in the image the faces are, along with face attributes like age and gender. There are two ways in U-SQL to extract age and gender from the face in an image:

* FaceDetectionApplier
* FaceDetectionExtractor 

> [!IMPORTANT]
> Use an Extractor rather than an Applier when you have images larger than 4 MB.

## FaceDetectionApplier
<table><th align="left">Arguments</th><tr><td><pre>
FaceDetectionApplier(                                                                                    
    string imgCol     = "ImgData", 
    string numCol     = "NumFaces", 
    string indexCol   = "FaceIndex", 
    string ageCol     = "FaceAge", 
    string genderCol  = "FaceGender")
</pre></td></tr></table>

`FaceDetectionApplier` is applied to each image in the byte array column with the default name `ImgData` and it generates one row per face detected in the file. It returns the number of detected faces in the image (column `NumFaces` of type int), the current index of the face from all the faces recognized in the image for the returned row (column `FaceIndex` of type int) and its face rectangle (columns `RectX`, `RectY`, `Width`, `Height` of type float) along with the estimated age (column `FaceAge` of type int) and gender (column `FaceGender` of type string) for the current face.
 

## FaceDetectionExtractor
<table><th align="left">Arguments</th><tr><td><pre>
FaceDetectionExtractor(                                                                                  
    string numCol     = "NumFaces", 
    string indexCol   = "FaceIndex", 
    string ageCol     = "FaceAge", 
    string genderCol  = "FaceGender")
</pre></td></tr></table>

`FaceDetectionExtractor` is applied to each image and it generates one row per face detected in the file. It returns the number of detected faces in the image (column `NumFaces` of type int), the current index of the face from all the faces recognized in the image for the returned row (column `FaceIndex` of type int) and its face rectangle (columns `RectX`, `RectY`, `Width`, `Height` of type float) along with the estimated age (column `FaceAge` of type int) and gender (column `FaceGender` of type string) for the current face.


### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.


### A.	FaceDetectionApplier
**Estimate age and gender for human faces using Applier**
```
REFERENCE ASSEMBLY ImageCommon;       
REFERENCE ASSEMBLY FaceSdk;

// Load images
@images =
    EXTRACT FileName string, 
            ImgData byte[]
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.ImageExtractor();

@faces_from_applier =
    SELECT FileName,
        Details.NumFaces,
        Details.FaceIndex,
        Details.RectX, Details.RectY, Details.Width, Details.Height,
        Details.FaceAge,
        Details.FaceGender
    FROM @images
    CROSS APPLY
        USING new Cognition.Vision.FaceDetectionApplier() AS Details(
            NumFaces int, 
            FaceIndex int, 
            RectX float, RectY float, Width float, Height float, 
            FaceAge int, 
            FaceGender string);

OUTPUT @faces_from_applier
TO "/ReferenceGuide/Cognition/Vision/FaceDetectionApplier.txt"
USING Outputters.Tsv(outputHeader: true);

```

### B.	FaceDetectionExtractor
**Extract age and gender using Face Detection Extractor**
```
REFERENCE ASSEMBLY ImageCommon; 
REFERENCE ASSEMBLY FaceSdk;       

@faces_from_extractor =
    EXTRACT FileName string, 
        NumFaces int, 
        FaceIndex int, 
        RectX float, RectY float, Width float, Height float, 
        FaceAge int, 
        FaceGender string
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.FaceDetectionExtractor();

OUTPUT @faces_from_extractor
TO "/ReferenceGuide/Cognition/Vision/FaceDetectionExtractor.txt"
USING Outputters.Tsv(outputHeader: true);
```


### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* [ImageExtractor (U-SQL)](imageextractor-u-sql.md)

 
