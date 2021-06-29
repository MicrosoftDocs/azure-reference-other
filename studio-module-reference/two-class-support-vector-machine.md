---
title: "ML Studio (classic): Two-Class Support Vector Machine - Azure"
description: Learn how to use the Two-Class Support Vector Machine module to create a model that is based on the support vector machine algorithm. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Support Vector Machine
*Creates a binary classification model using the Support Vector Machine algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md) 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)] 
  
## Module overview  

This article describes how to use the **Two-Class Support Vector Machine** module in Machine Learning Studio (classic), to create a model that is based on the support vector machine algorithm. 

Support vector machines (SVMs) are a well-researched class of supervised learning methods. This particular implementation is suited to prediction of two possible outcomes, based on either continuous or categorical variables.

After defining the model parameters, train the model by using one of the [training modules](machine-learning-train.md), and providing a *tagged dataset* that includes a label or outcome column.

###  More about support vector machines

Support vector machines are among the earliest of machine learning algorithms, and SVM models have been used in many applications, from information retrieval to text and image classification. SVMs can be used for both classification and regression tasks.

This SVM model is a supervised learning model that requires labeled data. In the training process, the algorithm analyzes input data and recognizes patterns in a multi-dimensional feature space called the *hyperplane*.  All input examples are represented as points in this space, and are mapped to output categories in such a way that categories are divided by as wide and clear a gap as possible.

For prediction, the SVM algorithm assigns new examples into one category or the other, mapping them into that same space. 

## How to configure Two-Class Support Vector Machine 

For this model type, it is recommended that you normalize the dataset before using it to train the classifier.
  
1.  Add the **Two-Class Support Vector Machine** module to your experiment in Studio (classic).  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**: If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer iterates over multiple combinations of the settings and determines the combination of values that produces the best model.
  
3.  For **Number of iterations**, type a number that denotes the number of iterations used when building the model.  
  
     This parameter can be used to control trade-off between training speed and accuracy.  
  
4.  For **Lambda**, type a value to use as the weight for L1 regularization.  
  
     This regularization coefficient can be used to tune the model. Larger values penalize more complex models.  
  
5.  Select the option, **Normalize features**, if you want to normalize features before training.
  
     If you apply normalization, before training, data points are centered at the mean and scaled to have one unit of standard deviation.
  
6.  Select the option, **Project to the unit sphere**, to normalize coefficients.
  
     Projecting values to unit space means that before training, data points are centered at 0 and scaled to have one unit of standard deviation.
  
7.  In **Random number seed**, type an integer value to use as a seed if you want to ensure reproducibility across runs.  Otherwise, a system clock value is used as a seed, which can result in slightly different results across runs.
  
8.  Select the option, **Allow unknown category**, to create a group for unknown values in the training or validation sets.  In this case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.
  
     If you deselect it, the model can accept only the values that are contained in the training data.
  
9. Connect a labeled dataset, and one of the [training modules](machine-learning-train.md):
  
    -   If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.
  
    -   If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md).
  
    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  

10. Run the experiment.

### Results

After training is complete:

+ To see a summary of the model's parameters, together with the feature weights learned from training, , right-click the output of [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md), and select **Visualize**.

+ To use the trained models to make predictions, connect the trained model to the [Score Model](score-model.md) module.

+ To perform cross-validation against a labeled data set, connect the untrained model and the dataset to [Cross-Validate Model](cross-validate-model.md).

## Examples

For examples of how this learning algorithm is used, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Direct marketing](https://go.microsoft.com/fwlink/?LinkId=525168): Uses an SVM model to classify customers by appetency.
  
- [Credit risk prediction](https://go.microsoft.com/fwlink/?LinkId=525270): Uses SVM for assessing credit risk.  
  
- [Compare Multiclass Classifiers](https://go.microsoft.com/fwlink/?LinkId=525730):Uses an SVM model for handwriting recognition.  
  
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

For this model type, it is recommended that you normalize the dataset before using it to train the classifier.

Although recent research has developed algorithms that have higher accuracy, this algorithm can work well on simple data sets when your goal is speed over accuracy. If you do not get the desired results by using **Two-Class Support Vector Model**, try one of these classification methods:  
  
-   [Multiclass Logistic Regression](multiclass-logistic-regression.md)  
  
-   [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md)  

##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Number of iterations|>=1|Integer|1|The number of iterations|  
|Lambda|>=double.Epsilon|Float|0.001|Weight for L1 regularization. Using a non-zero value avoids overfitting the model to the training dataset.|  
|Normalize features|Any|Boolean|True|If True, normalize the features.|  
|Project to the unit-sphere|Any|Boolean|False|If True, project the features to a unit circle.|  
|Random number seed|Any|Integer||The seed for the random number generator used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[Data Table](data-table.md)|An untrained binary classification model.|  
  
## See also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)
