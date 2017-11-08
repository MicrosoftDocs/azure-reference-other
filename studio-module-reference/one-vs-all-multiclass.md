---
title: "One-vs-All Multiclass | Microsoft Docs"
ms.custom: ""
ms.date: 10/05/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7191efae-b4b1-4d03-a6f8-7205f87be664
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# One-vs-All Multiclass
*Creates a multiclass classification model from an ensemble of binary classification models*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the **One-Vs-All Multiclass** module in Azure Machine Learning Studio to create a classification model that can predict multiple classes.  
  
This classifier must be connected to an existing **binary classification** algorithm. You configure the two-class model, and then train the combination of models by using [Train Model](train-model.md) with a labeled training dataset. 

When you combine the models, even though the training dataset might have multiple class values, the **One-Vs-All Multiclass** creates multiple binary classification models, optimizes the algorithm for each class, and then merges the models.  

  
This module is useful for creating models that predict three or more possible outcomes, when the outcome depends on continuous or categorical predictor variables. This method also lets you use binary classification methods for issues that require multiple output classes.  
  
## Understanding the One-vs-All Classifier  

While some classification algorithms permit the use of more than two classes by design, others restrict the possible outcomes to one of two values (a binary, or two-class model. However, even binary classification algorithms can be adapted for multi-class classification tasks using a variety of strategies. 

This module implements the *one vs. all method*, in which a binary model is created for each of the multiple output classes. Each of these binary models for the individual classes is assessed against its complement (all other classes in the model) as though it were a binary classification issue. Prediction is then performed by running these binary classifiers, and choosing the prediction with the highest confidence score.  
  
In essence, an ensemble of individual models is created and the results are then merged, to create a single model that predicts all classes. Thus, any binary classifier can be used as the basis for a one-vs-all model.  
  
 For example, let’s say you configure a [Two-Class Support Vector Machine](two-class-support-vector-machine.md) model and provide that as input to the **One-Vs-All Multiclass** module. The module would create two-class support vector machine models for all members of the output class and then apply the one-vs-all method to combine the results for all classes.  
  
## How to Configure the One-vs-All Classifier  
  
1.  Add the **One-Vs-All Multiclass** to your experiment.  
  
2.  Add one of the two-class classification models to the experiment, and configure that model.  
  
     For example, you might use a [Two-Class Support Vector Machine](two-class-support-vector-machine.md) or [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md) tree model.  
  
    > [!WARNING]
    >  Need help choosing the right algorithm? See these resources:  
    >   
    >  -   [Machine learning algorithm cheat sheet for Azure ML](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-cheat-sheet/)  
    > -   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
  
     Note that the **One-Vs-All Multiclass** classifier has no configurable parameters of its own. Any customizations must be done in the model that is provided as input.  
  
3.  Connect the untrained classifier that is the output of **One-Vs-All Multiclass** to [Train Model](train-model.md).  
  
     On the other input of [Train Model](train-model.md), connect a labeled training data set that has multiple class values.  
  
4.  To train the classification model, run the experiment, or select **Train Mode**l and click **Run Selected**.

     Alternatively, you can pass the untrained classifier to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled validation data set.  

5. After the classifier has been trained, you can use the model to make multiclass predictions.  
  
  
## Examples  
 For examples of how this learning algorithm is used, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [News Categorization](http://go.microsoft.com/fwlink/?LinkId=525167) sample uses **One-Vs-All Multiclass** with a [Two-Class Decision Forest](two-class-decision-forest.md) model.  
  
-   In the [Compare Multiclass Classifier sample](http://go.microsoft.com/fwlink/?LinkId=525730), binary classifiers are used for each digit and the results combined.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained binary classification model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification|  
  
##  <a name="exceptions"></a> Exception  

For a list of all error messages, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0013](error-0013.md)|An exception occurs if the learner that was passed to the module is the wrong type.|  
  
## See Also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)