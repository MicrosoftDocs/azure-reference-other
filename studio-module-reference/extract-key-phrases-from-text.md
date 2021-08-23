---
title: "ML Studio (classic): Extract Key Phrases from Text - Azure"
description: Learn how to extract key phrases with the Extract Key Phrases from Text module.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Extract Key Phrases from Text

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Extracts key phrases from given text*  
  
 Category: [Text Analytics](text-analytics.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article explains how to use the **Extract Key Phrases from Text** module in Machine Learning Studio (classic), to pre-process a text column. Given a column of natural language text, the module extracts one or more meaningful phrases. A phrase might be a single word, a compound noun, or a modifier plus a noun.
 
This module is a wrapper for natural language processing APIs for key-phrase extraction. The phrases are analyzed as potentially meaningful in the context of the sentence for various reasons:

+ The phrase captures the topic of the sentence.
+ The phrase contains a combination of modifier and noun that indicates sentiment.
 
For example, assume the sentence analyzed is: "It was a wonderful hotel to stay at, with unique decor and friendly staff." 
 
The **Extract Key Phrases from Text** module might return these key phrases:
  
- wonderful hotel
- friendly staff
- unique decor

## How to configure Extract Key Phrases from Text

To extract key phrases, you must connect a dataset that has a column of text.  
  
1. Add the **Extract Key Phrases from Text** module to your experiment in Machine Learning Studio (classic). Then, connect a dataset that has at least one full-text column.  
  
2. Use the Column Selector to select a column of type string, from which to extract key phrases.

3. For **Language**, select a language to use when analyzing phrases. If you specify a language, only phrases in the target language will be output.

4. If the text column contains phrases in multiple languages, choose the option, **Language identified in columns**. A new column selector is displayed that lets you select a column in your data set that contains a language identifier. The language identifier can either be the language name or the Iso6391 culture identifier. For example, either "English" or "en" are acceptable.

    > [!TIP] 
    > Before running **Extract Key Phrases from Text**, use the [Detect Languages](detect-languages.md) module to identify the language in each row and generate the identifier for you.
    > An error is raised if the language identifier column contains any languages not supported by **Extract Key Phrases from Text**. 

### Results

The output of the module is a dataset containing a column of comma-separated key phrases. 

For example, the following example results are for an input dataset containing reviews in multiple languages: 

|Key Phrases|
|-----|
|novel,nuclear submarine,good book,adventure story,avalanche of events,good characters|
|primer misterio,personajes,fan,aventura,isla|

+ All output phrases are contained in a single column; no other columns are passed through, and an identifier is not added. However, if you want to align the output phrases with the source text, you can recombine the output phrases with the input by using the [Add Columns](add-columns.md) module.

+ The output of key-phrase extraction does not flag the language of individual phrases.

+ If a language is included that is not supported by the **Extract Key Phrases** module, an error is raised (0039). To avoid errors, be sure to filter out input text that has an incompatible language identifier. 

    If there are very few rows of other languages, you can also avoid the error by omitting the language identifier, and analyzing all text using a single language selection. However, when you do so, results are very poor, because entire sentences in the other languages might be output as a single key phrase.

## Examples

The following example demonstrates how to use this module to extract key phrases and then build a word cloud from the phrases: [Extract Key Phrases and Show Word Cloud](https://gallery.azure.ai/Experiment/Extract-Key-Phrases-and-Show-Word-Cloud-1)

See the [Azure AI Gallery](https://gallery.azure.ai/) for more examples of text processing using Machine Learning.
  
## Technical notes

This module currently supports the following languages:

+ Dutch
+ English 
+ French 
+ German
+ Italian
+ Spanish   

For additional languages, consider using the [Text Analytics API](/azure/cognitive-services/text-analytics/) in Azure Cognitive Services. For more information, see [How to extract key phrases in Text Analytics](/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-keyword-extraction)
  
##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset |[Data Table](data-table.md) |The table containing the text to be processed.|  
  
##  Module parameters  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Culture-language column|ColumnSelection||language:Column contains language||Name or one-based index of the column containing the culture-language information|  
|Text column|ColumnSelection||Required||Name or one-based index of the text column.|  
|Language|T_Language|English, Spanish, French, Dutch, German, Italian, Column contains language|Required|English|Select the language of the text to be processed.|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|The extracted key phrases|  
  
##  Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0010](errors/error-0010.md)|Exception occurs if input datasets have column names that should match but do not.|  
|[Error 0016](errors/error-0016.md)|Exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0008](errors/error-0008.md)|Exception occurs if parameter is not in range.|

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also  

 [Text Analytics](text-analytics.md)   
 [A-Z Module List](a-z-module-list.md)   
