---
title: "Machine Learning - Initialize Model | Microsoft Docs"
ms.custom: ""
ms.date: 10/05/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0c67013c-bfbc-428b-87f3-f552d8dd41f6
caps.latest.revision: 10
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning - Initialize Model
This article describes the modules in Azure Machine Learning Studio that you can use to create an untrained machine learning model.

## Initialize, then Train and Score

Azure Machine Learning provides many different state-of-the art machine learning algorithms to help you build analytical models. In general, these algorithms are packaged as modules, that you can connect to perform machine learning tasks. To create a model, the process is generally as follows: 
  
1. Choose a model by [category](#bkmk_categories).

    The algorithms provided in Studio are grouped by specific types of predictive tasks, such as regression, classification, or image recognition. Your first job is to identify the general category of machine learning task to perform, and then select an algorithm from those provided. 
    
    If you need help selecting an algorithm, see these resources:  
  
    -   [Machine learning algorithm cheat sheet for Microsoft Azure Machine Learning Studio](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-cheat-sheet/)  
  
    -   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
  
2. Configure algorithm parameters.

    After you choose a regression, classification or clustering model type, use the **Properties** pane in each module to configure important *hyperparameters*.  In machine learning, hyperparameters refer to API options for each model type that affect the way the model trains on data, or that change the results.
    
3. Train the model.
    
    After the model has been configured, connect  a dataset, and use one of the [training modules](machine-learning-initialize-model.md) to run data through the chosen algorithms, or you can use [Tune Model Hyperparameters](tune-model-hyperparameters.md) to iterate over all possible parameters and determine the optimal configuration for your task and data.  
  
4. Predict, score, or evaluate.

    Having built and trained a model, typically your next step is to use one of the [scoring modules](machine-learning-score.md) to generate predictions based on the model.  
  
    You can use the modules for [model evaluation](machine-learning-evaluate.md) section to measure the accuracy of the model, based on the scores you’ve generated.  
  
##  <a name="bkmk_categories"></a>  Machine Learning Algorithm Categories  

The model types in this section fall into the following categories:  
  
|Category|  
|--------------|  
|[Anomaly Detection](anomaly-detection.md)|  
|[Classification](machine-learning-initialize-model-classification.md)|  
|[Clustering](machine-learning-initialize-model-clustering.md)|  
|[Regression](machine-learning-initialize-model-regression.md)|  

### Related tasks

[Text analysis](text-analytics.md)   
[Image classification](pretrained-cascade-image-classification.md)   
  
## See Also  
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Train](machine-learning-train.md)   
 [Score](machine-learning-score.md)   
 [Evaluate](machine-learning-evaluate.md)