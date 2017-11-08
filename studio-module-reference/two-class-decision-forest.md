---
title: "Two-Class Decision Forest | Microsoft Docs"
ms.custom: ""
ms.date: 06/09/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5a7d5466-9928-40c8-a19c-d5de4882c77e
caps.latest.revision: 30
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Two-Class Decision Forest
*Creates a two-class classification model using the decision forest algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
## Module Overview  
 You can use the **Two-Class Decision Forest** module to create a machine learning model based on the random decision forests algorithm. Decision forests are fast, supervised ensemble models. This module can be used to predict a target that has two values.  
  
 If you are not sure of the best parameters, we recommend that you use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to train and test multiple models and find the optimal parameters.  
  
##  <a name="Remarks"></a> Understanding Decision Forests  
 The decision forest algorithm is an ensemble learning method for classification. The algorithm works by building multiple decision trees and then voting on the most popular output class. Voting is a form of aggregation, in which each tree in a classification decision forest outputs a non-normalized frequency histogram of labels. The aggregation process sums these histograms and normalizes the result to get the “probabilities” for each label. The trees that have high prediction confidence will have a greater weight in the final decision of the ensemble.  
  
 Decision trees are non-parametric models, and they support data with varied distributions. In each tree, a sequence of simple tests is run for each class, increasing the levels of a tree structure until a leaf node (decision) is reached.  
  
 Decision trees have many advantages:  
  
-   They can represent non-linear decision boundaries.  
  
-   They are efficient in computation and memory usage during training and prediction.  
  
-   They perform integrated feature selection and classification.  
  
-   They are resilient in the presence of noisy features.  
  
 This decision forest classifier consists of an ensemble of decision trees. Generally, ensemble models provide better coverage and accuracy than single decision trees. For more information, see [Decision Forests](http://go.microsoft.com/fwlink/?LinkId=403677).  
  
 This article by Microsoft Research also provides useful information about ensemble methods that use decision trees. [From Stumps to Trees to Forests](http://blogs.technet.com/b/machinelearning/archive/2014/09/10/from-stumps-to-trees-to-forests.aspx).  
  
## How to Configure Two-Class Decision Forest  
  
1.  Add the **Two-Class Decision Forest** module into your experiment.  
  
2.  For **Resampling method**, choose the method used to create the individual trees.  You can choose from **Bagging** or **Replicate**.  
  
    -   **Bagging**.   Bagging is also called *bootstrap aggregating*. In this method, each tree is grown on a new sample, created by randomly sampling the original dataset with replacement until you have a dataset the size of the original.  
  
         The outputs of the models are combined by *voting*, which is a form of aggregation. Each tree in a classification decision forest outputs an un-normalised frequency histogram of labels. The aggregation is to sum these histograms and normalise to get the “probabilities” for each label. In this manner, the trees that have high prediction confidence will have a greater weight in the final decision of the ensemble.  
  
         For more information, see the Wikipedia entry for Bootstrap aggregating.  
  
    -   **Replicate**.   In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random and the trees will be diverse.  
  
         For more information about the training process with the **Replicate** option, see [Decision Forests for Computer Vision and Medical Image Analysis. Criminisi and J. Shotton. Springer 2013.](http://research.microsoft.com/en-us/projects/decisionforests/)  
  
3.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                   If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer will iterate over multiple combinations of the settings you provided and determine the combination of values that produces the best model.  
  
4.  For **Number of decision trees**, type the maximum number of decision trees that can be created in the ensemble. By creating more decision trees, you can potentially get better coverage, but training time will increase.  
  
    > [!NOTE]
    >  This value also controls the number of trees displayed when visualizing the trained model. if you want to see or print a single tree, you can set the value to 1; however, this means that only one tree will be produced (the tree with the initial set of parameters) and no further iterations will be performed.  
  
5.  For **Maximum depth of the decision trees**, type a number to limit the maximum depth of any decision tree. Increasing the depth of the tree might increase precision, at the risk of some overfitting and increased training time.  
  
6.  For **Number of random splits per node**, type the number of splits to use when building each node of the tree. A *split* means that features in each level of the tree (node) are randomly divided.  
  
7.  For **Minimum number of samples per leaf node**, indicate the minimum number of cases that are required to create any terminal node (leaf) in a tree.  
  
     By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.  
  
8.  Select the **Allow unknown values for categorical features** option to create a group for unknown values in the training or validation sets.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
9. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, connect a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, connect a tagged dataset and train the model by using [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    > [!NOTE]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
10. When the model is trained, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize** to see the tree that was created on each iteration.  
  
     You can click on each tree to drill down into the splits and see the rules for each node.  
  
## Example  
 For examples of how decision forests are used in machine learning, see this sample experiment in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [News categorization](https://gallery.azureml.net/Experiment/fcb1bf27ee26443fb19bd07852a620c4) sample compares a multiclass classifier to a model built using the **Two-Class Decision Forest** algorithm with the [One-vs-All Multiclass](one-vs-all-multiclass.md).  
  
-   The [Predictive maintenance](https://gallery.azureml.net/Experiment/6835de908e6b479e92f2e221e7d18195) sample is an extended walkthrough that uses the **Two-Class Decision Forest** algorithm to predict if an asset will fail within certain time frame.  
  
##  <a name="Notes"></a> Technical Notes  
 If you have limited data or you want to minimize the time spent training the model, try these settings:  
  
-   **Limited training set**: If the training set contains a limited number of instances, you can:  
  
     Create the decision forest by using a large number of decision trees (for example, more than 20).  
  
     Use the **Bagging** option for resampling.  
  
     Specify a large number of random splits per node (for example, more than 1,000).  
  
-   **Limited training time**: If the training set contains a large number of instances and training time is limited, you can:  
  
     Create the decision forest by using fewer decision trees (for example, 5-10).  
  
     Use the **Replicate** option for resampling.  
  
     Specify a smaller number of random splits per node (for example, fewer than 100).  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method|  
|Number of decision trees|>=1|Integer|8|Specify the number of decision trees to create in the ensemble|  
|Maximum depth of the decision trees|>=1|Integer|32|Specify the maximum depth of any decision tree that can be created|  
|Number of random splits per node|>=1|Integer|128|Specify the number of splits generated per node, from which the optimal split is selected|  
|Minimum number of samples per leaf node|>=1|Integer|1|Specify the minimum number of training samples that are required to produce a leaf node|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See Also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [Decision Forest Regression](decision-forest-regression.md)   
 [Multiclass Decision Forest](multiclass-decision-forest.md)   
 [A-Z Module List](a-z-module-list.md)