---
title: "ML Studio (classic): Score Model - Azure"
description: Learn how to use the Score Model module to generate predictions using a trained classification or regression model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Score Model

*Scores predictions for a trained classification or regression model*

Category: [Machine Learning / Score](machine-learning-score.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Score Model](score-model.md) module in Machine Learning Studio (classic), to generate predictions using a trained classification or regression model.

## How to use Score Model

1. Add the **Score Model** module to your experiment in Studio (classic).

2. Attach a trained model and a dataset containing new input data. 

    The data should be in a format compatible with the type of trained model you are using. The schema of the input dataset should also generally match the schema of the data used to train the model.

3. Run the experiment.

### Results

After you have generated a set of scores using [Score Model](score-model.md):

+ To generate a set of metrics used for evaluating the model’s accuracy (performance).  you can connect the scored dataset to [Evaluate Model](evaluate-model.md), 
+ Right-click the module and select **Visualize** to see the a sample of the results.
+ Save the results to a dataset.

The score, or predicted value, can be in many different formats, depending on the model and your input data:

- For classification models, [Score Model](score-model.md) outputs a predicted value for the class, as well as the probability of the predicted value.
- For regression models, [Score Model](score-model.md) generates just the predicted numeric value.
- For image classification models, the score might be the class of object in the image, or a Boolean indicating whether a particular feature was found.

### Publish scores as a web service

A common use of scoring is to return the output as part of a predictive web service. For more information, see this tutorial on how to create a web service based on an experiment in Azure ML Studio (classic):

+ [Publish a web service from Azure ML Studio (classic)](/azure/machine-learning/classic/tutorial-part3-credit-risk-deploy)


## Examples

For examples of how [Score Model](score-model.md) is used in an experimental workflow, see the [Azure AI Gallery](https://azure.microsoft.com/documentation/services/machine-learning/models/):  

- [Compare Binary Classification Models](https://go.microsoft.com/fwlink/?LinkId=525729)
- [Compare Multiclass Classification Models](https://go.microsoft.com/fwlink/?LinkId=525730)
- [Compare Multiple Regression Models](https://go.microsoft.com/fwlink/?LinkId=525731)

## Technical notes

### Models not supported by Score Model

If you are using one of the following special types of model, you might need to use one of these custom scoring modules:

- Score a clustering model: Use [Assign Data to Clusters](assign-data-to-clusters.md).

- Create recommendations or generate data for evaluating a recommender: Use [Score Matchbox Recommender](score-matchbox-recommender.md)

### Usage tips

If the data that you are scoring contains missing values, in many cases no score will be generated for the entire row.

The following machine learning models require that data have no missing values. When using the following machine learning models, review the data before passing it to [Score Model](score-model.md), and use [Clean Missing Data](clean-missing-data.md) to amend the missing values in input columns.

- [Two-Class Logistic Regression](two-class-logistic-regression.md)
- [Two-Class Support Vector Machine](two-class-support-vector-machine.md)

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained predictive model|  
|Dataset|[Data Table](data-table.md)|Input test dataset|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Scored dataset|[Data Table](data-table.md)|Dataset with obtained scores|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0032](errors/error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](errors/error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if the learner that is passed to the module is an invalid type.|  

## See also

 [Evaluate](machine-learning-evaluate.md)   
 [Train Model](train-model.md)   
 [Score Matchbox Recommender](score-matchbox-recommender.md)
