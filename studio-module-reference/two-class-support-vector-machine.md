---
title: "Two-Class Support Vector Machine | Microsoft Docs"
ms.custom: ""
ms.date: 06/09/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 12d8479b-74b4-4e67-b8de-d32867380e20
caps.latest.revision: 20
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Two-Class Support Vector Machine
*Creates a binary classification model using the Support Vector Machine algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
## Module Overview  
 You can use the **Two-Class Support Vector Machine** module to create a model that is based on the support vector machine algorithm. The classifier that this module initializes is useful for predicting between two possible outcomes that depend on continuous or categorical predictor variables.  
  
 This model is a supervised learning method, and therefore requires a *tagged dataset*, which includes a label column.  
  
 You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  
  
##  <a name="Remarks"></a> Understanding Support Vector Machines  
 Support vector machines (SVMs) are supervised learning models that analyze data and recognize patterns. They can be used for classification and regression tasks.  
  
 The classifier that is created by this module is useful for predicting between two possible outcomes that depend on continuous or categorical predictor variables.  
  
 Given a set of training examples labeled as belonging to one of two classes, the SVM algorithm assigns new examples into one category or the other. The examples are represented as points in space, and they are mapped so that the examples of the separate categories are divided by a clear gap that is as wide as possible. New examples are then mapped into that same space and predicted to belong to a category based on which side of the gap they fall on.  
  
 The feature space that contains the training examples is sometimes called a *hyperplane*, and it may have many dimensions.  
  
 Support vector machines are among the earliest of machine learning algorithms, and SVM models have been used in many applications, from information retrieval to text and image classification. Although recent research has developed algorithms that have higher accuracy, this algorithm can work well on simple data sets when your goal is speed over accuracy. If you do not get the desired results by using **Two-Class Support Vector Model**, try one of these classification methods:  
  
-   [Multiclass Logistic Regression](multiclass-logistic-regression.md)  
  
-   [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md)  
  
## How to Configure a Two-Class SVM Model  
 For this model type, it is recommended that you normalize the dataset before using it to train the classifier.  
  
1.  Add the **Two-Class Support Vector Machine** module to the experiment.  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                   If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer will iterate over multiple combinations of the settings you provided and determine the combination of values that produces the best model.  
  
3.  For **Number of iterations**, type a number that denotes the number of iterations used when building the model.  
  
     This parameter can be used to control trade-off between training speed and accuracy.  
  
4.  For **Lambda**, type a value to use as the weight for L1 regularization.  
  
     This regularization coefficient can be used to tune the model. Larger values penalize more complex models.  
  
5.  Select the option, **Normalize features**, if you want to normalize features before training.  
  
     If you apply normalization, before training, data points are centered at the mean and scaled to have one unit of standard deviation.  
  
6.  Select the option, **Project to the unit sphere**, to normalize coefficients.  
  
     Projecting values to unit space means that before training, data points are centered at the mean and scaled to have one unit of standard deviation.  
  
7.  In **Random number seed**, type an integer value to use as a seed if you want to ensure reproducibility across runs.  
  
8.  Select the option, **Allow unknown category**, to create a group for unknown values in the training or validation sets.  In this case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
     If you deselect it, the model can accept only the values that are contained in the training data.  
  
9. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, connect a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, connect a tagged dataset and train the model by using [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    > [!NOTE]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
10. When the model is trained, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize** to see a summary of the model's parameters, together with the feature weights learned from training.  
  
11. You can pass the trained model to the [Score Model](score-model.md) module to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
## Examples  
 For examples of how this learning algorithm is used, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Direct marketing](http://go.microsoft.com/fwlink/?LinkId=525168) sample uses an SVM model to classify customers by appetency.  
  
-   The [Credit risk prediction](http://go.microsoft.com/fwlink/?LinkId=525270) sample uses SVM for assessing credit risk.  
  
-   The [Compare Multiclass Classifiers](http://go.microsoft.com/fwlink/?LinkId=525730) sample uses an SVM model for handwriting recognition.  
  
## Technical Notes  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Number of iterations|>=1|Integer|1|The number of iterations|  
|Lambda|>=double.Epsilon|Float|0.001|Weight for L1 regularization. Using a non-zero value avoids overfitting the model to the training dataset.|  
|Normalize features|Any|Boolean|True|If True, normalize the features.|  
|Project to the unit-sphere|Any|Boolean|False|If True, project the features to a unit circle.|  
|Random number seed|Any|Integer||The seed for the random number generator used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[Data Table](data-table.md)|An untrained binary classification model.|  
  
## See Also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)