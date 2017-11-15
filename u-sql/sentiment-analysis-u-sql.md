---
title: "Sentiment Analysis (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-05"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 470c25ae-e61b-4857-9b96-ceeb8f3229c2
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Sentiment Analysis (U-SQL)
The `SentimentAnalyzer` cognitive function evaluates sentiment from the text. It returns a numeric score between 0 and 1 long with the sentiment string from the text. Scores close to 1 indicate positive sentiment and scores close to 0 indicate negative sentiment. Sentiment score is generated using classification techniques. The input features of the classifier include n-grams, features generated from part-of-speech tags, and word embeddings. English text is supported.

<table><th align="left">Arguments TBD</th><tr><td><pre>
SentimentAnalyzer(                                                                                       
     string TBD  = "TBD", 
     string TBD  = "Sentiment",
     string TBD  = "Conf")
</pre></td></tr></table>

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Books**  
The examples utilize two books: War and Peace, and Peter Pan.    
* `war_and_peace.csv` is installed automatically when you install the cognitive assemblies.  The file is located at `/usqlext/samples/cognition/war_and_peace.csv`.  
* `PeterPan.txt` was obtained from `https://www.gutenberg.org/files/16/16-0.txt`.


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

**Extract Sentiment**
```
REFERENCE ASSEMBLY [TextSentiment];

// War and Peace
@sentiment =
    PROCESS @book
    PRODUCE No,
            Year,
            Book,
            Chapter,
            Text,
            Sentiment string,
            Conf double
    READONLY No,
            Year,
            Book,
            Chapter,
            Text
    USING new Cognition.Text.SentimentAnalyzer(true); // true returns confidence

// Peter Pan
@otherSentiment =
    PROCESS @otherBook
    PRODUCE Text,
            Sentiment string,
            Conf double
    READONLY Text
    USING new Cognition.Text.SentimentAnalyzer(true); // true returns confidence

OUTPUT @sentiment
TO "/ReferenceGuide/Cognition/Text/SentimentAnalyzer1A.txt"
USING Outputters.Tsv();

OUTPUT @otherSentiment
TO "/ReferenceGuide/Cognition/Text/SentimentAnalyzer1B.txt"
USING Outputters.Tsv();
```

**Calculate average sentiment**
```
// War and Peace
@grouped =
    SELECT Year,
           Book,
           Chapter,
           AVG(Conf) AS Sentiment
    FROM @sentiment
    GROUP BY Year,
             Book,
             Chapter;

// Peter Pan
@otherGrouped =
    SELECT AVG(Conf) AS Sentiment
    FROM @sentiment;

OUTPUT @grouped
TO "/ReferenceGuide/Cognition/Text/SentimentAnalyzer2A.txt"
USING Outputters.Tsv();

OUTPUT @otherGrouped
TO "/ReferenceGuide/Cognition/Text/SentimentAnalyzer2B.txt"
USING Outputters.Tsv();
```

**Combine the key phrases and chapter sentiment analysis**
```
REFERENCE ASSEMBLY [TextKeyPhrase];

// First capture key phrases
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

@KPsplits =
    SELECT No,
           Year,
           Book,
           Chapter,
           Text,
           T.KeyPhrase
    FROM @keyphrase
         CROSS APPLY EXPLODE (KeyPhrase.Split(';')) AS T(KeyPhrase);

// Then combine with sentiment extracted from earlier example
@all =
    SELECT K.Year,
           K.Book,
           K.Chapter,
           K.Text,
           K.KeyPhrase,
           S.Conf AS Sentiment
    FROM @KPsplits AS K
         INNER JOIN
             @sentiment AS S
         ON K.No == S.No;

OUTPUT @all
TO "/ReferenceGuide/Cognition/Text/SentimentAnalyzer3A.txt"
USING Outputters.Tsv();
```



### See Also
* [Built-in U-SQL System Objects and Extensions](../USQL/built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](../USQL/extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md)
* [Key Phrases Extraction (U-SQL)](../USQL/key-phrases-extraction-u-sql.md)

