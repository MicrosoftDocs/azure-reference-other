---
title: "Two-Class Bayes Point Machine | Microsoft Docs"
ms.custom: ""
ms.date: 10/11/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a1acf84e-a4d0-42ab-99d6-a4f4616b92cf
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Two-Class Bayes Point Machine
*Creates a Bayes point machine binary classification model*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
## Module Overview  
 You can use the **Two-Class Bayes Point Machine** module to create an untrained binary classification model.  
  
 After you have configured the model, you must train the model on a labeled dataset using the [Train Model](train-model.md) module.  
  
##  <a name="Remarks"></a> Understanding Bayes Point Machines  
 The Bayes Point Machine is a Bayesian approach to linear classification. It efficiently approximates the theoretically optimal Bayesian average of linear classifiers (in terms of generalization performance) by choosing one "average" classifier, the Bayes Point. Because the Bayes Point Machine is a Bayesian classification model, it is not prone to overfitting to the training data.  
  
 For more information, download the original research paper (PDF): [Bayes Point Machines, by Herbert, Graepe, and Campbell](http://www.jmlr.org/papers/volume1/herbrich01a/herbrich01a.pdf)  
  
 This implementation improves on the original algorithm in several ways:  
  
-   It uses the expectation propagation message-passing algorithm. For more information, see [A family of algorithms for approximate Bayesian inference](http://go.microsoft.com/fwlink/?LinkId=511015).  
  
-   It does not require parameter sweeping.  
  
-   It does not require data to be normalized.  
  
 These improvements make the Bayes Point Machine classification model more robust and easier-to-use, and you can bypass the time-consuming step of parameter tuning.  
  
 For more information, see Chris Bishop's post on the Microsoft Machine Learning blog: [Embracing Uncertainty - Probabilistic Inference](http://blogs.technet.com/b/machinelearning/archive/2014/10/30/embracing-uncertainty-probabilistic-inference.aspx),  
  
## How to Use the Two-Class Bayes Point Machine  
  
1.  Add the **Two-Class Bayes Point Machine** module to the experiment.  
  
2.  For **Number of training iterations**, type a number to specify how often the message-passing algorithm iterates over the training data. The higher the number of training iterations, the more accurate the predictions; however, training will be slower.  
  
     For most datasets, the default setting of 30 training iterations is sufficient for the algorithm to make accurate predictions. Sometimes accurate predictions can be made by using fewer iterations. For datasets with highly correlated features, you might benefit from more training iterations. Typically, the number of iterations should be set to a value in the range 5 – 100.  
  
3.  Select the option, **Include bias**, if you want a constant feature or bias to be added to each instance in training and prediction.  
  
     Including a bias is necessary when the data does not already contain a constant feature.  
  
4.  Select the option, **Allow unknown values**, to create a group for unknown values.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
5.  Connect a dataset and choose a single label column. Connect an instance of the [Train Model](train-model.md) module.  
  
6.  Run the experiment.  
  
7.  When the model is trained, right-click the output of the [Train Model](train-model.md) module and select **Visualize** to see a summary of the model's parameters, together with the feature weights learned from training.  
  
8.  You can pass the trained model to the [Score Model](score-model.md) module to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
##  <a name="Notes"></a> Examples  
 To see how the Two-Class Bayes Point Machine is used in machine learning, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Compare Binary Classifiers](http://go.microsoft.com/fwlink/?LinkId=525729) sample demonstrates the use of various two-class classifiers.  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Number of training iterations|>=1|Integer|30|Specify the number of iterations to use when training|  
|Include bias|Any|Boolean|True|Indicate whether a constant feature or bias should be added to each instance|  
|Allow unknown values in categorical features|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See Also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)