---
title: "ML Studio (classic): Two-Class Decision Forest - Azure"
description: Learn  how to use the Two-Class Decision Forest module to create a machine learning model based on the decision forests algorithm.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Decision Forest
*Creates a two-class classification model using the decision forest algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md) 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)] 
  
## Module overview

This article describes how to use the **Two-Class Decision Forest** module in Machine Learning Studio (classic), to create a machine learning model based on the decision forests algorithm.  

Decision forests are fast, supervised ensemble models. This module is a good choice if you want to predict a target with a maximum of two outcomes. If you are not sure how to configure a decision tree model for the best results, we recommend that you use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to train and test multiple models. tuning iterates over multiple possibilities and finds the optimal solution for you.

## Understanding decision forests

This decision forest algorithm is an ensemble learning method intended for classification tasks. Ensemble methods are based on the general principle that rather than relying on a single model, you can get better results and a more generalized model by creating multiple related models and combining them in some way. Generally, ensemble models provide better coverage and accuracy than single decision trees. 

There are many ways to create individual models and combine them in an ensemble. This particular implementation of a decision forest works by building multiple decision trees and then **voting** on the most popular output class. Voting is one of the better-known methods for generating results in an ensemble model. 

+ Many individual classification trees are created, using the entire dataset, but different (usually randomized) starting points. This differs from the random forest approach, in which the individual decision trees might only use some randomized portion of the data or features.
+ Each tree in the decision forest tree outputs a non-normalized frequency histogram of labels. 
+ The aggregation process sums these histograms and normalizes the result to get the “probabilities” for each label. 
+ The trees that have high prediction confidence will have a greater weight in the final decision of the ensemble.

Decision trees in general have many advantages for classification tasks:
  
- They can capture non-linear decision boundaries.
- You can train and predict on lots of data, as they are efficient in computation and memory usage.
- Feature selection is integrated in the training and classification processes.  
- Trees can acommodate noisy data and many features.  
- They are non-parametric models, meaning they can handle data with varied distributions. 

However, simple decision trees can overfit on data, and are less generalizable than tree ensembles.

