---
title: "Key Phrase Extraction (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb05c292-8dbe-43df-8c24-c0726420e16f
caps.latest.revision: 5
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Key Phrase Extraction (U-SQL)
The Key Phrase Extraction cognitive functions return strings denoting the key talking points in the input text. These cognitive functions employ techniques from Microsoft Office's sophisticated Natural Language Processing toolkit and supports English text. There are two ways in U-SQL to extract key phrases from text:

* KeyPhraseProcessor 
* KeyPhraseExtractor  

> [!IMPORTANT]  
> Use an Extractor rather than a Processor  when you have text larger than the [string size limit](textual-types-and-literals.md).

The extractor allows to perform the key phrase extraction directly on files, thus avoiding the size limit. As a trade-off, the scale is limited by the scale of operating on file sets (up to 10000s of files) compared to millions of rows with the processor. In addition, the key phrases are now returned in a SqlArray<string> thus being only limited by the row size.


## KeyPhraseProcessor  
### Arguments
<pre>
Cognition.Text.KeyPhraseProcessor (
    string txtCol = "Text",
    string outCol = "KeyPhrase") 
</pre>

For each row in its input rowset this U-SQL processor returns one row providing the detected key phrases (column `KeyPhrase` of type `SqlArray<string>`) for the specified input text column (column `Text` of type `string`).


## KeyPhraseExtractor
### Arguments
<pre>
Cognition.Text.KeyPhraseExtractor(
    string outCol = "KeyPhrase", 
    string numCol = "NumPhrases") 
</pre>

For each text file it gets applied to, this U-SQL extractor returns one row per file providing the number of detected key phrases (column `NumPhrases` of type `int`) and the key phrases (column `KeyPhrase` of type `SqlArray<string>`).

All columns have to be specified in the EXTRACT clause.


## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Books**  
The examples utilize two books: War and Peace, and Peter Pan.  
- `war_and_peace.csv` is installed automatically when you install the cognitive assemblies.  The file is located at `/usqlext/samples/cognition/war_and_peace.csv`.  
- `PeterPan.txt` was obtained from `https://www.gutenberg.org/files/16/16-0.txt`.


### A.	KeyPhraseProcessor
**Identify key phrases using Processor**  
The following statement extracts the key phrases from the specified files (War and Peace) together with their count. It uses the default column names.
```sql
REFERENCE ASSEMBLY [TextKeyPhrase];

@WarAndPeace =
  EXTRACT No int,
          Year string,
          Book string,
          Chapter string,
          Sentence string
  FROM @"/Samples/Books/war_and_peace.csv"
  USING Extractors.Csv();

@keyphrase =
  PROCESS @WarAndPeace
  PRODUCE No,
          Year,
          Book,
          Chapter,
          Sentence,
          KeyPhrase SqlArray<string>
  READONLY No,
           Year,
           Book,
           Chapter,
           Sentence
  USING new Cognition.Text.KeyPhraseProcessor(txtCol:"Sentence");

@keyphrase_exploded =
  SELECT No,
         Year,
         Book,
         Chapter,
         Sentence,
         T.KeyPhrase
  FROM @keyphrase
       CROSS APPLY EXPLODE (KeyPhrase) AS T(KeyPhrase);

OUTPUT @keyphrase_exploded
TO "/ReferenceGuide/Cognition/KeyPhrases/Processor.csv"
ORDER BY No, Year, Book, Chapter
USING Outputters.Csv(outputHeader : true);
```


### B.	KeyPhraseExtractor
**Identify key phrases using Extractor**  
The following statement extracts the key phrases from the specified file's Sentence column (War and Peace).
```sql
REFERENCE ASSEMBLY [TextKeyPhrase];

@keyphrase_from_extractor = 
  EXTRACT //FileName string,
          NumPhrases int,
          KeyPhrase SQL.ARRAY<string>
  FROM @"/Samples/Books/war_and_peace.csv"
  USING new Cognition.Text.KeyPhraseExtractor();

@keyphrase_from_extractor_exploded =
  SELECT // FileName, 
         NumPhrases, T.KeyPhrase
  FROM @keyphrase_from_extractor
  CROSS APPLY EXPLODE (KeyPhrase) AS T(KeyPhrase);

OUTPUT @keyphrase_from_extractor_exploded
TO "/ReferenceGuide/Cognition/KeyPhrases/Extractor.csv"
USING Outputters.Csv(outputHeader : true);
```


## See Also 
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md) 
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md) 
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md) 
* [Sentiment Analysis (U-SQL)](sentiment-analysis-u-sql.md)

 
