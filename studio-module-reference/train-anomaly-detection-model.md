---
title: "Train Anomaly Detection Model | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/17/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d6acbace-a72d-44b9-9878-869115e02458
caps.latest.revision: 11
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Train Anomaly Detection Model
*Trains an anomaly detection model on a training set*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  
  
## Module overview

This article describes how to use the **Train Anomaly Detection Model** module in Azure Machine Learning to create a trained anomaly detection model.

The module takes as input a set of model parameters for anomaly detection model, such as that produced by the [One-Class Support Vector Machine](one-class-support-vector-machine.md) module, and an unlabeled dataset. It returns a trained anomaly detection model, together with a set of labels for the training data.  

For more information about the anomaly detection algorithms provided in Azure Machine Learning, see these topics: 

+ [One-Class Support Vector Machine](one-class-support-vector-machine.md)
  
+ [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md)  

## How to configure Train Anomaly Detection Model 

1.  Add the **Train Anomaly Detection Model** module to your experiment in Studio.  You can find the module under **Machine Learning**, in the **Train** category.

2. Connect one of the modules designed for anomaly detection, such as [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md) or [One-Class Support Vector Machine](one-class-support-vector-machine.md).  
  
    Other types of models are not supported; on running the experiment you will get the error: All models must have the same learner type.  
  
3.  Configure the anomaly detection module by choosing the label column and setting other parameters specific to the algorithm.  
  
4.  Attach a training dataset to the right-hand input of **Train Anomaly Detection Model**.  
  
5.  Run the experiment.  
  
### Results

After training is complete:

+ To view the model's parameters, right-click the module and select **Visualize**. 

+ To create predictions, use [Score Model](score-model.md) with new input data.

+ To save a snapshot of the trained model, right-click the **Trained Model** output, and select **Save As**.   

## Examples

For an example of how anomaly detection is implemented in Azure Machine Learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):  
  
- [On-line Fraud Detection](http://go.microsoft.com/fwlink/?LinkId=525964): Provides a detailed walkthrough of an anomaly detection scenario, including how to engineer features and interpret the results of an algorithm.  
  
- [Anomaly Detection: Credit Risk](https://gallery.azureml.net/Experiment/1219e87f8fb84e88a2e1b54256808bb3): Illustrates how to use the [One-Class Support Vector Machine](one-class-support-vector-machine.md) and [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md) modules for fraud detection.  
  
##  Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|Untrained anomaly detection model|  
|Dataset|[Data Table](data-table.md)|Input data source|  

##  Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained anomaly detection model|  
  
##  Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).  

## See also  
 [Train](machine-learning-train.md)   
 [Anomaly Detection](anomaly-detection.md)