For more information, see [Decision Forests](https://go.microsoft.com/fwlink/?LinkId=403677), or the other papers listed in the [Technical notes](#bkmk_Notes) section.  

## How to configure Two-Class Decision Forest
  
1.  Add the **Two-Class Decision Forest** module to your experiment in Machine Learning Studio (classic), and open the **Properties** pane of the module. 

    You can find the module under **Machine Learning**. Expand **Initialize**, and then **Classification**.  
  
2.  For **Resampling method**, choose the method used to create the individual trees.  You can choose from **Bagging** or **Replicate**.  
  
    -   **Bagging**: Bagging is also called *bootstrap aggregating*. In this method, each tree is grown on a new sample, created by randomly sampling the original dataset with replacement until you have a dataset the size of the original.  
  
         The outputs of the models are combined by *voting*, which is a form of aggregation. Each tree in a classification decision forest outputs an un-normalised frequency histogram of labels. The aggregation is to sum these histograms and normalise to get the “probabilities” for each label. In this manner, the trees that have high prediction confidence will have a greater weight in the final decision of the ensemble.  
  
         For more information, see the Wikipedia entry for Bootstrap aggregating.  
  
    -   **Replicate**: In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random and the trees will be diverse.  
  
         For more information about the training process with the **Replicate** option, see the papers listed in the [Technical Notes](#bkmk_Notes) section.
  
3.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, you can provide a specific set of values as arguments.
  
    -   **Parameter Range**: If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer iterates over multiple combinations of the settings you provided and determines the combination of values that produces the best model.
  
4.  For **Number of decision trees**, type the maximum number of decision trees that can be created in the ensemble. By creating more decision trees, you can potentially get better coverage, but training time increases.  
  
    > [!NOTE]
    >  This value also controls the number of trees displayed when visualizing the trained model. If you want to see or print a single tree, you can set the value to 1. However, only one tree can be produced (the tree with the initial set of parameters) and no further iterations are performed.
  
5.  For **Maximum depth of the decision trees**, type a number to limit the maximum depth of any decision tree. Increasing the depth of the tree might increase precision, at the risk of some overfitting and increased training time.
  
6.  For **Number of random splits per node**, type the number of splits to use when building each node of the tree. A *split* means that features in each level of the tree (node) are randomly divided.
  
7.  For **Minimum number of samples per leaf node**, indicate the minimum number of cases that are required to create any terminal node (leaf) in a tree.
  
     By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.  
  
8.  Select the **Allow unknown values for categorical features** option to create a group for unknown values in the training or validation sets. The model might be less precise for known values, but it can provide better predictions for new (unknown) values. 

     If you deselect this option, the model can accept only the values that are contained in the training data.
  
9. Attach a labeled dataset, and one of the [training modules](machine-learning-train.md):  
  
    -   If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, use [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), only the first value in the parameter range list is used.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values, and uses the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value is used throughout the sweep, even if other parameters change across a range of values.

### Results

After training is complete:

+ To see the tree that was created on each iteration, right-click [Train Model](train-model.md) module and select **Trained model** to visualize. If you use [Tune Model Hyperparameters](tune-model-hyperparameters.md), right click the module and select **Trained best model** to visualize the best model. 
  
    Click each tree to drill down into the splits and see the rules for each node.

+ To save a snapshot of the model, right-click the **Trained Model** output, and select **Save Model**. The saved model is not updated on successive runs of the experiment.

+ To use the model for scoring, add the **Score Model** module to an experiment.

## Examples

For examples of how decision forests are used in machine learning, see the sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-  [News categorization](https://gallery.azureml.net/Experiment/fcb1bf27ee26443fb19bd07852a620c4): Compares a multiclass classifier to a model built using the **Two-Class Decision Forest** algorithm with the [One-vs-All Multiclass](one-vs-all-multiclass.md).  
  
- [Predictive maintenance](https://gallery.azureml.net/Experiment/6835de908e6b479e92f2e221e7d18195): An extended walkthrough that uses the **Two-Class Decision Forest** algorithm to predict if an asset will fail within certain time frame.  
  
##  <a name="bkmk_Notes"></a> Technical notes

This section contains additional implementation details, research, and frequently asked questions.
### Usage tips

If you have limited data, or if you want to minimize the time spent training the model, try these settings:  
  
**Limited training set**

If the training set contains a limited number of instances:  
  
+ Create the decision forest by using a large number of decision trees (for example, more than 20).  
+ Use the **Bagging** option for resampling.  
+ Specify a large number of random splits per node (for example, more than 1,000).  
  

**Limited training time**

If the training set contains a large number of instances and training time is limited:  
  
+ Create the decision forest by using fewer decision trees (for example, 5-10).  
+ Use the **Replicate** option for resampling.  
+ Specify a smaller number of random splits per node (for example, fewer than 100).  

### Implementation details

This article by Microsoft Research provides useful information about ensemble methods that use decision trees. [From Stumps to Trees to Forests](https://blogs.technet.com/b/machinelearning/archive/2014/09/10/from-stumps-to-trees-to-forests.aspx).  

For more information about the training process with the **Replicate** option, see [Decision Forests for Computer Vision and Medical Image Analysis. Criminisi and J. Shotton. Springer 2013.](https://research.microsoft.com/en-us/projects/decisionforests/)


##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method|  
|Number of decision trees|>=1|Integer|8|Specify the number of decision trees to create in the ensemble|  
|Maximum depth of the decision trees|>=1|Integer|32|Specify the maximum depth of any decision tree that can be created|  
|Number of random splits per node|>=1|Integer|128|Specify the number of splits generated per node, from which the optimal split is selected|  
|Minimum number of samples per leaf node|>=1|Integer|1|Specify the minimum number of training samples that are required to produce a leaf node|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [Decision Forest Regression](decision-forest-regression.md)   
 [Multiclass Decision Forest](multiclass-decision-forest.md)   
 [A-Z Module List](a-z-module-list.md)
