---
title: "Machine Learning - Evaluate | Microsoft Docs"
ms.custom: ""
ms.date: 04/27/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ea496474-d04c-474f-896f-3f4531cd8be0
caps.latest.revision: 24
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning - Evaluate

This section describes the modules that are provided in Azure Machine Learning Studio to help you measure the accuracy of predictive models and assess model fit.

In general, when evaluating a model, you have the following options, depending on the type of model you are evaluating, and the metric you want to use:

+ In most cases, you will use the generic [Evaluate Model](evaluate-model.md) module, especially if your model is based on one of the supported classification or regression algorithms. 

+ Some models have special evaluation modules, or require special scoring modules to generate results that can be evaluated. 
  + For recommendation models, use the [Evaluate Recommender](evaluate-recommender.md) module.
  + For clustering models, use the [Assign Data to Clusters](assign-data-to-clusters.md) module, and then use the visualizations in that module to see evaluation results.

+ Use the [Cross Validate Model](cross-validate-model.md) module, if you want to test the validity of your training set and the model. Cross-validation partitions the data into some number of folds and then tests multiple models on combinations of folds.

+ Create your own evaluation metric, by providing R code in the [Execute R Script](execute-r-script.md) module, or Python code, in the [Execute Python Script](execute-python-script.md) module. This option is handy if you want to use metrics that were published as part of open source libraries, or if you want to design your own metric for measuring model accuracy. 

  The Cortana Intelligence Gallery contains multiple examples of custom R modules used for generating model metrics. 

## How to View Evaluation Results

All of the modules used for model evaluation output a dataset containing scores that you can use for further processing or analysis.

Additionally, Studio provides a variety of visualizations, depending on the type of model you are using, and how many classes your model is predicting. 

### View metrics for two-class classification models

+ Right-click the module output, and select **Visualize**.
+ Or, right-click the module, select **Evaluation results**, and then select **Visualize**. 

![evaluate_binaryclassification_defaultview](media/evaluate-binaryclassification-defaultview.JPG)

This is the default view for binary classification models, and includes an interactive ROC chart, together with a table of values for the principal metrics.  

You can also use the slider to change the probability **threshold** value, which determines whether a result should be accepted as true or not, and see how these values change:   


### View metrics for multi-class classification models

+ Right-click the module output, and select **Visualize**.
+ Or, right-click the module, select **Evaluation results**, and then select **Visualize**. 

![evaluate_multiclass_view](media/evaluate-multiclass-view.JPG)

The default metrics view for multi-class classification models (shown here side-by-side) includes a confusion matrix for all classes, and a set of metrics for the model as a whole.  

### View metrics for regression models

+ To view the accuracy metrics in a table, right-click the **Evaluate Model** module's output, and select **Visualize**.
+ To view an error histogram together with the values, right-click the **module itself**, select **Evaluation results**, and then select **Visualize**.  

The default metrics view for regression models differs depending on the type of model you created. This is due to the underlying algorithm interfaces, as well as best fit for the model metrics.  

The **error histogram** helps you understand how error is distributed, and is provided for the following model types, with a table of default metrics such as root mean squared error (RMSE).

+ [Boosted Decision Tree Regression](boosted-decision-tree-regression.md)
+ [Linear Regression](linear-regression.md)
+ [Neural Network Regression](neural-network-regression.md)

![error-histogram-linear-regression](media/error-histogram-linear-regression.JPG)

The following types of regression models provide a table of default metrics, along with some custom metrics, in a tabular format:
+ [Bayesian Linear Regression](bayesian-linear-regression.md)
+ [Decision Forest Regression](decision-forest-regression.md)
+ [Fast Forest Quantile Regression](fast-forest-quantile-regression.md)
+ [Ordinal Regression](ordinal-regression.md)  

>[!TIP]
> 
> Want to pull the numbers out without using copy-paste from the Studio UI? You can use the new [PowerShell library for Azure ML](https://github.com/hning86/azuremlps) to get metadata and other information for an entire experiment, or from individual modules.
> 
> To extract values from an Evaluate Model module, you must add a unique comment to the module, for easier identification. Then, use the **Download-AmlExperimentNodeOutput** cmdlet to get the metrics and their values from the visualization in JSON format.
> 
> For more information, see [Create Machine Learnign Models using PowerShell](https://docs.microsoft.com/azure/machine-learning/machine-learning-create-models-and-endpoints-with-powershell).
  
## Interpreting Metrics  

The accuracy metrics provided for each model differ depending on the type of model you are using, and how many classes your model is predicting. These topics list some of the most used metrics.

+ [Evaluate Model](evaluate-model.md) 
+ [Cross Validate Model ](cross-validate-model.md)

However, interpreting these statistics often requires a greater understanding of the particular algorithm on which the model was trained.

For a general explanation of how to evaluate a model, and how to interpret the values that are returned for each measure, we recommend that you read this article: [How to evaluate model performance in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-evaluate-model-performance).  
 

  
## Examples
  
Interpreting the results of evaluation of machine learning models is an art, one that requires understanding the mathematical results as well as the data and the business problems. We recommend that you review these articles for an explanation of how to interpret results in different scenarios:  
  
-   [How to choose parameters to optimize your algorithms in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-parameters-optimize)  
  
-   [How to interpret model results in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-interpret-model-results)  
  
-   [How to evaluate model performance in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-evaluate-model-performance)  



##  <a name="modules"></a> List of Modules  
 The Evaluate category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Cross-Validate Model](cross-validate-model.md)|Cross validates parameter estimates for classification or regression models by partitioned the data|  
|[Evaluate Model](evaluate-model.md)|Evaluates a scored classification or regression model with standard metrics|  
|[Evaluate Recommender](evaluate-recommender.md)|Evaluates the accuracy of recommender model predictions|  
  
## See Also  
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Train](machine-learning-train.md)   
 [Score](machine-learning-score.md)   
 [Evaluate](machine-learning-evaluate.md)   
 [A-Z Module List](a-z-module-list.md)