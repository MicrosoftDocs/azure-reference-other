---
title: "Boosted Decision Tree Regression | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/11/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0207d252-6c41-4c77-84c3-73bdf1ac5960
caps.latest.revision: 24
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Boosted Decision Tree Regression

*Creates a regression model using the Boosted Decision Tree algorithm*  

Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  

## Module overview  

This article describes how to use the **Boosted Decision Tree Regression** module in Azure Machine Learning Studio, to create an ensemble of regression trees using boosting. *Boosting* means that each tree is dependent on prior trees. The algorithm learns by fitting the residual of the trees that preceded it. Thus, boosting in a decision tree ensemble tends to improve accuracy with some small risk of less coverage.  
  
This regression method is a supervised learning method, and therefore requires a *labeled dataset*. The label column must contain numerical values.  

> [!NOTE]
> Use this module only with datasets that use numerical variables.  

After you have defined the model, train it by using the [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md) modules. 

> [!TIP]
> Want to know more about the trees that were created? After the model has been trained, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize** to see the tree that was created on each iteration. You can drill down into the splits for each tree and see the rules for each node.  
  
## More about boosted regression trees  

Boosting is one of several classic methods for creating ensemble models, along with bagging, random forests, and so forth.  In Azure Machine Learning Studio, boosted decision trees use an efficient implementation of the MART gradient boosting algorithm. Gradient boosting is a machine learning technique for regression problems. It builds each regression tree in a step-wise fashion, using a predefined loss function to measure the error in each step and correct for it in the next. Thus the prediction model is actually an ensemble of weaker prediction models.  
  
In regression problems, boosting builds a series of trees in a step-wise fashion, and then selects the optimal tree using an arbitrary differentiable loss function.  
  
For additional information, see these articles:  
  
+ [https://wikipedia.org/wiki/Gradient_boosting#Gradient_tree_boosting](https://wikipedia.org/wiki/Gradient_boosting)

    This Wikipedia article on gradient boosting provides some background on boosted trees. 
  
-  [http://research.microsoft.com/apps/pubs/default.aspx?id=132652](http://research.microsoft.com/apps/pubs/default.aspx?id=132652)  

    Microsoft Research: From RankNet to LambdaRank to LambdaMART: An Overview. By J.C. Burges.

The gradient boosting method can also be used for classification problems by reducing them to regression with a suitable loss function. For more information about the boosted trees implementation for classification tasks, see [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md).  

## How to configure Boosted Decision Tree Regression

1.  Add the **Boosted  Decision Tree** module to your experiment. You can find this module under **Machine Learning**, **Initialize**, under the **Regression** category. 
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: Select this option if you know how you want to configure the model, and provide a specific set of values as arguments.  
  
    -   **Parameter Range**: Select this option if you are not sure of the best parameters, and want to run a parameter sweep. Select a range of values to iterate over, and the [Tune Model Hyperparameters](tune-model-hyperparameters.md) iterates over all possible combinations of the settings you provided to determine the hyperparameters that produce the optimal results.  
  
3. **Maximum number of leaves per tree**: Indicate the maximum number of terminal nodes (leaves) that can be created in any tree.  

    By increasing this value, you potentially increase the size of the tree and get better precision, at the risk of overfitting and longer training time.  

4. **Minimum number of samples per leaf node**: Indicate the minimum number of cases required to create any terminal node (leaf) in a tree.

    By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.

5. **Learning rate**: Type a number between 0 and 1 that defines the step size while learning. The learning rate determines how fast or slow the learner converges on the optimal solution. If the step size is too big, you might overshoot the optimal solution. If the step size is too small, training takes longer to converge on the best solution.

6. **Number of trees constructed**: Indicate the total number of decision trees to create in the ensemble. By creating more decision trees, you can potentially get better coverage, but training time increases.

    This value also controls the number of trees displayed when visualizing the trained model. if you want to see or print a ingle tree, you can set the value to 1; however, this means that only one tree is produced (the tree with the initial set of parameters) and no further iterations are performed.

7. **Random number seed**: Type an optional non-negative integer to use as the random seed value. Specifying a seed ensures reproducibility across runs that have the same data and parameters.

    By default, the random seed is set to 0, which means the initial seed value is obtained from the system clock.
  
8. **Allow unknown categorical levels**: Select this option to create a group for unknown values in the training and validation sets. If you deselect this option, the model can accept only the values that are contained in the training data. The model might be less precise for known values, but it can provide better predictions for new (unknown) values.

9. Add a training dataset, and one of the training modules:

    - If you set **Create trainer mode** option to **Single Parameter**, use the [Train Model](train-model.md) module.  
  
    - If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.

    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value is used throughout the sweep, even if other parameters change across a range of values.

10. Run the experiment.  
  
### Results

After training is complete:

+ To see the tree that was created on each iteration, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize**.
  
     Click each tree to drill down into the splits and see the rules for each node.  

+ To use the model for scoring, connect it to [Score Model](score-model.md), to predict values for new input examples.

+ To save a snapshot of the trained model, right-click the **Trained model** output of the training module and select **Save As**. The copy of the trained model that you save is not updated on successive runs of the experiment.

## Examples  
 
For examples of how boosted trees are used in machine learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com):  

- [Demand estimation](http://go.microsoft.com/fwlink/?LinkId=525271): Uses **Boosted Decision Tree Regression** to predict the number of rentals for a particular time.  
  
- [Twitter sentiment analysis](http://go.microsoft.com/fwlink/?LinkId=525274): Uses regression to generate a predicted rating.  
  
##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

> [!TIP]
> In general, decision trees yield better results when features are somewhat related. If features have a large degree of entropy (that is, they are not related), they share little or no mutual information, and ordering them in a tree will not yield a lot of predictive significance.  


### Implementation details
  
The ensemble of trees is produced by computing, at each step, a regression tree that approximates the gradient of the loss function, and adding it to the previous tree with coefficients that minimize the loss of the new tree. The output of the ensemble produced by MART on a given instance is the sum of the tree outputs.  
  
+ For binary classification problem, the output is converted to probability by using some form of calibration.  
  
+ For regression problems, the output is the predicted value of the function.  
  
+ For ranking problems, the instances are ordered by the output value of the ensemble.  
  
## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Maximum number of leaves per tree|>=1|Integer|20|Specify the maximum number of leaves per tree|  
|Minimum number of samples per leaf node|>=1|Integer|10|Specify the minimum number of cases required to form a leaf node|  
|Learning rate|[double.Epsilon;1.0]|Float|0.2|Specify the initial learning rate|  
|Total number of trees constructed|>=1|Integer|100|Specify the maximum number of trees that can be created during training|  
|Random number seed|any|Integer||Provide a seed for the random number generator used by the model. Leave blank for default.|  
|Allow unknown categorical levels|any|Boolean|true|If true, create an additional level for each categorical column. Levels in the test dataset not available in the training dataset are mapped to this additional level.|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  
  
## See also

 [A-Z Module List](a-z-module-list.md)   
 [Regression](machine-learning-initialize-model-regression.md)