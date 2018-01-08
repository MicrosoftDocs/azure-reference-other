---
title: "Preprocess Text | Microsoft Docs"
ms.custom: ""
ms.date: 05/31/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bf9e794a-9e2b-4662-902a-0e73b255c135
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Preprocess Text
*Performs cleaning operations on text*  
  
 Category: [Text Analytics](text-analytics.md)  
  
## Module Overview  

You can use the **Preprocess Text** module to clean and simplify text. By preprocessing the text, you can more easily create meaningful features from text. For example, the **Preprocess Text** module supports these common operations on text:  
  
-   Removal of stop-words  
  
-   Definition of regular expressions, to let you search for and replace specific target strings  
  
-   Lemmatization, which converts multiple related words to a single canonical form  
  
-   Filtering on specific parts of speech  
  
-   Case normalization  
  
-   Removal of certain classes of characters, such as numbers, special characters, and sequences of repeated characters such as "aaaa"  
  
-   Identification and removal of emails and URLs  
  
 You can choose which cleaning options to use, and optionally specify a custom list of stop-words.  
  
 The module currently supports  six languages: English, Spanish, French, Dutch, German and Italian.  
  
## How to Configure Text Preprocessing  
  
1.  Add the **Preprocess Text** module to your experiment, and connect a dataset that has at least one column containing text.  
  
2.  If the text you are preprocessing is all in the same language, select the language from the **Language** dropdown list, and the text will be proprocessed using linguistic rules specific to the selected language.  

     + Dutch
     + English
     + French
     + German
     + Italian
     + Spanish

