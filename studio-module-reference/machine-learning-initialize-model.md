---
title: "ML Studio (classic): Initialize Model - Azure"
description: "Learn about the modules you can use in Machine Learning Studio (classic) to define a machine learning model and set its parameters."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Machine Learning - Initialize Model

This article describes the modules in Machine Learning Studio (classic) that you can use to define a machine learning model and set its parameters. 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

You can think of the *untrained model* as a specification that you can apply to different input datasets. You might apply the same model specification to different data and get different results. Or, you can use the specification to retrain a model. You can then add new data.

This article also describes the overall process of creating, training, evaluating, and scoring a model in Machine Learning Studio (classic).

## Create and use machine learning models in Machine Learning Studio (classic)

The typical workflow for machine learning includes these phases:

- Choose a suitable algorithm and set initial options.
- Train the model by using compatible data.
- Create predictions by using new data based on the patterns in the model.
- Evaluate the model to determine whether the predictions are accurate, the amount of error, and whether overfitting occurs.

Machine Learning Studio (classic) supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module. Modules can be modified, added, or removed without breaking the rest of your experiment.

Use the modules in this category to select an initial algorithm. Then, configure detailed parameters based on the specific model type. You can then apply this model specification to a set of data.

## About creating models

Machine Learning provides many state-of-the art machine learning algorithms to help you build analytical models. Each algorithm is packaged in its own module. To create a customized model:

1. Choose a model by category.

    Algorithms are grouped by specific types of predictive tasks. Examples include regression, classification, and image recognition. Your first task is to identify the general category of machine learning task to perform, and then to select an algorithm. 
 
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
