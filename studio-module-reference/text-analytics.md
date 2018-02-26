---
title: "Text Analytics | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c790e4eb-2aae-4228-a12f-69809b9e70ae
caps.latest.revision: 24
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Text Analytics

This article describes the text analytics modules included in Azure Machine Learning Studio. These modules provide specialized computational tools for working with both structured and unstructured text:  

+ Multiple options for preprocessing text
+ Language detection
+ Creation of features from text using customizable n-gram dictionaries
+ Feature hashing, to efficiently analyze text without preprocessing or advanced linguistic analysis  
+ Vowpal Wabbit, for very fast machine learning on text. Vowpal Wabbit supports feature hashing, topic modeling (LDA), classification, and more.
+ Named entity recognition, to extract the names of people, places, and organizations from unstructured text

## Examples

For examples of text analytics using Azure Machine Learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):  

- [News Categorization](http://go.microsoft.com/fwlink/?LinkId=525167): Uses feature hashing to classify articles into a predefined list of categories.

- [Find similar companies](http://go.microsoft.com/fwlink/?LinkId=525164): Uses the text of Wikipedia articles to categorize companies.  
  
- [Text Classification](http://go.microsoft.com/fwlink/?LinkId=525957): This five-part sample demonstrates the end-to-end process of using text from Twitter messages in sentiment analysis.

##  List of modules

The **Text Analytics** category in Azure machine Learning Studio includes these modules:

+ [Detect Languages](detect-languages.md): Detects the language of each line in the input file  
+ [Extract Key Phrases from Text](extract-key-phrases-from-text.md): Extracts key phrases from given text  
+ [Extract N-Gram Features from Text](extract-n-gram-features-from-text.md): Creates N-Gram dictionary features and does feature selection on them  
+ [Feature Hashing](feature-hashing.md): Converts text data to integer-encoded features using the Vowpal Wabbit library  
+ [Latent Dirichlet Allocation](latent-dirichlet-allocation.md): Performs topic modeling using the Vowpal Wabbit library for LDA  
+ [Named Entity Recognition](named-entity-recognition.md): Recognizes named entities in a text column  
+ [Preprocess Text](preprocess-text.md): Performs cleaning operations on text  
+ [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md): Scores input from Azure using version 7-4 of the Vowpal Wabbit machine learning system  
+ [Score Vowpal Wabbit 7-10 Model](score-vowpal-wabbit-version-7-10-model.md): Scores input from Azure using version 7-10 of the Vowpal Wabbit machine learning system  
+ [Score Vowpal Wabbit 8 Model](score-vowpal-wabbit-version-8-model.md): Scores input from Azure using version 8 of the Vowpal Wabbit machine learning system  
+ [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md): Trains a model using version 7-4 of the Vowpal Wabbit machine learning system  
+ [Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md): Trains a model using version 7-10 of the Vowpal Wabbit machine learning system  
+ [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md): Trains a model using version 8 of the Vowpal Wabbit machine learning system  

## See also
 [Regression](machine-learning-initialize-model-regression.md)   
 [Classification](machine-learning-initialize-model-classification.md)   
 [Clustering](machine-learning-initialize-model-clustering.md)   
 [Text analytics modules](text-analytics.md)   
 [OpenCV library modules](opencv-library-modules.md)   
 [All module categories](machine-learning-module-descriptions.md)