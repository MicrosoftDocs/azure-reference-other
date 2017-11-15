---
title: "Image Tagging (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-03"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ab59a2b2-bcc5-4650-a91b-82797d2c67bb
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Image Tagging (U-SQL)
Cognitive image tagging functions return information about visual content found in an image.  Use tagging, descriptions, and domain-specific models to identify content and label content with confidence. There are two ways in U-SQL to extract contents and its confidence from an image:
* ImageTagger
* ImageTagsExtractor

> [!IMPORTANT]
> Use an Extractor rather than a Processor when you have images larger than 4 MB.

<table><th align="left">Arguments</th><tr><td><pre>
ImageTagger | ImageTagsExtractor(                                                                        
    string numCol = "NumObjects", 
    string tagCol = "Tags")
</pre></td></tr></table>

`ImageTagger` and `ImageTagsExtractor` will operate on a JPEG file and return a rowset with two columns called `NumObjects` of type int that provides the number of detected objects in the image and `Tags` that returns a SQL.MAP\<string, float?> instance which contains the set of object tags as keys with a floating point value indicating the confidence of each of the tags as values.


### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.
- The examples utillize the table `myImages` from the example [Load images to a table](imageextractor-u-sql.md#loadImages).

### A.	ImageTagger
**Extract tags from the image using Image tagging Processor**
```
REFERENCE ASSEMBLY ImageCommon; 
REFERENCE ASSEMBLY ImageTagging;

@TaggedObjects =
    PROCESS dbo.myImages    
    PRODUCE FileName,
            NumObjects int,
            Tags SQL.MAP<string, float?>
    READONLY FileName
    USING new Cognition.Vision.ImageTagger();
```

**Perform various queries against `@TaggedObjects` created above**
```
// A record will not be returned for FileName if Tags is empty for that record
@result1A = 
    SELECT  FileName,
            NumObjects,
            T.key AS Content,
            T.value AS Confidence
    FROM    @TaggedObjects
    CROSS APPLY EXPLODE (Tags) AS T(key, value);


// Use the edited code below if you want a default value to be returned for a FileName that has no Tags
@result1B = 
    SELECT  FileName,
            NumObjects,
            T.key AS Content,
            T.value AS Confidence
    FROM    @TaggedObjects
    CROSS APPLY EXPLODE ((Equals(Tags.Count, 0)) ? new SQL.MAP<string, float?>{{"None", 0.0f}} : Tags) AS T(key, value);

// Alternative output
@result2 =
    SELECT FileName,
           NumObjects,
           String.Join("; ", Tags.Select(x => String.Format("{0}:{1}", x.Key, x.Value))) AS TagsString
    FROM @TaggedObjects;

// Filtering
@result3 =
    SELECT FileName,
           NumObjects,
           T.key AS Content,
           T.value AS Confidence
    FROM @TaggedObjects
         CROSS APPLY
             EXPLODE(Tags) AS T(key, value)
    WHERE T.key == "athletic game" 
    AND T.value >= 0.85f;


OUTPUT @result1A
TO "/ReferenceGuide/Cognition/Vision/ImageTagger1A.txt"
ORDER BY FileName
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1B
TO "/ReferenceGuide/Cognition/Vision/ImageTagger1B.txt"
ORDER BY FileName
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result2
TO "/ReferenceGuide/Cognition/Vision/ImageTagger2.txt"
ORDER BY FileName
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/Cognition/Vision/ImageTagger3.txt"
ORDER BY FileName
USING Outputters.Tsv(outputHeader: true);
```

### B.	ImageTagsExtractor
**Extract the tags from each image using image tagging Extractor**
```
REFERENCE ASSEMBLY ImageCommon;   
REFERENCE ASSEMBLY ImageTagging;

@tags =
    EXTRACT FileName string, 
            NumObjects int,
            Tags SQL.MAP<string, float?>
    FROM @"/Samples/Images/{FileName}.jpg"
    USING new Cognition.Vision.ImageTagsExtractor();
```

**Perform various queries against `@tags` created above**
```
// Merge the Map into a string for outputting
@tags_serialized =
    SELECT FileName,
           NumObjects,
           String.Join(";", Tags.Select(x => String.Format("{0}:{1}", x.Key, x.Value))) AS TagsString
    FROM @tags;

// Flatten results
@result2 = 
    SELECT  FileName,
            NumObjects,
            T.key AS Content,
            T.value AS Confidence
    FROM    @tags
    CROSS APPLY EXPLODE (Tags) AS T(key, value);

// alternative view
@result3 =
    SELECT  FileName,
            NumObjects,
            string.Join(",", Tags) AS Tags
    FROM @tags;

OUTPUT @tags_serialized
TO "/ReferenceGuide/Cognition/Vision/ImageTagsExtractor.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/Cognition/Vision/ImageTagsExtractor2.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result3
TO "/ReferenceGuide/Cognition/Vision/ImageTagsExtractor3.txt"
USING Outputters.Tsv();
```

### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* [ImageExtractor (U-SQL)](imageextractor-u-sql.md)


