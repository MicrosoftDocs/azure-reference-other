---
title: "Permutation Feature Importance | Microsoft Docs"
ms.custom: ""
ms.date: 10/11/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2e010ee4-714e-44e9-933e-62d8c41818a9
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Permutation Feature Importance
*Computes the permutation feature importance scores of feature variables given a trained model and a test dataset*  
  
 Category: [Feature Selection Modules](feature-selection-modules.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the [Permutation Feature Importance](permutation-feature-importance.md) module to compute a set of feature importance scores for your dataset, based on how much the performance of a model based on the dataset changes when the feature values are randomly shuffled.  
  
 The scores that the module returns represent the change in the performance of a trained model, after permutation. You can configure the module to use any one of several standard performance metrics used for evaluation.  
  
 The module requires that you provide a test dataset, as well as an existing trained classification or regression model.  
  
## Understanding Permutation Feature Importance  
 Permutation feature importance works by randomly changing the values of each feature column, one column at a time, and then evaluating the input model. Important features are usually more sensitive to the shuffling process, and will thus result in higher importance scores.  
  
 This article provides a good general overview of permutation feature importance, its theoretical basis, and its applications in machine learning: [Permutation feature importance](http://blogs.technet.com/b/machinelearning/archive/2015/04/14/permutation-feature-importance.aspx)  
  
## How to Use Permutation Feature Importance  
 To generate a set of feature scores requires that you have an already trained model, as well as a test dataset.  
  
1.  Add the **Permutation Feature Importance** module to your experiment.  
  
2.  To the left input, connect a trained model.  
  
     The model must be a regression model or classification model.  
  
3.  To the right input, connect a dataset, preferably one that is different from the dataset used for training the model. This dataset is used for scoring based on the trained model, and for evaluating the model after feature values have been changed.  
  
4.  For **Random seed**, type a value to use as seed for randomization. If you specify 0 (the default), a number is generated based on the system clock.  
  
     A value is optional but you should provide a value if you want reproducibility across runs of the same experiment.  
  
5.  For **Metric for measuring performance**, select a single metric to use when computing model quality after permutation.  
  
     Azure Machine Learning Studio supports the following metrics, depending on whether you are evaluating a classification or regression model:  
  
    -   **Classification**
    
        Accuracy, Precision, Recall, Average Log Loss  
  
    -   **Regression**
    
        Precision, Recall, Mean Absolute Error , Root Mean Squared Error, Relative Absolute Error, Relative Squared Error, Coefficient of Determination  
  
     For a more detailed description of these evaluation metrics, and how they are calculated, see [Evaluate](machine-learning-evaluate.md).  
  
6.  Run the experiment.  
  
7.  The module outputs a list of feature columns and the scores associated with them, ranked in order of the scores, descending.  
  
## Examples  
 To see examples of how feature selection is used in machine learning, see these sample experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Permutation Feature Importance](https://gallery.cortanaintelligence.com/Experiment/e2ccb5a5d9dc480489ba8ff0b7eb98ac) sample demonstrates how to use this module to rank feature variables of a dataset in order of permutation importance scores.  
  
-   The [Using the Permutation Feature Importance module](https://gallery.cortanaintelligence.com/Experiment/4802f138edcb4582a877018460edd943) sample illustrates the usage of this module in a web service.  
  
##  <a name="Notes"></a> Technical Notes  
 the rankings provided by permutation feature importance are often different from the ones you get from [Filter Based Feature Selection](filter-based-feature-selection.md), which calculates scores **before** a model is created. This is because permutation feature importance doesn’t measure the association between a feature and a target value, but instead captures how much influence each feature has on predictions from the model.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|A trained classification or regression model|  
|Test data|[Data Table](data-table.md)|Test dataset for scoring and evaluating a model after permutation of feature values|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Random seed|Integer|>=0|Required|0|Random number generator seed value|  
|Metric for measuring performance|EvaluationMetricType|select from list|Required|Classification - Accuracy|Select the metric to use when evaluating the variability of the model after permutations|
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Feature importance|[Data Table](data-table.md)|A dataset containing the feature importance results, based on the selected metric|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0062](errors/error-0062.md)|Exception occurs when attempting to compare two models with different learner types.|  
|[Error 0024](errors/error-0024.md)|Exception occurs if dataset does not contain a label column.|  
|[Error 0105](errors/error-0105.md)|Thrown when a module definition file defines an unsuppported parameter type|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
  
## See Also  
 [Feature Selection](feature-selection-modules.md)   
 [Filter Based Feature Selection](filter-based-feature-selection.md)   
 [Principal Component Analysis](principal-component-analysis.md)