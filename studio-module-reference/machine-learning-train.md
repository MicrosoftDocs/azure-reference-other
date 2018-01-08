---
title: "Machine Learning - Train | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a85a6491-fe78-4461-ba01-2f798a9e3927
caps.latest.revision: 27
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Machine Learning - Train
This article describes the process for training a model in Azure Machine Learning Studio. It also lists the modules used for training different types of models.

## Training concepts

For your machine learning model to provide predictions, the model must first learn from known data in a process known as *training*. During training, the data is evaluated by the machine learning algorithm, which analyzes the distribution and type of the data, compiling statistics and looking for rules and patterns that can be used later for prediction. 

### Tasks to do before training

When Azure Machine Learning is training a model, rows with **missing values** are skipped. Therefore, if you want to manually fix the values, use imputation, or specify a differnt method for handling missing values, use [Clean Missing Data](clean-missing-data.md) module before training on the dataset.

We also recommend that you use the [Edit Metadata](edit-metadata.md) module to fix any other issues with the data, such as flagging the label column, changing data types, or correcting  column names.

Other common data tasks such as normalization, sampling, binning, and scaling are supported by the [Data Transformation](data-transformation.md) modules.

### Choose a training method by model type

The method that you use to train a model depends on the type of model you are creating, and the type of data that the model requires. For example, Azure Machine Learning provides modules specifically for training anomaly detection models, recommendation models, and more.

Check the [list of training modules](#bkmk_ModList) to determine which one is correct for your scenario.

### Tuning and model validation during and after training

If you are not sure of the best parameters ot use when training a model, we recommend that you use one of the modules provides for parameter sweeping and validation.

+  [Tune Model Hyperparameters](tune-model-hyperparameters.md) can perform a parameter sweep on almost all classification and regression models. It trains multiple models and then returns the best model. 

+ The [Sweep Clustering](sweep-clustering.md) module supports model tuning during the training process, and is intended for use only with clustering models. You can specify a rnage of centroids and train on data while automatically detecting the best parameters.

+ The [Cross-Validate Model](cross-validate-model.md) module is also useful for model optimization but does not return a trained model; instead, it provides metrics that you can use to determine the best model.

### Retraining models

If you need to retrain a production model, you can re-run the experiment at any time.

You can also automate the retraining process by using web services. See this article for a walkthrough on how you can automatically retrain and update models using Azure Data Factory: [Retraining and Updating Azure Machine Learning models with Azure Data Factory](https://azure.microsoft.com/blog/retraining-and-updating-azure-machine-learning-models-with-azure-data-factory/)


### Using pretrained models

Azure Machine Learning includes some models that are pre-trained, such as the [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md) module. You can use these models for scoring without additional data input.

Also, some modules (such as [Time Series Anomaly Detection](time-series-anomaly-detection.md)) do not generate a trained model in the iLearner format, yet take training data and create amodel internally, which can then be used to make predictions. To use these you just confugure the parameters and provide data. 

### Saving a snapshot of a trained model

If you want to save or export the model, right-click the training module and select **Save as Trained Model**. The model is exported to the iLearner format and saved in your workspace, under **Trained Models**. Trained models can be re-used in other experiments or connected to other modules for scoring.

You can also use the [Load Trained Model](load-trained-model.md) module in an experiment to retrieve a stored model.

## <a name = "bkmk_ModList"> </a>Training Modules

The **Train** category includes these modules:

|Module|Description|
|------------|-----------------|
|[Sweep Clustering](sweep-clustering.md)|Performs a parameter sweep on a clustering model to determine the optimum parameter settings, and trains the best model|
|[Train Anomaly Detection Model](train-anomaly-detection-model.md)|Trains an anomaly detector model and labels data from a training set|
|[Train Clustering Model](train-clustering-model.md)|Trains a clustering model and assigns data from the training set to clusters|
|[Train Matchbox Recommender](train-matchbox-recommender.md)|Trains a Bayesian recommender using the Matchbox algorithm|
|[Train Model](train-model.md)|Trains a classification or regression model from a training set|
|[Tune Model Hyperparameters](tune-model-hyperparameters.md)|Performs a parameter sweep on a regression or classification model to determine the optimum parameter settings, and trains the best model|

## Related training tasks

Some modules require a special format or are customized for a specific task, and are not listed with the other training modules in the table. See the following documentation links for details of how to train these model types:

+ [Train Anomaly Detection Model](train-anomaly-detection-model.md)
+ [Train Vowpal Wabbit Version 7-4](train-vowpal-wabbit-version-7-4-model.md) 
+ [Train Vowpal Wabbit Version 7-10](train-vowpal-wabbit-version-7-10-model.md)
+ [Train Vowpal Wabbit Version 8](train-vowpal-wabbit-version-8-model.md)
+ [Latent Dirichlet Allocation](latent-dirichlet-allocation.md)


## See Also

[Evaluate](machine-learning-evaluate.md)

[Initialize Model](machine-learning-initialize-model.md)
