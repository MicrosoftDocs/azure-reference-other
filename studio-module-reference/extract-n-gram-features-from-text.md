---
title: "Extract N-Gram Features from Text | Microsoft Docs"
ms.custom: ""
ms.date: 02/23/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8a662d0-89bb-48c9-8562-9b9589124c4a
caps.latest.revision: 14
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Extract N-Gram Features from Text
*Creates N-Gram dictionary features and does feature selection on them*  

Category: [Text Analytics](text-analytics.md)  
  
## Module Overview  
 You can use the **Extract N-Gram Features from Text** module to *featurize* long text strings,  extracting only the most important pieces of information.  
  
 The module works by creating a dictionary of N-grams from a text column that you specify.  It then applies various information metrics to the n-gram list to reduce data dimensionality and identify the n-grams that have the most information value.  
  
 Multiple options are provided for scoring and weighting N-grams:  
  
-   Binary (term exists or does not exist)  
  
-   Term frequency (TF), inverse document frequency (IDF), and TF*IDF  
  
-   Graph weight  
  
 If you have already created a vocabulary of N-grams, you can still use it; you can also update an existing vocabulary with new N-grams when re-training a module. Because this module supports featurization from n-grams, it can also be used when scoring.   
  
## How to Create an N-Gram Dictionary for Training  

There are several scenarios in which you would build or use an n-gram dictionary:  
  
-   You are training a new model on a text column and want to create a new dictionary based purely on the input corpus.  
  
-   You have already built an n-gram dictionary and want to update the weights by processing new text inputs.  
  
-   You are scoring based on text inputs and want to leverage an n-gram dictionary.  

 
1.  Add the **Extract N-Gram Features from Text** module to your experiment and connect the dataset that has the text you want to process.  
  
