---
title: "Machine Learning - Evaluate | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ea496474-d04c-474f-896f-3f4531cd8be0
caps.latest.revision: 24
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Machine Learning - Evaluate

This article describes the modules provided in Azure Machine Learning Studio for evaluating a machine learning model. _Model evaluation_ is performed after training is complete, to measure the accuracy of the predictions and assess model fit.

This article also describes the overall process in Studio for model creation, training, evaluation, and scoring.

## Creating and using machine learning models in Studio

The typical workflow for machine learning includes these phases:

- Choosing a suitable alorithm, and setting initial options
- Training the model on compatible data
- Creating predictions using new data, based on the patterns in the model
- Evaluating the model to determine if the predictions are accurate, how much error there is, and if there is any overfitting

Azure Machine Learning Studio supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module, which can be modified, added, re removed, without breaking the rest of your experiment. 

You use the modules in this category to evaluate an existing model. Model evaluation typically requires some kind of result dataset. If you do not have an evaluation datset, you can generate results by scoring. You can also use a test dataset, or some other set of data that contains "ground truth", or known expected results.

### More about model evaluation

In general, when evaluating a model, your options depend on the type of model you are evaluating, and the metric you want to use. These topics list some of the most used metrics.

+ [Evaluate Model](evaluate-model.md) 
+ [Cross Validate Model ](cross-validate-model.md)

Additionally, Studio provides a variety of visualizations, depending on the type of model you are using, and how many classes your model is predicting. For help finding these visualizations, see [View evaluation metrics](#bkmk_ViewMetrics).

Interpreting these statistics often requires a greater understanding of the particular algorithm on which the model was trained. For a good explanation of how to evaluate a model, and how to interpret the values that are returned for each measure, we recommend this article: [How to evaluate model performance in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-evaluate-model-performance).

##  <a name="modules"></a> List of modules

The Evaluate category includes the following modules:

+ [Cross-Validate Model](cross-validate-model.md): Cross validates parameter estimates for classification or regression models by partitioned the data

    Use the [Cross Validate Model](cross-validate-model.md) module, if you want to test the validity of your training set and the model. Cross-validation partitions the data into some number of folds and then tests multiple models on combinations of folds.

+ [Evaluate Model](evaluate-model.md): Evaluates a scored classification or regression model with standard metrics.

    In most cases, you will use the generic [Evaluate Model](evaluate-model.md) module, especially if your model is based on one of the supported classification or regression algorithms. 

+ [Evaluate Recommender](evaluate-recommender.md): Evaluates the accuracy of recommender model predictions

    For recommendation models, use the [Evaluate Recommender](evaluate-recommender.md) module.

### Related tasks

+ For clustering models, use the [Assign Data to Clusters](assign-data-to-clusters.md) module, and then use the visualizations in that module to see evaluation results.

+ You can create custom evaluation metrics, by providing R code in the [Execute R Script](execute-r-script.md) module, or Python code, in the [Execute Python Script](execute-python-script.md) module. This option is handy if you want to use metrics that were published as part of open source libraries, or if you want to design your own metric for measuring model accuracy. 

## Examples

Interpreting the results of evaluation of machine learning models is an art, one that requires understanding the mathematical results as well as the data and the business problems. We recommend that you review these articles for an explanation of how to interpret results in different scenarios:

-   [How to choose parameters to optimize your algorithms in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-parameters-optimize)  
  
-   [How to interpret model results in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-interpret-model-results)  
  
-   [How to evaluate model performance in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-evaluate-model-performance)  

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### <a name="bkmk_ViewMetrics"></a> How to view evaluation metrics

This section describes where to look in Studio to find the metric charts for each model type.

### Two-class classification models

The default view for binary classification models includes an interactive ROC chart, together with a table of values for the principal metrics.

![evaluate_binaryclassification_defaultview](media/evaluate-binaryclassification-defaultview.JPG)

+ Right-click the module output, and select **Visualize**.
+ Or, right-click the module, select **Evaluation results**, and then select **Visualize**.

You can also use the slider to change the probability **threshold** value, which determines whether a result should be accepted as true or not, and see how these values change.

### Multiclass classification models

The default metrics view for multi-class classification models includes a confusion matrix for all classes, and a set of metrics for the model as a whole.

+ Right-click the module output, and select **Visualize**.
+ Or, right-click the module, select **Evaluation results**, and then select **Visualize**. 

For simplicity, here the two results are shown side-by-side:

![evaluate_multiclass_view](media/evaluate-multiclass-view.JPG)

### Regression models

The metrics view for regression models is different depending on the type of model you created. This is due to the underlying algorithm interfaces, as well as best fit for the model metrics.

+ To view the accuracy metrics in a table, right-click the **Evaluate Model** module's output, and select **Visualize**.
+ To view an error histogram together with the values, right-click the **module itself**, select **Evaluation results**, and then select **Visualize**.  

![error-histogram-linear-regression](media/error-histogram-linear-regression.JPG)

The **error histogram** helps you understand how error is distributed, and is provided for the following model types, with a table of default metrics such as root mean squared error (RMSE).

+ [Boosted Decision Tree Regression](boosted-decision-tree-regression.md)
+ [Linear Regression](linear-regression.md)
+ [Neural Network Regression](neural-network-regression.md)

The following regression models generate a table of default metrics, along with some custom metrics:

+ [Bayesian Linear Regression](bayesian-linear-regression.md)
+ [Decision Forest Regression](decision-forest-regression.md)
+ [Fast Forest Quantile Regression](fast-forest-quantile-regression.md)
+ [Ordinal Regression](ordinal-regression.md)  

### Usage tips

To pull the numbers out without using copy-paste from the Studio UI, you can use the new [PowerShell library for Azure ML](https://github.com/hning86/azuremlps). You can toget metadata and other information for an entire experiment, or from individual modules.

To extract values from an Evaluate Model module, you must add a unique comment to the module, for easier identification. Then, use the **Download-AmlExperimentNodeOutput** cmdlet to get the metrics and their values from the visualization in JSON format.

For more information, see [Create Machine Learnign Models using PowerShell](https://docs.microsoft.com/azure/machine-learning/machine-learning-create-models-and-endpoints-with-powershell).

## See also  
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Train](machine-learning-train.md)   
 [Score](machine-learning-score.md)   
 [Evaluate](machine-learning-evaluate.md)   
 [A-Z Module List](a-z-module-list.md)