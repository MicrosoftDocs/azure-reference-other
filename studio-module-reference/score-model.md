---
title: "Score Model | Microsoft Docs"
ms.custom: ""
ms.date: 10/13/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 401b4f92-e724-4d5a-be81-d5b0ff9bdb33
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Score Model
*Scores predictions for a trained classification or regression model*  
  
 Category: [Machine Learning / Score](machine-learning-score.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use [Score Model](score-model.md) to generate predictions using a trained classification or regression model. The predicted value can be in many different formats, depending on the model and your input data:  
  
-   If you are using a classification model to create the scores, [Score Model](score-model.md) outputs a predicted value for the class, as well as the probability of the predicted value.  
  
-   For regression models, [Score Model](score-model.md) generates just the predicted numeric value.  
  
-   For image classification models, the score might be the class of object in the image, or a Boolean indicating whether a particular feature was found.  
  
 After you have generated a set of scores using [Score Model](score-model.md), you can connect the scored dataset to [Evaluate Model](evaluate-model.md), to generate a set of metrics used for evaluating the model’s accuracy (performance).  
  
 You can also save the results to a dataset, or use the output as part of a predictive web service. For more information, see [this tutorial](http://azure.microsoft.com/documentation/articles/machine-learning-walkthrough-5-publish-web-service/) on publishing a web service using Azure ML Studio.  
  
 **Models Not Supported by [Score Model](score-model.md)**  
  
 If you are using one of the following special types of model, you might need to use one of these custom scoring modules:  
  
-   Score a clustering model – [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)  
  
-   Create recommendations or generate data for evaluating a recommender -  [Score Matchbox Recommender](score-matchbox-recommender.md)  
  
## Example  
 For examples of how [Score Model](score-model.md) is used in an experimental workflow, see these examples in the [Model Gallery](http://azure.microsoft.com/documentation/services/machine-learning/models/):  
  
-   [Compare Binary Classification Models](http://go.microsoft.com/fwlink/?LinkId=525729)  
  
-   [Compare Multiclass Classification Models](http://go.microsoft.com/fwlink/?LinkId=525730)  
  
-   [Compare Multiple Regression Models](http://go.microsoft.com/fwlink/?LinkId=525731)  
  
## Technical Notes  
 If the data that you are scoring contains missing values, in many cases no score will be generated for the entire row.  
  
 The following machine learning models require that data have no missing values. When using the following machine learning models, review the data before passing it to [Score Model](score-model.md), and use [Clean Missing Data](clean-missing-data.md) to amend the missing values in input columns.  
  
-   [Two-Class Logistic Regression](two-class-logistic-regression.md)  
  
-   [Two-Class Support Vector Machine](two-class-support-vector-machine.md)  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained predictive model|  
|Dataset|[Data Table](data-table.md)|Input test dataset|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Scored dataset|[Data Table](data-table.md)|Dataset with obtained scores|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0032](errors/error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](errors/error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if the learner that is passed to the module is an invalid type.|  
  
## See Also  
 [Evaluate](machine-learning-evaluate.md)   
 [Train Model](train-model.md)   
 [Score Matchbox Recommender](score-matchbox-recommender.md)   
 [A-Z Module List](a-z-module-list.md)