2.  If you have a custom vocabulary that you can use to validate input text, connect it to **Input vocabulary**.  
  
     For more information about how to prepare a custom vocabulary, see [Technical Notes](#bkmk_TechnicalNotes).  
  
3.  For **Target column**, select the single column that will be used as the label in the model.  
  
4.  For **Text column**, choose the column that contains the text you want to featurize.  
  
5.  Set the following options that determines how n-grams are created.  
  
    -   **N-Grams size**. Type a value that indicates the maximum size of n-grams to create.  
  
         For example, if you type `3`, unigrams, bigrams, and trigrams will be created.  
  
    -   **K-Skip size**. Type the maximum number of characters that can be different when creating n-grams.  
  
         If the value of k is set to 0, n-grams can be created only from a  unique, contiguous sequence of characters. For example, assume that your dictionary contains  the unigram "computer". A k value of 0 would mean that "computer" is the only valid unigram.  
  
         If you increase the value of k to 1, you can skip over one intervening character, which lets you find more similar sequences. A skip-gram with a  k value of 1 would differ by one character from the 0- k unigram. Thus, the skip-grams "conputer" and "compuuter" can be considered part of the same dictionary entry as "computer". Setting the  k value to 2 would match even more dissimilar words.  
  
         For more information about how skip-grams are used in text analytics, see this paper: [Candidate Generation and Feature Engineering for Supervised Lexical Normalization](http://www.aclweb.org/anthology/W15-4313)  
  
    -   **Minimum word length**. Specify the minimum length of strings that can be included in n-grams.  
  
         For example, with the default value of 3, sequences such as "go to DC" would result in no n-gram being created, whereas a sequence such as "going to the DC area" would result in n-grams using the tokens "going", "the", and "area".  
  
    -   **Maximum word length**. Limit the length of words that can be included in n-grams.  
  
         By default, up to 25 characters per word or token are allowed. Words longer than that are removed, on the assumption that they are possibly sequences of arbitrary characters rather than actual lexical items.  
  
    -   **Minimum n-gram document absolute frequency**. Type a number that indicates the minimum occurrences required for any one word or token to be included in the n-gram dictionary.  
  
         For example, with the default of 5, an n-gram (or skip-gram) must appear at least five times in the corpus to be included in the n-gram dictionary.  
  
    -   **Maximum n-gram document ratio**. Type a number that represents the ratio of the number of rows that contain a particular n-gram over the number of rows in the overall corpus. For example, a ratio of 1 would indicate that the corpus could include a specific n-gram in every single row and the n-gram would still be added to the n-gram dictionary. However, more typically a word that occurs in every single row would be considered a noise word and might be removed. By decreasing the ratio, you can often filter out such domain-dependent noise words.  
  
         it is important to remember that the rate of occurrence of particular words is not uniform, but varies from document to document. For example, if you are analyzing customer comments about a specific product, the product name might be very high frequency and close to a noise word, but be a significant term in other contexts.  
  
6.  Select the option, **Detect out-of-vocabulary rows**, to flag rows that contain words that are not in the n-gram vocabulary.  
  
     All lexicons are finite; therefore, your text corpus is almost guaranteed to include words that are  not in the lexicon or n-gram dictionary. These are called out-of-vocabulary (OOV) words.  
  
     Out-of-vocabulary (OOV) words have various effects on language models, including higher error rates compared to in-vocabulary (IV) words. Depending on your domain, these OOV words might represent important content words. By identifying rows that contains these words, you can compensate for them or handle the rows separately.  
  
7.  Select the  option, **Mark begin-of-sentence**, to add a special character sequence that indicates the beginning of a sentence in your n-gram dictionary.  
  
     The symbol `|||` is inserted. You cannot specify a custom character.  
  
     Prefixing n-grams that start a sentence with a special character is common in text analysis and can be useful in analyzing discourse boundaries.  
  
8.  For **Vocabulary mode**, select an option from the drop-down list, to specify how the n-gram vocabulary should be created from the corpus.  
  
    -   **Create**. Create a completely new n-gram vocabulary from the input corpus.  
  
         *Use this option when training a text classifier.*  
  
    -   **ReadOnly**. Represent the input corpus in terms of the input vocabulary.  In this mode, the n-gram weights from the input vocabulary are used, instead of computing them from the input text dataset.  
  
         *Use this  option when scoring a text classifier.*  
  
    -   **Update**. Create a new n-gram vocabulary from the input corpus and merge it with the input vocabulary. In other words, you can add new entries to the created vocabulary from the input vocabulary, or you can update existing entries.  
  
         *Use this option for incremental update of vocabulary with incoming data batches.*  
  
    -   **Merge**. Create a new n-gram vocabulary from the input corpus.  
  
         This option is useful if you are passing a background vocabulary as input to the module and want to down-weight stop words. In other words, each entry that has a high DF in the background vocabulary will be assigned a lower IDF in the created vocabulary .  
  
         *Use this option if you don't want to add new entries to the created vocabulary from the input, and only want to update existing entries*.  
  
9. The option, **Choose the weighting function**, is required if you merge or update vocabularies.  
  
     Choose from the  following weighting functions to specify how the n-gram values in the two vocabularies are to be weighted against each other.:  
  
    -   **Binary Weight**. Assigns a binary presence value to the extracted n-grams.  In other words, the value for each n-gram is 1 if it exists in the given document, and 0 otherwise.  
  
    -   **TF Weight**. Assigns a term-frequency score (**TF**) to the extracted n-grams.  The value for each n-gram is its occurrence frequency in the given document.  
  
    -   **IDF Weight**. Assigns an inverse document frequency score (**IDF**) to the extracted n-grams.  The value for each n-gram is the log of corpus size divided by its occurrence frequency in the whole corpus. That is, IDF = log of corpus_size / document_frequency).  
  
    -   **TF-IDF Weight**. Assigns an term frequency/inverse document frequency score (**TF/IDF**) to the extracted n-grams.  The value for each n-gram is its TF score multiplied by its IDF score.  
  
    -   **Graph Weight**. Assigns score to the extracted n-grams based on the TextRank graph ranking.  
  
         TextRank  is a graph-based ranking model for text processing. Graph-based ranking algorithms are essentially a way of deciding importance  based on global information. For more information about the TextRank algorithm, see [TextRank- Bringing Order Into Texts](http://acl.ldc.upenn.edu/acl2004/emnlp/pdf/Mihalcea.pdf) by Rada Mihalcea and Paul Tarau.  
  
10. Select the option **Normalize n-gram feature vectors** to apply normalization to n-gram feature vectors.  If true, then the n-gram feature vector is divided by its L2 norm.  
  
     Normalization is applied by default.  
  
11. Select the option, **Use filter-based feature selection**, if you want to reduce the dimensionality of your n-grams by applying filter-based feature selection. If you do not use this option, all possible n-grams will be created, increasing coverage at the expense of making the dictionary longer and possibly including many infrequent terms.  
  
     If you use feature selection, select one of the following feature scoring methods from the **Feature scoring method** drop-down list:  
  
    -   **PearsonCorrelation**. Compute Pearson's correlation, using the label column value and the text vector.  
  
    -   **MutualInformation**. Compute a mutual information score, using the label column value and the text vector.  
  
    -   **KendallCorrelation**. Compute Kendall's correlation, using the label column value and the text vector.  
  
    -   **SpearmanCorrelation**. Compute the Spearman correlation, using the label column value and the text vector.  
  
    -   **ChiSquared**. Use the chi-squared method to calculate correlation between the label column value and the text vector.  
  
    -   **FisherScore**. Compute the Fisher score for the label column value and the text vector.  
  
    -   **Count-based feature selection**.  Create new features based on the counts of values. A label column is not required.  
  
     For more information about these methods, see [Filter Based Feature Selection](filter-based-feature-selection.md).  
  
12. For **Number of desired features**, type the number of many features you want as the **output** of feature selection. N-grams that have low feature value will be discarded.  
  
     This option is not available for count-based feature selection, which computes counts for all columns used as input.  
  
     Instead, use the option, **Minimum number of non-zero elements**, and type a threshold value that determines the minimum number of instances required to tabulate counts for a potential feature.  
  
13. Run the experiment.  
 
### Results  

The **Extract N-Gram Features from Text** module creates two outputs:  
  
- **Results dataset**. The results dataset contained the text after n-gram extraction.  
  
- **Result vocabulary**. The vocabulary contains the n-gram dictionary with weights that was created. You can save the dataset for re-use with a different set of inputs, or for later update.  
  
## How to Score or Publish a Model with N-Grams  
  
1.  Copy the **Extract N-Gram Features from Text** module from the training dataflow to the scoring dataflow.  
  
2.  Connect the **Result Vocabulary** output from the training dataflow to the **Input Vocabulary** on the scoring dataflow.  
  
3.  In the scoring workflow, modify the **Extract N-Gram Features from Text** module and make these changes, leaving all else the same:  
  
    -   Set the **Vocabulary mode** parameter to **ReadOnly**  
  
    -   Change the option **Use filter based feature selection** to `False`.  
  
4.  To publish the  experiment, save the **Result Vocabulary** as dataset.  
  
     Then, connect the saved dataset to the **Extract N-Gram Features from Text** module in your scoring graph.  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical Notes  
 You might need to experiment with different ranges of values for n-gram length and feature count to determine the dimensionality of your text corpus and the optimum feature ratio.  
  
 For more information about n-grams and skip-grams, see these resources:  
  
 [Automatic Evaluation of Summaries Using N-gram  Co-Occurrence Statistics](http://research.microsoft.com/en-us/um/people/cyl/download/papers/NAACL2003.pdf)  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input data|  
|Input vocabulary|[Data Table](data-table.md)|Input vocabulary|  
  
##  <a name="parameters"></a> Module Parameters  
  
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
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Extracted features|  
|Result vocabulary|[Data Table](data-table.md)|Result vocabulary|  
  
## See Also  
 [Text Analytics](text-analytics.md)   
 [A-Z List of Machine Learning Modules](a-z-module-list.md)