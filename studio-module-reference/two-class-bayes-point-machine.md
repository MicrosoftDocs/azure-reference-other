---
title: "ML Studio (classic): Two-Class Bayes Point Machine - Azure"
description: Learn how to use the Two-Class Bayes Point Machine module to create an untrained binary classification model.
ms.date: 03/05/2020
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Bayes Point Machine

Creates a Bayes point machine binary classification model
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Two-Class Bayes Point Machine** module in Machine Learning Studio (classic), to create an untrained binary classification model.

The algorithm in this module uses a Bayesian approach to linear classification called the "Bayes Point Machine". This algorithm efficiently approximates the theoretically optimal Bayesian average of linear classifiers (in terms of generalization performance) by choosing one "average" classifier, the Bayes Point. Because the Bayes Point Machine is a Bayesian classification model, it is not prone to overfitting to the training data.

For more information, see Chris Bishop's post on the Microsoft Machine Learning blog: [Embracing Uncertainty - Probabilistic Inference](https://blogs.technet.com/b/machinelearning/archive/2014/10/30/embracing-uncertainty-probabilistic-inference.aspx).
  
## How to configure Two-Class Bayes Point Machine
  
1. In Machine Learning Studio (classic), add the **Two-Class Bayes Point Machine** module to your experiment. You can find the module under **Machine Learning**, **Initialize Model**, **Classification**.
  
2. For **Number of training iterations**, type a number to specify how often the message-passing algorithm iterates over the training data. Typically, the number of iterations should be set to a value in the range 5 – 100.

    The higher the number of training iterations, the more accurate the predictions; however, training will be slower.  
  
    For most datasets, the default setting of 30 training iterations is sufficient for the algorithm to make accurate predictions. Sometimes accurate predictions can be made by using fewer iterations. For datasets with highly correlated features, you might benefit from more training iterations.
  
3. Select the option, **Include bias**, if you want a constant feature or bias to be added to each instance in training and prediction.  
  
     Including a bias is necessary when the data does not already contain a constant feature.  
  
4. Select the option, **Allow unknown values in categorical features**, to create a group for unknown values.
  
     If you deselect this option, the model can accept only the values that are contained in the training data.

     If you select this option and allow unknown values, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.
  
5. Add an instance of the [Train Model](train-model.md) module, and your training data.  

6. Connect the training data and the output of the **Two-Class Bayes Point Machine** module to the [Train Model](train-model.md) module, and choose the label column.
  
7. Run the experiment.
  
### Results

After training is complete, right-click the output of the [Train Model](train-model.md) module to view the results:

+ To see a summary of the model's parameters, together with the feature weights learned from training,  select **Visualize**.
+ To save the model for later use, right-click the output of **Train MOdel**, and select **Save as Trained Model**.
+ To make predictions, use the trained model as an input to the [Score Model](score-model.md) module.

    The untrained model can also be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
## Examples

To see how the Two-Class Bayes Point Machine is used in machine learning, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
+ [Compare Binary Classifiers](https://go.microsoft.com/fwlink/?LinkId=525729): This sample demonstrates the use of multiple two-class classifiers.  

## Technical notes

This section contains implementation details and frequently asked questions about this algorithm.

Details from the original research and underlying theory are available in this paper (PDF): [Bayes Point Machines, by Herbert, Graepe, and Campbell](http://www.jmlr.org/papers/volume1/herbrich01a/herbrich01a.pdf)  

However, this implementation improves on the original algorithm in several ways:

+ It uses the expectation propagation message-passing algorithm. For more information, see [A family of algorithms for approximate Bayesian inference](https://go.microsoft.com/fwlink/?LinkId=511015).  

+ A parameter sweep is not required.

+ This method does not require data to be normalized.  
  
These improvements make the Bayes Point Machine classification model more robust and easier-to-use, and you can bypass the time-consuming step of parameter tuning.

## Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Number of training iterations|>=1|Integer|30|Specify the number of iterations to use when training|  
|Include bias|Any|Boolean|True|Indicate whether a constant feature or bias should be added to each instance|  
|Allow unknown values in categorical features|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
## Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See also

 [Classification](machine-learning-initialize-model-classification.md)
 [A-Z Module List](a-z-module-list.md)
