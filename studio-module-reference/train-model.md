---
title: "Train Model | Microsoft Docs"
ms.custom: ""
ms.date: 08/22/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5cc7053e-aa30-450d-96c0-dae4be720977
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Train Model
*Trains a classification or regression model in a supervised manner*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  
  
##  <a name="Remarks"></a> Module Overview  
 
 This article describes how to use the **Train Model** module in Azure Machine Learning to train a classification or regression model.  
  
 Training a classification or regression model is a kind of *supervised machine learning*. That means you must provide a dataset that contains historical data from which to learn patterns. The data should contain both the outcome you are trying to predict, and related factors (variables). The machine learning model uses the data to extract statistical patterns and build a model.  
  
 Additionally, you must also connect an already configured model, such as a regression algorithm, decision tree model, or other machine learning module. For more information, see  [classification](machine-learning-initialize-model-classification.md) or [regression](machine-learning-initialize-model-regression.md).  
  
 After the model has been trained by processing all the data, the output is a trained model that you can evaluate, or use to create predictions.  
  
> [!TIP]
>  New to machine learning? This tutorial walks you through the process of getting data, configuring an algorithm, training and then using a model: [Create your first machine learning experiment](https://azure.microsoft.com/documentation/articles/machine-learning-create-experiment/)  

### Related Tasks

+ Create a custom model using R, or import a trained model from another R package and then do scoring or testing using R script.
    
    - [Create R Model](create-r-model.md) 
    - [Execute R Script](execute-r-script.md) 
+ Write your own Python script to train a model. Azure Machine Learning supports Anaconda 2 with Python 2.7, or Anaconda 4 with Python 2.7 or 3.5. 
    - [Execute Python Script](execute-python-script.md)

+ Depending on the type of model you are creating, you might need to use one of these specialized training modules:

   - [Train Anomaly Detection Model](train-anomaly-detection-model.md)   
   - [Train Matchbox Recommender](train-matchbox-recommender.md)   
   - [Train Clustering Model](train-clustering-model.md)  

## How to Train a Model  
  
1.  Add the **Train Model** module to the experiment.  You can find this module in Azure Machine Learning Studio under the **Machine Learning** category. Expand  **Train**, and then drag the **Train Model** module into your experiment.  
  
2.  On the left input, attach one of the [classification](machine-learning-initialize-model-classification.md) or [regression](machine-learning-initialize-model-regression.md) models provided in Azure Machine Learning Studio.  
  
     > [!TIP]
     > You can also train a custom model created by using [Create R Model](create-r-model.md).  
  
3.  Attach a training dataset to the right-hand input of **Train Model**.  
  
4.  For **Label column**, you must identify a single column that contains outcomes the model can use for training. Click **Launch column selector**, and choose the column in the dataset that contains the values you want to predict.  
  
    -   For classification problems, the label column must contain categorical values or discrete values. Some examples might be a yes/no rating, a disease classification code or name, or an income group.  If you pick a noncategorical column, the module will return an error during training.
  
    -   For regression problems, the label column must contain a numeric data that represents the response variable. Some examples might be a credit risk score, the projected time to failure for a hard drive, or the forecasted number of calls to a call center on a given day or time.  If you do not choose a numeric column, you might get an error.
  
    -   If you do not specify which label column to use, Azure Machine Learning will try to infer which is the appropriate label column, by using the metadata of the dataset. If it picks the wrong column, launch the column selector and choose a new column.  
  
    > [!TIP] 
    > If you have trouble using the Column Selector, see the article [Select Columns in Dataset](select-columns-in-dataset.md) for tips. It describes some common scenarios and tips for using the **WITH RULES** and **BY NAME** options.
  
5.  Run the experiment. If you have a lot of data, this can take a while.  
  
### Results

When the model is trained, right-click the output and select **Visualize** to view the model parameters and feature weights.  
  
You can also save the trained model to use in other experiments, or connect it to the [Score Model](score-model.md) module to predict values for new cases.  
  
## Examples  

 For examples of how the **Train Model** module is used in machine learning experiments, see these experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Retail Forecasting](http://go.microsoft.com/fwlink/?LinkId=525950) sample demonstrates how to build, train, and compare multiple models.  
  
-   The [Flight Delay Prediction](http://go.microsoft.com/fwlink/?LinkId=525725) sample demonstrates how to train multiple related classification models.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|Untrained learner|  
|Dataset|[Data Table](data-table.md)|Training data|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Label column|any|ColumnSelection||Select the column that contains the label or outcome column|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
  
##  <a name="exceptions"></a> Exceptions  

 For a list of all module errors, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0032](errors/error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](errors/error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0083](errors/error-0083.md)|Exception occurs if dataset used for training cannot be used for concrete type of learner.|  
|[Error 0035](errors/error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if passed to module learner has invalid type.|  
  
## See Also  
 
 [Evaluate Model](evaluate-model.md)   
 [A-Z Module List](a-z-module-list.md)