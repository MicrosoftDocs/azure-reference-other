---
title: "ML Studio (classic): Two-Class Averaged Perceptron - Azure"
description: Learn how to use the Two-Class Averaged Perceptron module to create a machine learning model based on the averaged perceptron algorithm. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Averaged Perceptron

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates an averaged perceptron binary classification model*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Two-Class Averaged Perceptron** module in Machine Learning Studio (classic), to create a machine learning model based on the averaged perceptron algorithm.  
  
This classification algorithm is a supervised learning method, and requires a *tagged dataset*, which includes a label column. You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  

### More about averaged perceptron models

The *averaged perceptron method* is an early and very simple version of a neural network. In this approach, inputs are classified into several possible outputs based on a linear function, and then combined with a set of weights that are derived from the feature vector—hence the name "perceptron."

The simpler perceptron models are suited to learning linearly separable patterns, whereas neural networks (especially deep neural networks) can model more complex class boundaries. However, perceptrons are faster, and because they process cases serially, perceptrons can be used with continuous training.

## How to configure Two-Class Averaged Perceptron

1.  Add the **Two-Class Averaged Perceptron** module to your experiment in Studio (classic).  

2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, provide a specific set of values as arguments.
  
    -   **Parameter Range**: If you are not sure of the best parameters, find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration. The trainer iterates over multiple combinations of the settings you provided and determines the combination of values that produces the best model.  
  
3.  For **Learning rate**, specify a value for the *learning rate*. The learning rate values controls the size of the step that is used in stochastic gradient descent each time the model is tested and corrected.
  
     By making the rate smaller, you test the model more often, with the risk that you might get stuck in a local plateau. By making the step larger, you can converge faster, at the risk of overshooting the true minima.
  
4.  For **Maximum number of iterations**, type the number of times you want the algorithm to examine the training data.  
  
     Stopping early often provides better generalization. Increasing the number of iterations improves fitting, at the risk of overfitting.
  
5.  For **Random number seed**, optionally type an integer value to use as the seed. Using a seed is recommended if you want to ensure reproducibility of the experiment across runs.  
  
6.  Select the **Allow unknown categorical levels** option to create a group for unknown values in the training and validation sets. The model might be less precise for known values, but it can provide better predictions for new (unknown) values.

    If you deselect this option, the model can accept only the values that are contained in the training data.   
7.  Connect a training dataset, and one of the [training modules](machine-learning-train.md): 
  
    -   If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.
  
    -   If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.
  
    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.


### Results

After training is complete:

+ To see a summary of the model's parameters, together with the feature weights learned from training, right-click the output of [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md).

## Examples

For examples of how this learning algorithm is used, see the [Azure AI Gallery](https://gallery.azure.ai/):

- [Cross Validation for Binary Classifiers sample](https://go.microsoft.com/fwlink/?LinkId=525734): Compares multiple classification models.

## Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

For this model type, it is a best practice to normalize datasets before using them to train the classifier. For normalization options, see  [Normalize Data](normalize-data.md).  

The averaged perceptron model is an early and simplified version of neural networks. As such, it works well on simple data sets when your goal is speed over accuracy. However, if you are not getting the desired results, try one of these models:  
  
-   [Two-Class Neural Network](two-class-neural-network.md) or [Multiclass Neural Network](multiclass-neural-network.md)  
  
-   [Two-Class Logistic Regression](two-class-logistic-regression.md) or [Multiclass Logistic Regression](multiclass-logistic-regression.md)  
  
-   [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md)  

##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Learning rate|>=double.Epsilon|Float|1.0|The initial learning rate for the Stochastic Gradient Descent optimizer.|  
|Maximum number of iterations|>=1|Integer|10|The number of Stochastic Gradient Descent iterations to be performed over the training dataset.|  
|Random number seed|Any|Integer||The seed for the random number generator used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model that can be connected to the [One-vs-All Multiclass](one-vs-all-multiclass.md), [Train Model](train-model.md), or [Cross-Validate Model](cross-validate-model.md) modules.|  
  
## See also
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)
