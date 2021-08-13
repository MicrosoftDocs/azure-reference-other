---
title: "ML Studio (classic): Text Analytics - Azure"
description: This article describes the text analytics modules included in Machine Learning Studio (classic). 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Text Analytics

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes the text analytics modules included in Machine Learning Studio (classic). These modules provide specialized computational tools for working with both structured and unstructured text, including:  

+ Multiple options for preprocessing text.
+ Language detection.
+ Creation of features from text using customizable n-gram dictionaries.
+ Feature hashing, to efficiently analyze text without preprocessing or advanced linguistic analysis.  
+ Vowpal Wabbit, for very fast machine learning on text. Vowpal Wabbit supports feature hashing, topic modeling (LDA), and classification.
+ Named entity recognition, to extract the names of people, places, and organizations from unstructured text.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Examples

For examples of text analytics using Machine Learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [News categorization](https://go.microsoft.com/fwlink/?LinkId=525167): Uses feature hashing to classify articles into a predefined list of categories.

- [Find similar companies](https://go.microsoft.com/fwlink/?LinkId=525164): Uses the text of Wikipedia articles to categorize companies.  
  
- [Text classification](https://go.microsoft.com/fwlink/?LinkId=525957): Demonstrates the end-to-end process of using text from Twitter messages in sentiment analysis (five-part sample).

##  List of modules

The **Text Analytics** category in Machine Learning Studio (classic) includes these modules:

+ [Detect Languages](detect-languages.md): Detects the language of each line in the input file.  
+ [Extract Key Phrases from Text](extract-key-phrases-from-text.md): Extracts key phrases from given text.  
+ [Extract N-Gram Features from Text](extract-n-gram-features-from-text.md): Creates N-Gram dictionary features, and does feature selection on them.  
+ [Feature Hashing](feature-hashing.md): Converts text data to integer-encoded features by using the Vowpal Wabbit library.  
+ [Latent Dirichlet Allocation](latent-dirichlet-allocation.md): Performs topic modeling by using the Vowpal Wabbit library for LDA.  
+ [Named Entity Recognition](named-entity-recognition.md): Recognizes named entities in a text column.  
+ [Preprocess Text](preprocess-text.md): Performs cleaning operations on text.  
+ [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md): Scores input from Azure by using version 7-4 of the Vowpal Wabbit machine learning system.  
+ [Score Vowpal Wabbit 7-10 Model](score-vowpal-wabbit-version-7-10-model.md): Scores input from Azure by using version 7-10 of the Vowpal Wabbit machine learning system.  
+ [Score Vowpal Wabbit 8 Model](score-vowpal-wabbit-version-8-model.md): Scores input from Azure by using version 8 of the Vowpal Wabbit machine learning system.  
+ [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md): Trains a model by using version 7-4 of the Vowpal Wabbit machine learning system.  
+ [Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md): Trains a model by using version 7-10 of the Vowpal Wabbit machine learning system.  
+ [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md): Trains a model by using version 8 of the Vowpal Wabbit machine learning system.  

## See also
- [Regression module](machine-learning-initialize-model-regression.md)   
- [Classification module](machine-learning-initialize-model-classification.md)  
- [Clustering module](machine-learning-initialize-model-clustering.md)   
- [OpenCV Library Modules category](opencv-library-modules.md)   
- [All module categories](machine-learning-module-descriptions.md)
