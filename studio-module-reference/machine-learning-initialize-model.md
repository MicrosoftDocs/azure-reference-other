---
title: "Machine Learning - Initialize Model | Microsoft Docs"
description: "Learn about the modules you can use in Azure Machine Learning Studio to define a machine learning model and set its parameters."
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0c67013c-bfbc-428b-87f3-f552d8dd41f6
caps.latest.revision: 10
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Machine Learning - Initialize Model

This article describes the modules in Azure Machine Learning Studio that you can use to define a machine learning model and set its parameters. 

You can think of the *untrained model* as a specification that you can apply to different input datasets. You might apply the same model specification to different data and get different results. Or, you can use the specification to retrain a model. You can then add new data.

This article also describes the overall process of creating, training, evaluating, and scoring a model in Machine Learning Studio.

## Create and use machine learning models in Machine Learning Studio

The typical workflow for machine learning includes these phases:

- Choose a suitable algorithm and set initial options.
- Train the model by using compatible data.
- Create predictions by using new data based on the patterns in the model.
- Evaluate the model to determine whether the predictions are accurate, the amount of error, and whether overfitting occurs.

Machine Learning Studio supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module. Modules can be modified, added, or removed without breaking the rest of your experiment.

Use the modules in this category to select an initial algorithm. Then, configure detailed parameters based on the specific model type. You can then apply this model specification to a set of data.

## About creating models

Azure Machine Learning provides many state-of-the art machine learning algorithms to help you build analytical models. Each algorithm is packaged in its own module. To create a customized model:

1. Choose a model by category.

    Algorithms are grouped by specific types of predictive tasks. Examples include regression, classification, and image recognition. Your first task is to identify the general category of machine learning task to perform, and then to select an algorithm. If you need help selecting an algorithm, see these resources:
 
    - [Machine learning algorithm cheat sheet for Machine Learning Studio](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-cheat-sheet/)
 
    - [Choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)
 
2. Configure algorithm parameters.

    Use the **Properties** pane in each module to set parameters. Parameters control how the model learns from data.
 
3. Train the model on data.
 
    After you configure the model, connect a dataset. Then, use one of the [training modules](machine-learning-initialize-model.md) to run data through the algorithms that you want to use.
 
    You can use [Tune Model Hyperparameters](tune-model-hyperparameters.md) to iterate over all possible parameters and determine the optimal configuration for your task and data.
 
4. Predict, score, or evaluate.

    After you build and train a model, typically your next step is to use one of the [scoring modules](machine-learning-score.md) to generate predictions based on the model.
 
    You can use the modules for [model evaluation](machine-learning-evaluate.md) to measure the accuracy of the model based on the scores that you generate.
 
## List of modules

The modules in this category are organized by the type of machine learning algorithm that the modules encapsulate. Each type of algorithm typically requires a different type of data.

- [Anomaly Detection](anomaly-detection.md)
- [Classification](machine-learning-initialize-model-classification.md)
- [Clustering](machine-learning-initialize-model-clustering.md)
- [Regression](machine-learning-initialize-model-regression.md)

## Related tasks

In addition to the traditional machine learning algorithm categories described here, the following modules provide specialized types of learning from data or preprocessing:

- [Text analysis](text-analytics.md)
- [Image classification](pretrained-cascade-image-classification.md)
- [Time series analysis](time-series.md)

## See also
 
- [Train](machine-learning-train.md)
- [Score](machine-learning-score.md)
- [Evaluate](machine-learning-evaluate.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)