---
title: "ML Studio (classic): Train - Azure"
description: This article describes the modules provided in Machine Learning Studio (classic) for training a machine learning model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Machine Learning - Train

This article describes the modules provided in Machine Learning Studio (classic) for training a machine learning model. _Training_ is the process of analyzing input data by using the parameters of a predefined model. From this analysis, the model learns the patterns, and saves them in the form of a trained model.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article also describes the overall process in Machine Learning Studio (classic) for model creation, training, evaluation, and scoring.

## Create and use machine learning models

The typical workflow for machine learning includes these phases:

- Choosing a suitable algorithm, and setting initial options.
- Training the model on compatible data.
- Creating predictions by using new data, based on the patterns in the model.
- Evaluating the model to determine if the predictions are accurate, how much error there is, and if there is any overfitting.

Machine Learning Studio (classic) supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module, which can be modified, added, or removed, without breaking the rest of your experiment. 

The modules in this category support training for different types of models. During training, the data is analyzed by the machine learning algorithm. This algorithm analyzes the distribution and type of the data, compiles statistics, and creates patterns that can be used later for prediction.

## More about model training

When Machine Learning is training a model, rows with missing values are skipped. Therefore, if you want to fix the values manually, use imputation, or specify a different method for handling missing values, use the [Clean Missing Data](clean-missing-data.md) module before training on the dataset.

We recommend that you use the [Edit Metadata](edit-metadata.md) module to fix any other issues with the data. You might need to mark the label column, change data types, or correct column names.

For other common data cleanup tasks, such as normalization, sampling, binning, and scaling, see the [Data Transformation](data-transformation.md) category.

### Choose the right trainer

The method that you use to train a model depends on the type of model you are creating, and the type of data that the model requires. For example, Machine Learning provides modules specifically for training anomaly detection models, recommendation models, and more.

Check the [list of training modules](#bkmk_ModList) to determine which one is correct for your scenario.

If you are not sure of the best parameters to use when training a model, use one of the modules provided for parameter sweeping and validation:

+  [Tune Model Hyperparameters](tune-model-hyperparameters.md) can perform a parameter sweep on almost all classification and regression models. It trains multiple models, and then returns the best model. 

+ The [Sweep Clustering](sweep-clustering.md) module supports model tuning during the training process, and is intended for use only with clustering models. You can specify a range of centroids, and train on data while automatically detecting the best parameters.

+ The [Cross-Validate Model](cross-validate-model.md) module is also useful for model optimization, but does not return a trained model. Instead, it provides metrics that you can use to determine the best model.

### Retrain models

If you need to retrain a production model, you can re-run the experiment at any time.

You can also automate the retraining process by using web services. For a walkthrough, see [Retraining and updating Machine Learning models with Azure Data Factory](https://azure.microsoft.com/blog/retraining-and-updating-azure-machine-learning-models-with-azure-data-factory/).

### Use pretrained models

Machine Learning includes some models that are pretrained, such as the [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md) module. You can use these models for scoring without additional data input.

Also, some modules (such as [Time Series Anomaly Detection](time-series-anomaly-detection.md)) do not generate a trained model in the iLearner format. But they do take training data and create a model internally, which can then be used to make predictions. To use these, you just configure the parameters and provide data. 

### Save a snapshot of a trained model

If you want to save or export the model, right-click the training module, and select **Save as Trained Model**. The model is exported to the iLearner format and saved in your workspace, under **Trained Models**. Trained models can be re-used in other experiments, or connected to other modules for scoring.

You can also use the [Load Trained Model](load-trained-model.md) module in an experiment to retrieve a stored model.

## <a name = "bkmk_ModList"></a> List of modules

The **Train** category includes these modules:

+ [Sweep Clustering](sweep-clustering.md): Performs a parameter sweep on a clustering model to determine the optimum parameter settings, and trains the best model.
+ [Train Anomaly Detection Model](train-anomaly-detection-model.md): Trains an anomaly detector model and labels data from a training set.
+ [Train Clustering Model](train-clustering-model.md): Trains a clustering model and assigns data from the training set to clusters.
+ [Train Matchbox Recommender](train-matchbox-recommender.md): Trains a Bayesian recommender by using the Matchbox algorithm.
+ [Train Model](train-model.md): Trains a classification or regression model from a training set.
+ [Tune Model Hyperparameters](tune-model-hyperparameters.md): Performs a parameter sweep on a regression or classification model to determine the optimum parameter settings, and trains the best model.

## Related tasks

Some modules are not in this category, because they require a special format or are customized for a specific task:

+ [Train Anomaly Detection Model](train-anomaly-detection-model.md)
+ [Train Vowpal Wabbit Version 7-4](train-vowpal-wabbit-version-7-4-model.md) 
+ [Train Vowpal Wabbit Version 7-10](train-vowpal-wabbit-version-7-10-model.md)
+ [Train Vowpal Wabbit Version 8](train-vowpal-wabbit-version-8-model.md)
+ [Latent Dirichlet Allocation](latent-dirichlet-allocation.md)

## See also

- [Evaluate](machine-learning-evaluate.md)

- [Initialize Model](machine-learning-initialize-model.md)
