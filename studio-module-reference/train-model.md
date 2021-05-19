---
title: "ML Studio (classic): Train Model - Azure"
description: Learn  how to use the Train Model module to train a classification or regression model. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Train Model
*Trains a classification or regression model in a supervised manner*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview
 
This article describes how to use the **Train Model** module in Azure Machine Learning Studio (classic) to train a classification or regression model. Training takes place after you have defined a model and set its parameters, and requires tagged data. You can also use **Train Model** to retrain an existing model with new data. 

### How the training process works

In Azure Machine Learning, creating and using a machine learning model is typically a three-step process. 

1. You configure a model, by choosing a particular type of algorithm, and defining its parameters or hyperparameters. Choose any of the following model types: 

    + [Classification models](machine-learning-initialize-model-classification.md), based on neural networks, decision trees, and decision forests, and other algorithms.
    + [Regression models](machine-learning-initialize-model-regression.md), which can include standard linear regression, or which use other algorithms, including neural networks and Baysian regression.  

2. Provide a dataset that is labeled, and has data compatible with the algorithm. Connect both the data and the model to **Train Model**.

    What training produces is a specific binary format, the [iLearner](ilearner-interface.md), that encapsulates the statistical patterns learned from the data. You cannot directly modify or read this format; however, other modules in Studio (classic) can use this trained model. 
    
    You can also view properties of the model. For more information, see the [Results](#bkmk_results) section.

3. After training is completed, use the trained model with one of the [scoring modules](machine-learning-score.md), to make predictions on new data.

> [!NOTE]
> Other specialized machine learning tasks require different training methods, and Studio (classic) provides separate training modules for them. For example, image detection, clustering, and anomaly detction all use custom training methods. **Train Model** is intended for use with regression and classification models only.

### Supervised and unsupervised training

You might have heard the terms _supervised_ or _unsupervised_ learning. Training a classification or regression model with **Train Model** is a classic example of *supervised machine learning*. That means you must provide a dataset that contains historical data from which to learn patterns. The data should contain both the outcome (label) you are trying to predict, and related factors (variables). The machine learning model needs the outcomes to determine the features that best predict the outcomes.

During the training process, the data are sorted by outcomes and the algorithm extracts statistical patterns to build the model.

_Unsupervised learning_ indicates either that the outcome is unknown, or you choose not to use known labels. For example, clustering algorithms usually employ unsupervised learning methods, but can use labels if available. Another example is topic modeling using [LDA](latent-dirichlet-allocation.md). You cannot use **Train Model** with these algorithms.

> [!TIP]
>  New to machine learning? This tutorial walks you through the process of getting data, configuring an algorithm, training and then using a model: [Create your first machine learning experiment](/azure/machine-learning/classic/create-experiment)  

## How to use **Train Model**  
  
1.  In Azure Machine Learning Studio (classic), configure a [classification model](machine-learning-initialize-model-classification.md) or [regression model](machine-learning-initialize-model-regression.md) models.  

    You can also train a custom model created by using [Create R Model](create-r-model.md).
    
2. Add the **Train Model** module to the experiment.  You can find this module under the **Machine Learning** category. Expand **Train**, and then drag the **Train Model** module into your experiment.
  
3.  On the left input, attach the untrained mode. Attach the training dataset to the right-hand input of **Train Model**.

    The training dataset must contain a label column. Any rows without labels are ignored.
  
4.  For **Label column**, click **Launch column selector**, and choose a single column that contains outcomes the model can use for training.
  
    - For classification problems, the label column must contain either **categorical** values or **discrete** values. Some examples might be a yes/no rating, a disease classification code or name, or an income group.  If you pick a noncategorical column, the module will return an error during training.
  
    -   For regression problems, the label column must contain **numeric** data that represents the response variable. Ideally the numeric data represents a continuous scale. 
    
    Examples might be a credit risk score, the projected time to failure for a hard drive, or the forecasted number of calls to a call center on a given day or time.  If you do not choose a numeric column, you might get an error.
  
    -   If you do not specify which label column to use, Azure Machine Learning will try to infer which is the appropriate label column, by using the metadata of the dataset. If it picks the wrong column, use the column selector to correct it.
  
    > [!TIP] 
    > If you have trouble using the Column Selector, see the article [Select Columns in Dataset](select-columns-in-dataset.md) for tips. It describes some common scenarios and tips for using the **WITH RULES** and **BY NAME** options.
  
5.  Run the experiment. If you have a lot of data, this can take a while.

### <a name="bkmk_results"></a> Results

After the model is trained:

+ To view the model parameters and feature weights, right-click the output and select **Visualize**.
+ To use the model in other experiments, right-click the model and select **Save Model**. Type a name for the model. 

    This saves the model as a snapshot that is not updated by repeated runs of the experiment.
+ To use the model in predicting new values, connect it to the [Score Model](score-model.md) module, together with new input data.
  
### Related tasks

If you need to train a type of model not supported by **Train Model**, there are several options:

 + Create a custom scoring method using R script, or use one of the many R scoring packages available.

    - [Create R Model](create-r-model.md) 
    - [Execute R Script](execute-r-script.md) 

+ Write your own Python script to train and score a model, or use an existing Python library:

    - [Execute Python Script](execute-python-script.md)

+ Anomaly detection models 

    - [Train Anomaly Detection Model](train-anomaly-detection-model.md) supports the anomaly detection modules in Studio (classic).

+ Recommendation models

    - If your model uses the Matchbox recommend provided in Azure Machine Learning, use the [Train Matchbox Recommender](train-matchbox-recommender.md) module. 

    - If you are using a different algorithm for market basket analysis or recommendation, use its training methods, in [R script](execute-r-script.md) or [Python script](execute-python-script.md).

+ Clustering models

     - Use [Train Clustering Model](train-clustering-model.md) for the included K-means algorithm. 
     
     - For other clustering models, use [R script](execute-r-script.md) or [Python script](execute-python-script.md) modules to both configure and train the models.

## Examples

For examples of how the **Train Model** module is used in machine learning experiments, see these experiments in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
+ [Retail Forecasting](https://go.microsoft.com/fwlink/?LinkId=525950): Demonstrates how to build, train, and compare multiple models.
+ [Flight Delay Prediction](https://go.microsoft.com/fwlink/?LinkId=525725): Demonstrates how to train multiple related classification models.

##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|Untrained learner|  
|Dataset|[Data Table](data-table.md)|Training data|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Label column|any|ColumnSelection||Select the column that contains the label or outcome column|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
  
##  Exceptions  

 For a list of all module errors, see [Module Error Codes](errors/machine-learning-module-error-codes.md).  
  
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
  
## See also  
 
 [Evaluate Model](evaluate-model.md)   
 [A-Z Module List](a-z-module-list.md)
