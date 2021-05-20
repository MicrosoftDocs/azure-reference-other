---
title: "ML Studio (classic): Latent Dirichlet Allocation - Azure"
description: Learn how to use the Latent Dirichlet Allocation module to group otherwise unclassified text into a number of categories.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"


author: xiaoharper
ms.author: amlstudiodocs

---
# Latent Dirichlet Allocation

*Use the Vowpal Wabbit library to perform VW LDA*

Category: [Text Analytics](text-analytics.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Latent Dirichlet Allocation** module in Azure Machine Learning Studio (classic), to group otherwise unclassified text into a number of categories. Latent Dirichlet Allocation (LDA) is often used in natural language processing (NLP) to find texts that are similar. Another common term is *topic modeling*.

This module takes a column of text, and generates these outputs:

+ The source text, together with a score for each category

+ A feature matrix, containing extracted terms and coefficients for each category

+ A transformation, which you can save and reapply to new text used as input

Because this module uses the Vowpal Wabbit library, it is very fast. For more information about Vowpal Wabbit, see the [GitHub repository](https://github.com/JohnLangford/vowpal_wabbit) which includes tutorials and an explanation of the algorithm.

### More about Latent Dirichlet Allocation (LDA)

Generally speaking, LDA is not a method for classification per se, but uses a generative approach. What this means is that you don’t need to provide known class labels and then infer the patterns.  Instead, the algorithm generates a probabilistic model that is used to identify groups of topics. You can use the probabilistic model to classify either  existing training cases, or new cases that you provide to the model as input.

A generative model can be preferable because it avoids making any strong assumptions about the relationship between the text and categories, and uses only the distribution of words to mathematically model topics.

+ The theory is discussed in this paper, available as a PDF download: [Latent Dirichlet Allocation: Blei, Ng, and Jordan](https://ai.stanford.edu/~ang/papers/nips01-lda.pdf)

+ The implementation in this module is based on the [Vowpal Wabbit library](https://github.com/JohnLangford/vowpal_wabbit/wiki/Latent-Dirichlet-Allocation) (version 8) for LDA.

For more information, see the [Technical notes](#bkmk_AboutLDA) section.

## How to configure Latent Dirichlet Allocation

This module requires a dataset that contains a column of text, either raw or preprocessed.

1. Add the **Latent Dirichlet Allocation** module to your experiment.

2. As input for the module, provide a dataset containing one or more text columns.

3. For **Target columns**, choose one or more columns containing text to analyze.

    You can choose multiple columns but they must be of the string data type.

    In general, because LDA creates a large feature matrix from the text, you'll typically analyze a single text column.

4. For  **Number of topics to model**, type an integer between 1 and 1000 that indicates how many categories or topics you want to derive from the input text.

    By default, 5 topics are created.

5. For **N-grams**, specify the maximum length of N-grams generated during hashing.

    The default is 2, meaning that both bigrams and unigrams are generated.

6. Select the **Normalize** option to converting output values to probabilities. Therefore, rather than representing the transformed values as integers, values in the output and feature dataset would be transformed as follows:

    + Values in the dataset will be represented as a probability where `P(topic|document)`.

    + Values in the feature topic matrix will be represented as a probability where `P(word|topic)`.

7. Select the option, **Show all options**, and then set it to TRUE if you want to view and then set  additional advanced parameters.

    These parameters are specific to the Vowpal Wabbit implementation of LDA. There are some good tutorials about LDA in Vowpal Wabbit online, as well as the official [Vowpal Wabbit Wiki](https://github.com/JohnLangford/vowpal_wabbit/wiki).

    See [this sample](https://github.com/JohnLangford/vowpal_wabbit/wiki/Tutorial) for examples in version 8 and use of VW in Azure ML.

    + **Rho parameter**. Provide a prior probability for the sparsity of topic distributions. Corresponds to VW's `lda_rho` parameter. You would use the value 1 if you expect that the distribution of words is flat; i.e, all words are assumed equiprobable. If you think most words appear sparsely, you might set it to a much lower value.

    + **Alpha parameter**. Specify a prior probability for the sparsity of per-document topic weights.  Corresponds to VW's `lda_alpha` parameter.

    + **Estimated number of documents**. Type a number that represents your best estimate of the number of documents (rows) that will be processed. This lets the module allocate a hash table of sufficient size.  Corresponds to the `lda_D` parameter in Vowpal Wabbit.

    + **Size of the batch**. Type a number that indicates how many rows to include in each batch of text sent to Vowpal Wabbit. Corresponds to the `batch_sz` parameter in Vowpal Wabbit.

    + **Initial value of iteration used in learning update schedule**. Specify the starting value for the learning rate. Corresponds to the `initial_t` parameter in Vowpal Wabbit.

    + **Power applied to the iteration during updates**. Indicate the level of power applied to the iteration count during online updates. Corresponds to the `power_t` parameter in Vowpal Wabbit.

    + **Number of passes over the data**. Specify the number of times the algorithm will cycle over the data. Corresponds to the `epoch_size` parameter in Vowpal Wabbit.

8. Select the option, **Build dictionary of ngrams** or **Build dictionary of ngrams prior to LDA**, if you want to create the n-gram list in an initial pass, before classifying text.

    If you create the initial dictionary beforehand, you can later use the dictionary when reviewing the model. Being able to map results to text rather than numerical indices is generally easier for interpretation. However, saving the dictionary will take longer and use additional storage.

9. For **Maximum size of ngram dictionary**, type the total number of rows that can be created in the n-gram dictionary.

    This option is useful for controlling the size of the dictionary. However, if the number of ngrams in the input exceeds this size, collisions may occur.

10. Run the experiment. The LDA module uses Bayes theorem to determine what topics might be associated with individual words. Words are not exclusively associated with any topics or groups; instead, each n-gram has a learned probability of being associated with any of the discovered classes.

### Results

The module has two outputs:

+ **Transformed dataset**: Contains the input text, and a specified number of discovered categories, together with the scores for each text example for each category.

+ **Feature topic matrix**: The leftmost column contains the extracted text feature, and there is a column for each category containing the score for that feature in that category.

For details, see [Example of LDA results](#bkmk_Understanding).

### LDA transformation

This module also outputs the *transformation* that applies LDA to the dataset, as an [ITransform interface](itransform-interface.md).

You can save this transformation and re-use it for other datasets. This might be useful if you have trained on a large corpus and want to reuse the coefficients or categories.

### Refining an LDA model or results

Typically you cannot create a single LDA model that will meet all needs, and even a model designed for one task might require many iterations to improve accuracy. We recommend that you try all these methods to improve your model:

+ Changing the model parameters
+ Using visualization to understand the results
+ Getting the feedback of subject matter experts to ascertain whether the generated topics are useful.

Qualitative measures can also be useful for assessing the results. To evaluate topic modeling results, consider:

+ Accuracy - Are similar items really similar?
+ Diversity - Can the model discriminate between similar items when required for the business problem?
+ Scalability - Does it work on a wide range of text categories or only on a narrow target domain?

The accuracy of models based on LDA can often be improved by using natural language processing to clean, summarize and simplify, or categorize text. For example, the following techniques, all supported in Azure Machine Learning, can improve classification accuracy:

+ Stop word removal

+ Case normalization

+ Lemmatization or stemming

+ Named entity recognition

For more information, see [Preprocess Text](preprocess-text.md) and [Named Entity Recognition](named-entity-recognition.md).

In Studio (classic), you can also use R or Python libraries for text processing: [Execute R Script](execute-r-script.md),  [Execute Python Script](execute-python-script.md)

## Examples

For examples of text analytics, see these experiments in the [Azure AI Gallery](https://azure.microsoft.com/documentation/services/machine-learning/models):

+ [Execute Python Script](https://go.microsoft.com/fwlink/?LinkId=525942): Uses natural language processing in Python to clean and transform text.

For details and an example based on customer review text, see [Understanding LDA Results](#bkmk_Understanding).

### <a name="bkmk_Understanding"></a>Example of LDA results

To illustrate how the **Latent Dirichlet Allocation** module works, the following example applies LDA with the default settings to the Book Review dataset provided in Azure Machine Learning Studio (classic).

#### Source dataset

The dataset contains a rating column, as well as the full comment text provided by users.

This table shows only a few representative examples.

|text|  
|----------|  
|This book has its good points. If anything, it helps you put into words what you want  from a supervisor....|  
|I admit, I haven't finished this book.  A friend recommended it to me as I have been having problems with insomnia...|  
|Poorly written  I tried reading this book but found it so turgid and poorly written that I put it down in frustration.  ...|  
|Since borrowing a dog-eared copy from friends who were passing it around a number of years ago, I have not been able to get my hands on this book which became a short-lived cult favorite|  
|The plot of this book was interesting, and it could have been a good book. Unfortunately, it wasn't. The main problem for me was that ...|  

During processing, the **Latent Dirichlet Allocation** module both cleans and analyzes the text, based on parameters you specify. For example, it can automatically tokenize the text and remove punctuation, and at the same time find the text features for each topic.

#### LDA transformed dataset

The following table contains the **transformed** dataset, based on the Book Review sample. The output contains the input text, and a specified number of discovered categories, together with the scores for each category.

|Movie name|Topic 1|Topic 2|Topic 3|Topic 4|Topic 5|  
|----------------|-------------|-------------|-------------|-------------|-------------|  
|this book has its good points|0.001652892|0.001652892|0.001652892|0.001652892|0.9933884|  
|friend recommended it to me|0.00198019|0.001980198|0.9920791|0.001980198|0.001980198|  
|tried reading this book|0.002469135|0.002469135|0.9901233|0.002469135|0.002469135|  
|borrowed it from friend|0.9901232|0.002469135|0.002469135|0.002469135|0.002469135|  
|plot of this book was interesting|0.001652892|0.001652892|0.9933884|0.001652892|0.001652892|  

In this example, we used the default value of 5 for **Number of topics to model**. Therefore, the LDA module creates five categories, which we can assume will correspond roughly with the original five-scale rating system.

The module also assigns a score to each entry for each of the five categories that represent topics. A score indicates the probability that the row should be assigned to a particular category.

#### Feature topic matrix

The second output of the module is the **feature topic matrix**. This is a tabular dataset that contains the *featurized text*, , in column **Feature**, along with a score for each of the categories, in the remaining columns _Topic 1_, _Topic 2_, ..._Topic N_. The score represents the coefficient.

|Feature|Topic 1|Topic 2|Topic 3|Topic 4|Topic  5|  
|-------------|-------------|-------------|-------------|-------------|--------------|  
|interesting|0.0240282071983144|0.0354678954779375|0.363051866576914|0.0276637824315893|0.660663576149515|  
|was|0.0171478729532397|0.0823969031108669|0.00452966877950789|0.0408714510319233|0.025077322689733|  
|from|0.0148224220349217|0.0505086981492109|0.00434423322461094|0.0273389126293824|0.0171484355106826|  
|plot|0.0227415889348212|0.0408709456489325|0.182791041345191|0.086937090812819|1   0.0169680136708971|  
|reading|0.0227415889348212|0.0408709456489325|0.182791041345191|0.0869370908128191|0.0169680136708971|  
|tried|0.0269724979147211|0.039026263551767|0.00443749106785087|0.0628829816088284|0.0235340728818033|  
|me|0.0262656945140134|0.0366941302751921|0.00656837975179138|0.0329214576160066|0.0214121851106808|  
|to|0.0141026103224462|0.043359976919215|0.00388640531859447|0.0305925953440055|0.0228993750526364|  
|it|0.0264490547105951|0.0356674440311847|0.00541759897864314|0.0314539386250293|0.0140606468587681|  
|friend|0.0135971322960941|0.0346118171467234|0.00434999437350706|0.0666507321888536|0.018156863779311|  
|points|0.0227415889348212|0.0396233855719081|0.00404663601474112|0.0381156510019025|0.0337788009496797|  
|good|0.651813073836783|0.0598646397444108|0.00446809691985617|0.0358975694646062|0.0138989124411206|  
|its|0.0185385588647078|0.144253986783184|0.00408876416453866|0.0583049240441475|0.015442805566858|  
|of|0.0171416780245647|0.0559361180418586|0.0100633904544953|0.087093930106723|0.0182573833869842|  
|borrowed|0.0171416780245647|0.0559361180418586|0.0100633904544953|0.087093930106723|0.0182573833869842|  
|has|0.0171416780245647|0.0559361180418586|0.0100633904544953|0.087093930106723|0.0182573833869842|  
|book|0.0143157047920681|0.069145948535052|0.184036340170983|0.0548757337823903|0.0156837976985903|  
|recommended|0.0161486848419689|0.0399143326399534|0.00550113530229642|0.028637149142764|0.0147675139039372|  
|this|0.0161486848419689|0.0399143326399534|0.00550113530229642|0.028637149142764|0.0147675139039372|  

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

By default, the distributions of outputs for transformed dataset and feature-topic matrix are normalized as probabilities.

+ The transformed dataset is normalized as the conditional probability of topics given a document. In this case, the sum of each row equals 1.

+ The feature-topic matrix is normalized as the conditional probability of words given a topic. In this case, the sum of each column equals 1.

> [!TIP]
> Occasionally the module might return an empty topic, which is most often caused by the pseudo-random initialization of the algorithm.  If this happens, you can try changing related  parameters, such as the maximum size of the N-gram dictionary or the number of bits to use for feature hashing.

### <a name="bkmk_AboutLDA"></a> LDA and topic modeling

Latent Dirichlet Allocation (LDA) is often used for *content-based topic modeling*, which basically means learning categories from unclassified text. In content-based topic modeling, a topic is a distribution over words.

For example, assume that you have provided a corpus of customer reviews that includes many, many products. The text of reviews that have been submitted by many customers over time would contain many terms, some of which are used in multiple topics.

A **topic** that is identified by the LDA process might represent reviews for an individual Product A, or it might represent a group of product reviews. To LDA, the topic itself is just a probability distribution over time for a set of words.

Terms are rarely exclusive to any one product, but can refer to other products, or be general terms that apply to everything (“great”, “awful”). Other terms might be noise words.  However, it is important to understand that the LDA method does not purport to capture all words in the universe, or to understand how words are related, aside from probabilities of co-occurrence. It can only group words that were used in the target domain.

After the term indexes have been computed, individual rows of text are compared using a distance-based similarity measure, to determine whether two pieces of text are like each other.  For example, you might find that the product has multiple names that are strongly correlated. Or, you might find that strongly negative terms are usually associated with a particular product. You can use the similarity measure both to identify related terms and to create recommendations.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

##  Module parameters

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Number of hash bits|Integer|[1;31]|Applies when the **Show all options** checkbox  is *not* selected|12|Number of bits to use for feature hashing|  
|Target column(s)|Column Selection||Required|StringFeature|Target column name or index|  
|Number of topics to model|Integer|[1;1000]|Required|5|Model the document distribution against N topics|  
|N-grams|Integer|[1;10]|Required|2|Order of N-grams generated during hashing|  
|Normalize|Boolean||Required|true|Normalize output to probabilities.  The transformed dataset will be P(topic&#124;document) and the feature topic matrix will be P(word&#124;topic).|  
|Show all options|Boolean|True or False|Required|False|Presents additional parameters specific to Vowpal Wabbit online LDA|  
|Rho parameter|Float|[0.00001;1.0]|Applies when the **Show all options** checkbox  is selected|0.01|Rho parameter|  
|Alpha parameter|Float|[0.00001;1.0]|Applies when the **Show all options** checkbox  is selected|0.01|Alpha parameter|  
|Estimated number of documents|Integer|[1;int.MaxValue]|Applies when the **Show all options** checkbox  is selected|1000|Estimated number of documents (Corresponds to lda_D parameter)|  
|Size of the batch|Integer|[1;1024]|Applies when the **Show all options** checkbox  is selected|32|Size of the batch|  
|Initial value of iteration used in learning rate update schedule|Integer|[0;int.MaxValue]|Applies when the **Show all options** checkbox  is selected|0|Initial value of iteration count used in learning rate update schedule (Corresponds to initial_t parameter)|  
|Power applied to the iteration during updates|Float|[0.0;1.0]|Applies when the **Show all options** checkbox  is selected|0.5|Power applied to the iteration count during online updates (Corresponds to power_t parameter)|  
|Number of training iterations|Integer|[1;1024]|Applies when the **Show all options** checkbox  is selected|25|Number of training iterations|  
|Build dictionary of ngrams|Boolean|True or False|Applies when the **Show all options** checkbox  is *not* selected|True|Builds a dictionary of ngrams prior to computing LDA. Useful for model inspection and interpretation|  
|Number of bits to use for feature hashing|Integer|[1;31]|Applies when the option **Build dictionary of ngrams** is False|12|Number of bits to use during feature hashing|  
|Maximum size of ngram dictionary|Integer|[1;int.MaxValue]|Applies when the option **Build dictionary of ngrams** is True|20000|Maximum size of the ngrams dictionary. If number of tokens in the input exceed this size, collisions may occur|  
|Build dictionary of ngrams prior to LDA|Boolean|True or False|Applies when the **Show all options** checkbox  is selected|True|Builds a dictionary of ngrams prior to LDA. Useful for model inspection and interpretation|  
|Maximum number of ngrams in dictionary|Integer|[1;int.MaxValue]|Applies when the option **Build dictionary of ngrams** is True and the **Show all options** checkbox  is selected|20000|Maximum size of the dictionary. If number of tokens in the input exceed this size, collisions may occur|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Transformed dataset|[Data Table](data-table.md)|Output dataset|  
|Feature topic matrix|[Data Table](data-table.md)|Feature topic matrix produced by LDA|  
|LDA transformation|[ITransform interface](itransform-interface.md)|Transformation that applies LDA to the dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0002](errors/error-0002.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Text Analytics](text-analytics.md)   
 [Feature Hashing](feature-hashing.md)   
 [Named Entity Recognition](named-entity-recognition.md)   
 [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md)
