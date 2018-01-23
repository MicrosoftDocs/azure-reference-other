---
title: "Machine Learning - Initialize Model | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0c67013c-bfbc-428b-87f3-f552d8dd41f6
caps.latest.revision: 10
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Machine Learning - Initialize Model

This article describes the modules in Azure Machine Learning Studio that you can use to define a machine learning model and set its parameters. You can think of the **untrained model** as a specification that you can then apply to different input data sets. You might apply the same model specification on different data, to get different results, or use the specification to retrain an model and add new data.

This article also describes the overall process in Studio for model creation, training, evaluation, and scoring.

## Creating and using machine learning models in Studio

The typical workflow for machine learning includes these phases:

- Choosing a suitable alorithm, and setting initial options
- Training the model on compatible data
- Creating predictions using new data, based on the patterns in the model
- Evaluating the model to determine if the predictions are accurate, how much error there is, and if there is any overfitting

Azure Machine Learning Studio supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module, which can be modified, added, re removed, without breaking the rest of your experiment. 

You use the modules in this category to select an initial algorithm, and then configure detailed parameters on the specific model type. You can then apply this model specification to some set of data.

## More about creating models

Azure Machine Learning provides many different state-of-the art machine learning algorithms to help you build analytical models. Each algorithm is packaged in its own module. To create a customized model: 
  
1. Choose a model by [category](#bkmk_categories).

    Algorithms are grouped by specific types of predictive tasks, such as regression, classification, or image recognition. Your first job is to identify the general category of machine learning task to perform, and then select an algorithm from those provided. If you need help selecting an algorithm, see these resources:  
  
    -   [Machine learning algorithm cheat sheet for Microsoft Azure Machine Learning Studio](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-cheat-sheet/)  
  
    -   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
  
2. Configure algorithm parameters.

    Use the **Properties** pane in each module to set parameters that control how the model learns from data. 
    
3. Train the model on data.
    
    After the model has been configured, connect a dataset, and use one of the [training modules](machine-learning-initialize-model.md) to run data through the chosen algorithms. 
    
    You can use [Tune Model Hyperparameters](tune-model-hyperparameters.md) to iterate over all possible parameters and determine the optimal configuration for your task and data.  
  
4. Predict, score, or evaluate.

    Having built and trained a model, typically your next step is to use one of the [scoring modules](machine-learning-score.md) to generate predictions based on the model.
  
    You can use the modules for [model evaluation](machine-learning-evaluate.md) section to measure the accuracy of the model, based on the scores you’ve generated.
  
##  <a name="bkmk_categories"></a>  List of modules

The modules in this category are organized by the type of machine learning algorithm encapsulated by the modules. For each type of algorithm, you typically requires a different type of data.

+ [Anomaly Detection](anomaly-detection.md)
+ [Classification](machine-learning-initialize-model-classification.md)
+ [Clustering](machine-learning-initialize-model-clustering.md)
+ [Regression](machine-learning-initialize-model-regression.md)

### Related tasks

In addition to the traditional machine learnign algorithm categoris described above, the following modules provide specialized types of learning from data or preprocessing:

[Text analysis](text-analytics.md)
[Image classification](pretrained-cascade-image-classification.md)
[Time series analysis](time-series.md)

## See also
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Train](machine-learning-train.md)   
 [Score](machine-learning-score.md)   
 [Evaluate](machine-learning-evaluate.md)