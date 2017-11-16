---
title: "Extract Key Phrases from Text | Microsoft Docs"
ms.custom: ""
ms.date: 02/23/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c08afa36-58ac-4a2b-bc59-f2a16bb4c2f3
caps.latest.revision: 10
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Extract Key Phrases from Text
*Extracts key phrases from given text*  
  
 Category: [Text Analytics](text-analytics.md)

  
## Module Overview  

 Use the **Extract Key Phrases from Text** module to pre-process a text column and extract meaningful phrases. A phrase can be either a single meaningful word, or a compound.  The extracted phrase or phrases are potentially meaningful in the context of the sentence for various reasons:
 + The phrase captures the topic of the sentence
 + The phrase contains a combination of modifier and noun that indicates sentiment
 
 For example, assume the sentence analyzed is: "It was a wonderful hotel to stay at, with unique decor and friendly staff." 
 
The **Extract Key Phrases from Text** module might return these key phrases:
  
- wonderful hotel
- friendly staff
- unique decor

## How to Configure Key-Phrase Extraction  

To extract key phrases, you must connect a dataset that has a column of text.  
  
1. Add the **Extract Key Phrases from Text** module to your experiment, and connect a dataset that has at least one full-text column.  
  
2. Use the Column Selector to select the column from which to extract key phrases.

3. For **Language**, select a language to use when analyzing phrases. If you specify the language, only phrases in the target language will be output.

4. If the text column contains phrases in multiple languages, choose the option, **Language identified in columns**. A new column selector is displayed that lets you select a column in your data set that contains a language identifier. The language identifier can either be the language name or the Iso6391 culture identifier. For example, either "English" or "en" are acceptable.

    > [!TIP] 
    > Before running **Extract Key Phrases from Text**, use the [Detect Languages](detect-languages.md) module to identify the language in each row and generate the identifier for you.

  
## Examples  

The following example demonstrates how to use this module to extract key phrases and then build a word cloud from them: [Extract Key Phrases and Show Word Cloud](https://gallery.cortanaintelligence.com/Experiment/Extract-Key-Phrases-and-Show-Word-Cloud-1)

Please see the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) for more examples of text processing using Azure Machine Learning.   
  
## Technical Notes  

This module currently supports the following languages:
+ Dutch
+ English 
+ French 
+ German
+ Italian
+ Spanish   
  
Support for additional languages will be added in future.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset |[Data Table](data-table.md) |The table containing the text to be processed.|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Culture-language column|ColumnSelection||language:Column contains language||Name or one-based index of the column containing the culture-language information|  
|Text column|ColumnSelection||Required||Name or one-based index of the text column.|  
|Language|T_Language|English, Spanish, French, Dutch, German, Italian, Column contains language|Required|English|Select the language of the text to be processed.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|The extracted key phrases|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0010](errors/error-0010.md)|Exception occurs if input datasets have column names that should match but do not.|  
|[Error 0016](errors/error-0016.md)|Exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0008](errors/error-0008.md)|Exception occurs if parameter is not in range.|

## See Also  

 [Text Analytics](text-analytics.md)   
 [A-Z Module List](a-z-module-list.md)   
