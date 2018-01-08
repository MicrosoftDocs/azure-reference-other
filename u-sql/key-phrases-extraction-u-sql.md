---
title: "Key Phrases Extraction (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb05c292-8dbe-43df-8c24-c0726420e16f
caps.latest.revision: 5
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Key Phrases Extraction (U-SQL)
The `KeyPhraseExtractor` cognitive function returns a list of “;” separated strings denoting the key talking points in the input text. This cognitive function employ techniques from Microsoft Office's sophisticated Natural Language Processing toolkit and supports English text.

<table><th align="left">Arguments TBD</th><tr><td><pre>
KeyPhraseExtractor(                                                                                      
     string TBD = "TBD", 
     string outCol = "KeyPhrase")
</pre></td></tr></table>

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Books**  
The examples utilize two books: War and Peace, and Peter Pan.    
- `war_and_peace.csv` is installed automatically when you install the cognitive assemblies.  The file is located at `/usqlext/samples/cognition/war_and_peace.csv`.  
- `PeterPan.txt` was obtained from `https://www.gutenberg.org/files/16/16-0.txt`.

**Extract Text**
```
// War and Peace
@book =
    EXTRACT No int,
            Year string,
            Book string,
            Chapter string,
            Text string
    FROM @"/Samples/Books/war_and_peace.csv"
    USING Extractors.Csv();

// Peter Pan
@otherBook =
    EXTRACT Text string
    FROM @"/Samples/Books/PeterPan.txt"
    USING Extractors.Text(silent: true, delimiter: '`');
```

**Extract Key Phrases**
```
REFERENCE ASSEMBLY [TextKeyPhrase];

// War and Peace
@keyphrase =
    PROCESS @book
    PRODUCE No,
            Year,
            Book,
            Chapter,
            Text,
            KeyPhrase string
    READONLY No,
            Year,
            Book,
            Chapter,
            Text
    USING new Cognition.Text.KeyPhraseExtractor();

// Peter Pan
@otherKeyPhrases =
    PROCESS @otherBook
    PRODUCE Text,
            KeyPhrase string
    READONLY Text
    USING new Cognition.Text.KeyPhraseExtractor();

OUTPUT @keyphrase
TO "/ReferenceGuide/Cognition/Text/KeyPhraseExtractor1A.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @otherKeyPhrases
TO "/ReferenceGuide/Cognition/Text/KeyPhraseExtractor1B.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Tokenize the key phrases**
```
// War and Peace
@KPsplits =
    SELECT No,
           Year,
           Book,
           Chapter,
           Text,
           T.KeyPhrase
    FROM @keyphrase
         CROSS APPLY EXPLODE (KeyPhrase.Split(';')) AS T(KeyPhrase);

// Peter Pan
@OtherKPsplits =
    SELECT Text,
           T.KeyPhrase 
    FROM @otherKeyPhrases
         CROSS APPLY EXPLODE (KeyPhrase.Split(';')) AS T(KeyPhrase);

OUTPUT @KPsplits
TO "/ReferenceGuide/Cognition/Text/KeyPhraseExtractor2A.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @OtherKPsplits
TO "/ReferenceGuide/Cognition/Text/KeyPhraseExtractor2B.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Some queries against `@KPsplits ` from above example**
```
// Top 5 key phrases overall
@wordCount = 
    SELECT KeyPhrase, COUNT(KeyPhrase) AS wordCount
    FROM @KPsplits
    WHERE NOT string.IsNullOrEmpty(KeyPhrase)
    GROUP BY KeyPhrase
    ORDER BY COUNT(KeyPhrase) DESC FETCH 5 ROWS;

OUTPUT @wordCount
TO "/ReferenceGuide/Cognition/Text/wordCount1.txt"
USING Outputters.Tsv();


// Top 5 key phrases and chapter 
@wordCount =
    SELECT 
            Chapter,
           KeyPhrase,
           COUNT(KeyPhrase) AS PhraseCount
    FROM @KPsplits
    WHERE NOT string.IsNullOrEmpty(KeyPhrase)
    GROUP BY Chapter, KeyPhrase
    ORDER BY COUNT(KeyPhrase) DESC FETCH 5 ROWS;

OUTPUT @wordCount
TO "/ReferenceGuide/Cognition/Text/wordCount2.txt"
USING Outputters.Tsv();

// Top 5 key phrases per chapter 
@wordCount =
    SELECT 
            Chapter,
           KeyPhrase,
           COUNT(KeyPhrase) AS PhraseCount
    FROM @KPsplits
    WHERE NOT string.IsNullOrEmpty(KeyPhrase)
    GROUP BY Chapter, KeyPhrase;

@wordCount =
    SELECT ROW_NUMBER() OVER(PARTITION BY Chapter ORDER BY PhraseCount DESC ) AS RowNumber,
            Chapter,
            KeyPhrase,
           PhraseCount
    FROM @wordCount;

@wordCount =
    SELECT Chapter,
            KeyPhrase,
           PhraseCount
    FROM @wordCount
    WHERE RowNumber < 6;

OUTPUT @wordCount
TO "/ReferenceGuide/Cognition/Text/wordCount3.txt"
USING Outputters.Tsv();
```



### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md)
* [Sentiment Analysis (U-SQL)](sentiment-analysis-u-sql.md)