3. If you need to preprocess text in multiple languages, choose the **Column contains language** option. 

   You can then use the **Culture-language column** field to pick a column that specifies the language to use, based on an identifier such as "English" or "en". The module will then check the language identifier for each row in the dataset, and use the appropriate linguistic resources to process the text.
   
   If the dataset does not contain such a column, use the **Detect Language** module to analyze the language and generate an identifier.
   
     > [!TIP]
     > 
     >  An error will be raised if an unsupported language is included. See the [Technical Notes](#bkmk_TechnicalNotes) section for more information. 

4.  Use the option, **Remove by part of speech**, if you want to apply part-of-speech analysis to identify classes of words and remove certain classes of words.  If you set this option to True, you can choose which word classes to remove.
  
    -   **Remove nouns**. Select this option to remove nouns.  
  
    -   **Remove adjectives**. Select this option to remove adjectives.  
  
    -   **Remove verbs**. Select this option to remove verbs.  
  
     For more information about the part-of-speech identification method used, see [Technical Notes](#bkmk_TechnicalNotes).  

5.  In **Text column to clean**, choose the column or columns that you want to preprocess.  
    
7.  Select the **Remove stop words** option if you want to apply a predefined stopword list to the text column before any other processes are performed.  
  
     Stopword lists are language dependent and customizable; for more information, see [Technical Notes](#bkmk_TechnicalNotes).  

6.  Select the **Lemmatization** option if you want words to be represented in their canonical form. This option is useful for reducing the number of unique occurrences of otherwise similar text tokens.  
  
     The lemmatization process is language-dependent; see the [Technical Notes](#bkmk_TechnicalNotes) section for details.  

4.  Select the **Detect sentences** option to mark sentence boundaries with a specific series of characters.  
  
     This module uses three pipe characters ( &#124;&#124;&#124; ) to represent the sentence terminator. 

8.  To perform custom find-and-replace operations, you can define a target string and its replacement string, using regular expressions.  
  
    - Use the **Custom regular expression** field to define the text you are searching for.  
  
    - Use the **Custom replacement string** field to define a single replacement to use for all found instances.  
  
9. Select the option **Normalize case to lowercase** if you want to convert ASCII uppercase characters to their lowercase forms. 

    If characters are not normalized, the same word in uppercase and lowercase letters would be considered two different words. 

11. Optionally, you can specify types of characters or character sequences to remove from the processed text.  
  
    -   **Remove numbers**. If you select this option, all numeric characters for the specified language are removed.  
  
         Note that the identification of what constitutes a number is domain dependent and language dependent. If numeric characters are an integral part of a known word, the number might not be removed.  
  
    -   **Remove special characters**. If you select this option, any non-alphanumeric special characters will be replaced with the pipe (&#124;) character.  
  
         The list of special characters is defined in the [Technical Notes](#bkmk_TechnicalNotes) section.  
  
    -   **Remove duplicate characters**.  If you select this option, any sequences that repeat the characters will be removed. For example, "aaaaa" would be removed.  
  
    -   **Remove email addresses**. If you select this option, any sequence of the format \<string>@\<string> will be removed.  
  
    -   **Remove URLs**.  If you select this option, any sequence including the following formats will be removed:  
  
        -   http and https  
  
        -   ftp  
  
        -   www prefix  

12. The option **Expand verb contractions** is applicable only to languages that use verb contractions; currently, English only. For example, by selecting this option, you could replace the phrase *"wouldn't stay there"* with *"would not stay there"*.

13. Use the option **Normalize backslashes to slashes** to map all instances of "\\" to "/". 

14. Select the option **Split tokens on special characters** if you want to break words on characters such as &, -, and so forth. For example, if you select this option, _MS-WORD_ would be separated into two tokens, _MS_ and _WORD_.

## Examples  

The following examples in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) illustrate the use of the **Preprocess Text** module:  
  
-   [How to use a custom stopword list](http://gallery.cortanaintelligence.com/Experiment/How-to-remove-custom-stopwords-1)  
  
-   [How to modify the default stopword list](http://gallery.cortanaintelligence.com/Experiment/How-to-modify-default-stopword-list-1)  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical Notes  

This section provides more information about the underlying text pre-processing technology, and how to specify custom text resources.  
 
  
### Supported Languages  

Currently Azure Machine Learning supports text preprocessing in these languages:  
  
-   Dutch  
  
-   English  
  
-   French  
  
-   German  
  
-   Italian  
  
-   Spanish  
  
 Additional languages are planned. See the [Microsoft Machine Learning blog](https://blogs.technet.microsoft.com/machinelearning/) for announcements.  
  
### Lemmatization  

Lemmatization is the process of identifying a single canonical form to represent multiple word tokens.  
  
The natural language processing libraries included in Azure Machine Learning combine the following multiple linguistic operations to provide lemmatization:  
  
- **Sentence separation**. In free text used for sentiment analysis and other text analytics, sentences are frequently run-on or punctuation might be missing. Input texts might constitute an arbitrarily long chunk of text, ranging from a tweet or fragment to a complete paragraph, or even document.  
  
     The natural language tools used by Azure ML perform sentence separation as part of the underlying lexical analysis. However, sentences are not separated in the output. Optionally, you can specify that a sentence boundary be marked to aid in other text processing and analysis.  
  
- **Tokenization**. The rules that determine the boundaries of words are language-dependent and can be complex even in languages that use spaces between words. Some languages (such as Chinese or Japanese) do not use any white space between words, and separation of words requires morphological analysis. Therefore, the tokenization methods and rules used in this module will provide different results from language to language. These tokenization rules are determined by text analysis libraries provided by Microsoft Research for each supported language, and cannot be customized.
  
  
- **Part-of-speech identification**. Given a sequence of words, many words will be ambiguous and will have multiple options for part of speech. Parts of speech are also very different depending on the morphology of different languages.  
  
     In Azure Machine Learning, a disambiguation model is used to choose the **single most likely part of speech**, given the current sentence context.  The part-of-speech information is used to help filter words used as features and aid in key-phrase extraction. However, the output of this module does not explicitly include POS tags and therefore cannot be used to generate POS-tagged text.  
  
- **Generating dictionary form**.  A word may have multiple *lemmas*, or dictionary forms, each coming from a different analysis. For instance, the English word building has two possible lemmas: *building* if the word is a noun ("the tall building"), or *build* if the word is a verb ("they are building a house"). In Azure Machine Learning, only the *single most probable* dictionary form is generated.  
   
 **Example**
 
 | Source| Lemmatized with case conversion|
 |------|------|
 |He is swimming| he i swim |
 | He is going for a swim| he i go for a swim|
 | Swimming is good for building muscle|swim be good for build muscle |
 | He is building a building|he i build a build|
 |We are all building buildings|we be all build building|
 
> [!NOTE]
>  The language models used to generate dictionary form have been trained and tested against a variety of general purpose and technical texts, and are used in many other  Microsoft products that require natural language APIs. However, natural language is inherently ambiguous and 100% accuracy on all vocabulary is not feasible.  For example, lemmatization can be affected by other parts of speech, or by the way that the sentence is parsed. 
> 
> If you need to perform additional pre-processing, or perform linguistic analysis using a specialized or domain-dependent vocabulary, we recommend that you use customizable NLP tools, such as those available in Python and R. 
  
### Special Characters  

Special characters are defined as single characters that cannot be identified as any other part of speech, and can include punctuation: colons, semi-colons, and so forth.  
  
### Stopwords  

A stopword is a word that is often removed from indexes because it is  common and provides little value for information retrieval, even though it might be linguistically meaningful. For example, many languages make a semantic distinction between definite and indefinite articles ("the building" vs "a building"), but for machine learning and information retrieval, the information is often unreliable, not available, or not relevant. Hence it is common practice to discard these words.  
  
 The Azure Machine Learning environment includes  lists of the most common stopwords for each of the supported languages.  
  
|Language|Number of stopwords|Examples|  
|-|-|-|  
|Dutch|49|aan, af, al|  
|English|312|a, about, above|  
|French|154|de, des, d', la|  
|German|602|a, ab, aber|  
|Italian|135|a, adesso, ai|  
|Spanish|368|ésa, ésta, éste|  
  
 For your convenience, a zipped file containing the default stopwords for all current languages has been made available on Azure: [Stopwords.zip](http://az754797.vo.msecnd.net/docs/Stopwords.zip).  
  
### How to Modify the Stopword List  
  
 We expect that many users will want to create their own stopword lists, or change the terms included in the default list. The following experiment in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) demonstrates how you can customize a stop word list.  
  
-   [How to modify the default stopword list](http://gallery.cortanaintelligence.com/Experiment/How-to-modify-default-stopword-list-1)  
  
 If you modify the list, or create your own stop word list, observe these requirements:  
  
-   The file must contain a single text column.  
  
     You might get the following error if an additional column is present:  
  
     Preprocess Text Error Column selection pattern "Text column to clean" is expected to provide 1 column(s) selected in input dataset, but 2 column(s) is/are actually provided. ( Error 0022 )  
  
     This can happen as a result of spaces, tabs, or hidden columns present in the file from which the stopword list was originally imported. Depending on how the file was prepared, tabs or commas included in text can also cause multiple columns to be created. If you get this error, you can review the source file, or use the [Select Columns in Dataset](select-columns-in-dataset.md) module to choose a single column to pass to the [Preprocess Text](preprocess-text.md) module.  
  
-   Each row can contain only one word. For the purposes of parsing the file, words are determined by insertion of spaces.  
  
-   The stopword list cannot be empty.  
  
## Order of Operations  

In this module, you can apply multiple operations to text. However, the order in which these operations are applied cannot be changed. This can affect the expected results.  
  
 For example, if you apply lemmatization to text, and also use stopword removal, all the words are converted to their lemma forms before the stopword list is applied. Therefore, if your text includes a word that is not in the stopword list, but its lemma is in the stopword list, the word would be removed.  
  
 Be sure to test target terms in advance to guarantee the correct results.  

## Unsupported Languages

If your text column includes languages not supported by Azure Machine Learning, we recommend that you use only those options that do not require language-dependent processing. This can help avoid strange results.

Also, if you use the option **Column contains language**, you must ensure that no unsupported languages are included in the text that is processed. If an unsupported language or its identifier is present in the dataset, the following run-time error will be generated:

*Preprocess Text Error (0039): Please specify a supported language.*         

To avoid failing the entire experiment because an unsupported language was detected, you can use the [Split Data](split-data.md) module, and specify a regular expression to divide the dataset into supported and unsupported languages. For example, the following regular expression splits the dataset based on the detected language for the column _Sentence_:

~~~~
\"Sentence Language" Dutch|English|French|Italian|Spanish
~~~~  

If you have a column that contains the language identifier, or if you have generated such a column, you can use a regular expression such as the following, to filter on the identifier column:

~~~~
\"Sentence Iso6391 Name" nl|en|fr|it|es
~~~~  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input data|  
|Stop words|[Data Table](data-table.md)|Optional custom list of stop words to remove|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Remove URLs|Boolean|True<br /><br /> False|Required|true|Remove URLs|  
|Language|Language|English<br /><br /> Spanish<br /><br /> French<br /><br /> Dutch<br /><br /> German<br /><br /> Italian|Required|English|Select the language to preprocess|  
|Text column to clean|Column Selection||Required|StringFeature|Select the text column to clean|  
|Custom regular expression|String||Optional||Specify the custom regular expression|  
|Custom replacement string|String||Optional||Specify the custom replacement string for the custom regular expression|  
|Remove stop words|Boolean||Required|true|Remove stop words|  
|Lemmatization|Boolean||Required|true|Use lemmatization|  
|Remove by part of speech|True False Type|true<br /><br /> false|Required|False|Indicate whether part-of-speech analysis should be used to identify and remove certain word classes|  
|Remove nouns|Boolean||Applies when the **Filter by part of speech** option is selected|true|Remove nouns|  
|Remove adjectives|Boolean||Applies when the **Filter by part of speech** option is selected|true|Remove adjectives|  
|Remove verbs|Boolean||Applies when the **Filter by part of speech** option is selected|true|Remove verbs|  
|Detect sentences|Boolean||Required|true|Detect sentences by adding a sentence terminator \\"&#124;&#124;&#124;\\" that can be used by the n-gram features extractor module|  
|Normalize case to lowercase|Boolean||Required|true|Normalize case to lowercase|  
|Remove numbers|Boolean||Required|true|Remove numbers|  
|Remove special characters|Boolean||Required|true|Remove non-alphanumeric special characters and replace them with \\"&#124;\\" character|  
|Remove duplicate characters|Boolean||Required|true|Remove duplicate characters|  
|Remove email addresses|Boolean||Required|true|Remove email addresses|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Results dataset|  
  
## Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0030](errors/error-0030.md)|an exception occurs in when it is not possible to download a file.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  
  
## See Also  

[Text Analytics](text-analytics.md)   

[A-Z Module List](a-z-module-list.md)