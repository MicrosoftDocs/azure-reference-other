---
title: "ML Studio (classic): Extract N-Gram Features from Text - Azure"
description: Learn how to use the Extract N-Gram Features from Text module to *featurize* text, and extract only the most important pieces of information from long text strings.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs

---
# Extract N-Gram Features from Text
*Creates N-Gram dictionary features and does feature selection on them*  

Category: [Text Analytics](text-analytics.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article explains how to use the **Extract N-Gram Features from Text** module in Machine Learning Studio (classic), to *featurize* text, and extract only the most important pieces of information from long text strings.
  
The module works by creating a dictionary of n-grams from a column of free text that you specify as input. The module applies various information metrics to the n-gram list to reduce data dimensionality and identify the n-grams that have the most information value.
   
If you have already created a vocabulary of n-grams, you can update its statistics, or merge in new terms, using a weighting algorithm of your choice. 
 
Because this module supports featurization from n-grams, it can also be used when scoring.

## How to configure Extract N-Gram Features from Text

Those module supports the following scenarios for creating, updating, or applying an n-gram dictionary:
  
+ You are developing a new model using a column of free text column and want to extract text features based purely on the input data. [See instructions.](#bkmk_create)
  
+ You have an existing set of text features, and want to update the weights by processing new text inputs. [See instructions.](#bkmk_update) 
  
+ You are generating scores from a predictive model and need to generate and use text inputs with an n-gram dictionary as part of the scoring process. [See instructions.](#bkmk_score)

You could use the [example experiment](https://gallery.azure.ai/Experiment/Predict-Book-Reviews-1) for reference.

### <a name="bkmk_create"></a> Create a new n-gram dictionary from a text column

1.  Add the **Extract N-Gram Features from Text** module to your experiment and connect the dataset that has the text you want to process.
  
2.  For **Text column**, choose a column of type **string** that contains the text you want to extract. 

    By default, the module selects all string columns. However, because the result are verbose, you might need to process a single column at a time.

3. For **Vocabulary mode**, select **Create** to indicate that you are creating a new list of n-gram features. 

    For information about how to update an existing set of n-gram features, see [this section](#bkmk_update).

4. For **N-Grams size**, type a number that indicates the _maximum_ size of the n-grams to extract and store. 

    For example, if you type `3`, unigrams, bigrams, and trigrams will be created.
  
5. For **K-Skip size**, type the maximum number of characters that can be different when identifying variants of n-grams. If the value of _k_ is set to 0, n-grams can be created only from a unique, contiguous sequence of characters. 
  
    For example, assume that your dictionary contains  the unigram "computer". A _k_ value of 0 would mean that "computer" is the only valid unigram. If you increase the value of _k_ to 1, you can skip over one intervening character, which lets you find more similar sequences. A skip-gram with a _k_ value of 1 would differ by one character from the 0-_k_ unigram. Thus, the skip-grams "conputer" and "compuuter" would both be considered part of the same dictionary entry as "computer". Setting the _k_ value to 2 would match even more dissimilar words.
  
    For more information about how skip-grams are used in text analytics, see this paper: [Candidate Generation and Feature Engineering for Supervised Lexical Normalization](https://www.aclweb.org/anthology/W15-4313)  
  
6. The option, **Weighting function**, is required only if you merge or update vocabularies. It specifies how terms in the two vocabularies and their scores should be weighted against each other.
  
7. For **Minimum word length**, type the minimum word length of strings that can be analyzed. 

    For example, assume the minimum word length was set to 3 (the default value), and you had one input that had a single word, and another that had some short text like "nice place". Both rows would be ignored. 
    
8. For **Maximum word length**, type the maximum number of letters that can be used in any _single word_ in an n-gram.
  
    By default, up to 25 characters per word or token are allowed. Words longer than that are removed, on the assumption that they are possibly sequences of arbitrary characters rather than actual lexical items.
  
9. For **Minimum n-gram document absolute frequency**, type a number that indicates the minimum occurrences required for any single word or token to be included in the n-gram dictionary.
  
    For example, if you use the default value of 5, any n-gram or skip-gram must appear at least five times in the corpus to be included in the n-gram dictionary.
  
10. For **Maximum n-gram document ratio**, type a number that represents this ratio: the number of rows that contain a particular n-gram, over the number of rows in the overall corpus.

    For example, a ratio of 1 would indicate that, even if a specific n-gram is present in every row, the n-gram can be added to the n-gram dictionary. More typically, a word that occurs in every row would be considered a noise word and would be removed. To filter out domain-dependent noise words, try reducing this ratio.
  
    > [!IMPORTANT]
    > The rate of occurrence of particular words is not uniform, but varies from document to document. For example, if you are analyzing customer comments about a specific product, the product name might be very high frequency and close to a noise word, but be a significant term in other contexts.  
  
11.  Select the option, **Detect out-of-vocabulary rows**, if you want to generate an indicator for any rows that contain words not in the n-gram vocabulary, which are called "out of vocabulary" (OOV) words.
  
     All lexicons are finite; therefore, your text corpus is almost guaranteed to include words that are not in the lexicon or n-gram dictionary. However, such words can have various effects on language models, including higher error rates compared to in-vocabulary (IV) words. Depending on your domain, these OOV words might represent important content words. 

     By identifying rows that contains these words, you can either compensate for the effects of these terms, or handle the terms and related rows separately.
  
12.  Select the option, **Mark begin-of-sentence**, to add a special character sequence that indicates the beginning of a sentence in your n-gram dictionary. Prefixing n-grams that start a sentence with a special character is common in text analysis and can be useful in analyzing discourse boundaries.
  
     Azure ML Studio (classic) inserts the symbol `|||`. You cannot specify a custom character.

13. Select the option **Normalize n-gram feature vectors** if you want to normalize the feature vectors. When you do this, each n-gram feature vector is divided by its L2 norm.
  
    Normalization is used by default.  
  
14. Set **Use filter-based feature selection** to **True** if you want to enable additional options for managing the size of your text feature vector.

    + Feature selection can be helpful in reducing the dimensionality of your n-grams.  
    + When you do not apply filter selection, all possible n-grams are created, increasing coverage at the expense of making the dictionary longer and possibly including many infrequent terms. 
    + In a small corpus, using feature selection can greatly reduce the number of terms that are created.
    + For more information, see [Filter Based Feature Selection](filter-based-feature-selection.md).  
  
    If you are using feature selection, you must select a method from the **Feature scoring method** drop-down list:
  
    + **PearsonCorrelation**: Computes Pearson's correlation based on the label column value and the text vector.
    + **MutualInformation**: Computes a mutual information score, based on the label column value and the text vector.
    + **KendallCorrelation**: Computes Kendall's correlation, based on the label column value and the text vector.
    + **SpearmanCorrelation**: Computes the Spearman correlation, based on the label column value and the text vector.
    + **ChiSquared**: Uses the chi-squared method to calculate the correlation between the label column value and the text vector.
    + **FisherScore**: Computes the Fisher score for the label column value and the text vector.
    + **Count-based feature selection**:  Creates new features based on the counts of values. A label column is not required with this method.
  
    Depending on the method you choose, set one of the following options:
    
    + **Number of desired features**: Required if you use any feature selection method other than count-based feature selection.

        In the process of feature selection, all n-grams get a feature score, and n-grams are ranked by score. The value you set here determines how many of the most highly-ranked features are output. N-grams with lower feature scores are discarded.

    + **Minimum number of non-zero elements**: Required if you use count-based feature selection. 
    
        Type a whole number that represents the minimum number of total instances required to tabulate counts for a potential feature.
  
15. Run the experiment.

    See [this section](#bkmk_results) for an explanation of the results and their format.

### <a name="bkmk_update"></a> Update an existing n-gram dictionary, or merge dictionaries

1.  Add the **Extract N-Gram Features from Text** module to your experiment and connect the dataset that has the text you want to process to the **Dataset** port.
  
2.  For **Text column**, choose the text column that contains the text you want to featurize. By default, the module selects all columns of type string. For best results, process a single column at a time.

3. Add the saved dataset containing a previously generated n-gram dictionary, and connect it to the **Input vocabulary** port. You can also connect the **Result vocabulary** output of an upstream instance of the **Extract N-Gram Features from Text** module.

    To merge or update vocabulary, the schema of the input vocabulary must exactly match the expected format. Do not remove any columns from or add any columns to the input vocabulary.

4. For **Vocabulary mode**, select one of the following update options from the drop-down list:
    
   + **ReadOnly**: Represents the input corpus in terms of the input vocabulary.  That is to say, rather than computing term frequencies from the new text dataset (on the left input), the n-gram weights from the input vocabulary are applied as is.
  
        > [!TIP]
        > Use this option when scoring a text classifier.
  
    + **Update**: Creates a new n-gram vocabulary from the input corpus, and merges it with the input vocabulary. In other words, you can add new entries to the created vocabulary from the input vocabulary, or you can update existing entries.
  
        > [!TIP]
        > Use this option for incremental updates of vocabulary with incoming data batches.
  
    + **Merge**: Generates a new n-gram vocabulary from the input corpus.
  
         This option is useful if you are passing a background vocabulary as input to the module and want to reduce the weight of stop words. In other words, each entry that has a high document frequency score in the background vocabulary will be assigned a lower inverse document frequency score in the created vocabulary.
  
         > [!TIP]
        > Use this option if you don't want to add new entries to the created vocabulary from the input, and only want to adjust the scores of existing entries.

9. The option, **Choose the weighting function**, is required if you merge or update vocabularies. The weighting function specifies how the DF and IDF scores in the two vocabularies should be weighted against each other:
  
    + **Binary Weight**: Assigns a binary presence value to the extracted n-grams.  In other words, the value for each n-gram is 1 when it exists in the given document, and 0 otherwise.  
    + **TF Weight**: Assigns a term-frequency score (**TF**) to the extracted n-grams.  The value for each n-gram is its occurrence frequency in the given document.  
    + **IDF Weight**: Assigns an inverse document frequency score (**IDF**) to the extracted n-grams.  The value for each n-gram is the log of corpus size divided by its occurrence frequency in the whole corpus. That is: `IDF = log of corpus_size / document_frequency` 
    +  **TF-IDF Weight**: Assigns an term frequency/inverse document frequency score (**TF/IDF**) to the extracted n-grams. The value for each n-gram is its TF score multiplied by its IDF score.  
    + **Graph Weight**: Assigns score to the extracted n-grams based on the TextRank graph ranking. TextRank is a graph-based ranking model for text processing. Graph-based ranking algorithms are essentially a way of deciding importance  based on global information. For more information, see [TextRank: Bringing Order into Texts](https://web.eecs.umich.edu/~mihalcea/papers/mihalcea.emnlp04.pdf) by Rada Mihalcea and Paul Tarau.

10. For all other options, see the property descriptions in the [preceding section](#bkmk_create).

11. Run the experiment.

    See [this section](#bkmk_results) for an explanation of the results and their format.

### <a name="bkmk_score"></a> Score or publish a model that uses n-grams  
  
1.  Copy the **Extract N-Gram Features from Text** module from the training dataflow to the scoring dataflow.  
  
2.  Connect the **Result Vocabulary** output from the training dataflow to the **Input Vocabulary** on the scoring dataflow.  
  
3.  In the scoring workflow, modify the **Extract N-Gram Features from Text** module and make these changes, leaving all else the same:  
  
    -   Set the **Vocabulary mode** parameter to **ReadOnly**.
  
    -   Change the option **Use filter based feature selection** to `False`.
  
4.  To publish the  experiment, save the **Result Vocabulary** as dataset.
  
     Then, connect the saved dataset to the **Extract N-Gram Features from Text** module in your scoring graph.  

## <a name="bkmk_results"></a> Results

The **Extract N-Gram Features from Text** module creates two types of output: 

+ **Results dataset**: A summary of the analyzed text together with the n-grams that were extracted. Columns that you did _not_ select in the **Text column** option are passed through to the output. For each column of text that you analyze, the module generates these columns:

    - **NgramsString**: A string containing all unique n-grams. 
    - **NumUniqueNgrams**:  The count of n-grams extracted using the specified properties.
    - **Sparse matrix of n-gram occurrences**: The module generates a column for each n-gram found in the total corpus and adds a score in each column to indicate the weight of the n-gram for that row. 

+ **Result vocabulary**: The vocabulary contains the actual n-gram dictionary, together with the term frequency scores that are generated as part of the analysis.  You can save the dataset for re-use with a different set of inputs, or for later update. You can also update the scores, or reuse the vocabulary for modeling and scoring.

### Sample results

To illustrate how you can use the results, the following short example uses the Amazon Book Review dataset available in Studio (classic). The dataaset was filtered to show only reviews with a score of 4 or 5, and reviews with a string length of under 300 characters. 

From this dataset, a short review was selected, containing only 92 words. Here the author's name has been replaced with `Xxx` and the book title replaced with `Yyy`: 

`"Xxx at his best ! Yyy is one of Xxx's best yet! I highly recommend this novel."`
  
#### Results dataset for sample review text

For this sample, the module generated these columns:

+ **NumUniqueNgrams**:  For this 92 word review, using the default settings, 11 n-grams were extracted from the sample review. 
    
    When the n-gram length was increased to 3 and the skip-gram value set to 1, 15 n-grams were found. 
    
    When feature selection was applied to the default, no n-grams were extracted. 

+ **NgramsString**:With the default settings, these n-grams were returned:  ["his","best","one","highly","recommend","this","novel","his_best","highly_recommend","recommend_this","this_novel"]

    With an n-gram length of 3 and skip-gram value of 1, these n-grams were returned: ["his","best","one","highly","recommend","this","novel","his_best","highly_recommend","recommend_this","this_novel","best_one","one_best","highly_this","highly_recommend_this"]

+ **Sparse matrix of n-gram occurrences**

    For this particular review, the results included these columns:

    | ReviewText.[manages]| ReviewText.[and\_highly]| ReviewText.[highly] |ReviewText.[highly\_recommend] |
    |----|----|----|----|
    |0|0|0.301511|0.301511|

    > [!TIP]
    > If you have trouble viewing a particular column, attach the [Select Columns in Dataset](select-columns-in-dataset.md) module to the output, and then use the search function to filter columns by name.

#### Result vocabulary for sample review text

The vocabulary contains the actual n-gram dictionary, together with the term frequency scores that are generated as part of the analysis. You can save the dataset for re-use with a different set of inputs, or for later update. The scores **DF** and **IDF** are generated regardless of other options. When you combine vocabularies, these stored values are used as input to the weighting function you choose.

+ **Id**: An identifier generated for each unique n-gram.
+ **Ngram**: The n-gram. Spaces or other word separators are replaced by the underscore character.
+ **DF**: The term frequency score for the n-gram in the original corpus.
+ **IDF**: The inverse document frequency score for the n-gram in the original corpus.

It is possible to manually update this dataset; however, be careful, as you can introduce errors. For example:

+ An error is raised if the module finds duplicate rows with the same key in the input vocabulary. Be sure that no two rows in the vocabulary have the same word.
+ The input schema of the vocabulary datasets must match exactly, including column names and column types. 
+ The **ID** column and **DF** score column must be of the integer type. 
+ The **IDF** column must be of type FLOAT (floating point).

##  Technical notes

We recommend that you experiment with different ranges of values for n-gram length, the number of skip-grams, and use of feature selection to determine the dimensionality of your text corpus and the optimum feature ratio.

For more information about n-grams and skip-grams, see these resources:
  
 + [Automatic Evaluation of Summaries Using N-gram Co-Occurrence Statistics](https://research.microsoft.com/en-us/um/people/cyl/download/papers/NAACL2003.pdf)  
  
##  Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input data|  
|Input vocabulary|[Data Table](data-table.md)|Input vocabulary|  
  
##  Module parameters  

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Minimum number of non-zero elements|Integer|>=1|Applies only when using the following method:<br /><br /> Count Based|1|Specify the number of features to output (for CountBased method)|  
|Text column|Column Selection||Required|StringFeature|Name or one-based index of text column|  
|Vocabulary mode|Vocabulary Mode|Create<br /><br /> ReadOnly<br /><br /> Update<br /><br /> Merge|Required|Create|Specify how the n-gram vocabulary should be created from the corpus|  
|N-Grams size|Integer|>=1|Required|1|Indicate the maximum size of n-grams to create|  
|K-Skip size|Integer|>=0|Required|0|Indicate the k-skip size|  
|Weighting function|Weighting Function|Binary Weight<br /><br /> TF Weight<br /><br /> IDF Weight<br /><br /> TF-IDF Weight<br /><br /> Graph Weight|Required|Binary Weight|Choose the weighting function to apply to each n-gram value|  
|Minimum word length|Integer|>=1|Required|3|Specify the minimum length of words to include in n-grams|  
|Maximum word length|Integer|>=2|Required|25|Specify the maximum length of words to include in n-grams|  
|Minimum n-gram document absolute frequency|Float|>=1.0|Required|5.0|Minimum n-gram document absolute frequency|  
|Maximum n-gram document ratio|Float|>=0.0001|Required|1.0|Maximum n-gram document ratio|  
|Detect out-of-vocabulary rows|Boolean||Required|true|Detect rows that have words not in the n-gram vocabulary (OOV)|  
|Mark begin-of-sentence|Boolean||Required|false|Indicate whether a begin-sentence mark should be added to n-grams|  
|Normalize n-gram feature vectors|Boolean||Required||Normalize n-gram feature vectors.  If true, then the n-gram feature vector is divided by its L2 norm.|  
|Use filter-based feature selection|True False Type|True<br /><br /> False|Required|True|Use filter-based feature selection to reduce dimensionality|  
|Feature scoring method|Scoring Method|Pearson Correlation<br /><br /> Mutual Information<br /><br /> Kendall Correlation<br /><br /> Spearman Correlation<br /><br /> Chi Squared<br /><br /> Fisher Score<br /><br /> Count Based|Applies only when the option **Use filter-based feature selection** is True|Fisher Score|Choose the method to use for scoring|  
|Target column|Column Selection||Applies when using one of the following methods:<br /><br /> Pearson Correlation<br /><br /> Mutual Information<br /><br /> Kendall Correlation<br /><br /> Spearman Correlation<br /><br /> Chi Squared<br /><br /> Fisher Score||Specify the target column|  
|Number of desired features|Integer|>=1|Applies when using one of the following methods:<br /><br /> Pearson Correlation<br /><br /> Mutual Information<br /><br /> Kendall Correlation<br /><br /> Spearman Correlation<br /><br /> Chi Squared<br /><br /> Fisher Score|1|Specify the number of features to output in results|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Extracted features|  
|Result vocabulary|[Data Table](data-table.md)|Result vocabulary|  
  
## See also
 [Text Analytics](text-analytics.md)   
 [A-Z List of Machine Learning Modules](a-z-module-list.md)
