---
title: "ML Studio (classic): One-vs-All Multiclass - Azure"
description: Learn how to use the One-Vs-All Multiclass module to create a classification model that can predict multiple classes, using the "one vs. all" approach.
ms.date: 07/03/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# One-vs-All Multiclass

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a multiclass classification model from an ensemble of binary classification models*

Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **One-Vs-All Multiclass** module in Machine Learning Studio (classic), to create a classification model that can predict multiple classes, using the "one vs. all" approach.

This module is useful for creating models that predict three or more possible outcomes, when the outcome depends on continuous or categorical predictor variables. This method also lets you use binary classification methods for issues that require multiple output classes.

### More about one-vs.all models

While some classification algorithms permit the use of more than two classes by design, others restrict the possible outcomes to one of two values (a binary, or two-class model). However, even binary classification algorithms can be adapted for multi-class classification tasks using a variety of strategies. 

This module implements the *one vs. all method*, in which a binary model is created for each of the multiple output classes. Each of these binary models for the individual classes is assessed against its complement (all other classes in the model) as though it were a binary classification issue. Prediction is then performed by running these binary classifiers, and choosing the prediction with the highest confidence score.  
  
In essence, an ensemble of individual models is created and the results are then merged, to create a single model that predicts all classes. Thus, any binary classifier can be used as the basis for a one-vs-all model.  
  
 For example, let’s say you configure a [Two-Class Support Vector Machine](two-class-support-vector-machine.md) model and provide that as input to the **One-Vs-All Multiclass** module. The module would create two-class support vector machine models for all members of the output class and then apply the one-vs-all method to combine the results for all classes.  
  
## How to Configure the One-vs-All Classifier  

This module creates an ensemble of binary classification models to analyze multiple classes. Therefore, to use this module, you need to configure and train a **binary classification** model first. 

You then connect the binary model to **One-Vs-All Multiclass** module, and train the ensemble of models by using [Train Model](train-model.md) with a labeled training dataset.

When you combine the models, even though the training dataset might have multiple class values, the **One-Vs-All Multiclass** creates multiple binary classification models, optimizes the algorithm for each class, and then merges the models.

1. Add the **One-Vs-All Multiclass** to your experiment in Studio (classic). You can find this module under Machine Learning - Initialize, in the **Classification** category.

    The **One-Vs-All Multiclass** classifier has no configurable parameters of its own. Any customizations must be done in the binary classification model that is provided as input.

2. Add a binary classification model to the experiment, and configure that model. For example, you might use a [Two-Class Support Vector Machine](two-class-support-vector-machine.md) or [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md).

    If you need help choosing the right algorithm, see these resources:
    
    - [Machine learning algorithm cheat sheet for Azure ML](/azure/machine-learning/studio/algorithm-cheat-sheet)  
    - [How to choose algorithms for Machine Learning Studio (classic)](/azure/machine-learning/studio/algorithm-choice)

3. Add the [Train Model](train-model.md) module to your experiment, and connect the untrained classifier that is the output of **One-Vs-All Multiclass**.

4. On the other input of [Train Model](train-model.md), connect a labeled training data set that has multiple class values.

5. Run the experiment, or select **Train Mode**l and click **Run Selected**.

### Results

After training is complete, you can use the model to make multiclass predictions.

Alternatively, you can pass the untrained classifier to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled validation data set.

## Examples

For examples of how this learning algorithm is used, see the [Azure AI Gallery](https://gallery.azure.ai/):

- [News Categorization](https://go.microsoft.com/fwlink/?LinkId=525167): This sample uses **One-Vs-All Multiclass** with a [Two-Class Decision Forest](two-class-decision-forest.md) model.

- [Compare Multiclass Classifier sample](https://go.microsoft.com/fwlink/?LinkId=525730): Binary classifiers are used for each digit and the results are combined.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained binary classification model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0013](errors/error-0013.md)|An exception occurs if the learner that was passed to the module is the wrong type.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Classification](machine-learning-initialize-model-classification.md)   
