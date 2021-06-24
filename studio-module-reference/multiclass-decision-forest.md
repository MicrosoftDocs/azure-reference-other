---
title: "ML Studio (classic): Multiclass Decision Forest - Azure"
description: Learn how to use the Multiclass Decision Forest module to create a machine learning model based on the *decision forest* algorithm. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Multiclass Decision Forest

*Creates a multiclass classification model using the decision forest algorithm*

Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Multiclass Decision Forest** module in Machine Learning Studio (classic), to create a machine learning model based on the *decision forest* algorithm. A decision forest is an ensemble model that very rapidly builds a series of decision trees, while learning from tagged data.

## More about decision forests

The decision forest algorithm is an ensemble learning method for classification. The algorithm works by building multiple decision trees and then *voting* on the most popular output class. Voting is a form of aggregation, in which each tree in a classification decision forest outputs a non-normalized frequency histogram of labels. The aggregation process sums these histograms and normalizes the result to get the “probabilities” for each label. The trees that have high prediction confidence have a greater weight in the final decision of the ensemble.

Decision trees in general are non-parametric models, meaning they support data with varied distributions. In each tree, a sequence of simple tests is run for each class, increasing the levels of a tree structure until a leaf node (decision) is reached.

Decision trees have many advantages:

+ They can represent non-linear decision boundaries.
+ They are efficient in computation and memory usage during training and prediction.
+ They perform integrated feature selection and classification.
+ They are resilient in the presence of noisy features.

The decision forest classifier in Machine Learning Studio (classic) consists of an ensemble of decision trees. Generally, ensemble models provide better coverage and accuracy than single decision trees. For more information, see [Decision trees](https://go.microsoft.com/fwlink/?LinkId=403677).

## How to configure Multiclass Decision Forest

> [!TIP]
> If you are not sure of the best parameters, we recommend that you use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to train and test multiple models and find the optimal parameters.

1. Add the **Multiclass Decision Forest** module to your experiment in Studio (classic). You can find this module under **Machine Learning**, **Initialize Model**, and **Classification**.

2. Double-click the module to open the **Properties** pane.

3. For **Resampling method**, choose the method used to create the individual trees.  You can choose from bagging or replication.

    + **Bagging**: Bagging is also called *bootstrap aggregating*. In this method, each tree is grown on a new sample, created by randomly sampling the original dataset with replacement until you have a dataset the size of the original. The outputs of the models are combined by *voting*, which is a form of aggregation. For more information, see the Wikipedia entry for Bootstrap aggregating.

    + **Replicate**: In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random, creating diverse trees.

    See the [How to Configure a Multiclass Decision Forest Model](#tips) section for guidance.

4. Specify how you want the model to be trained, by setting the **Create trainer mode** option.

    + **Single Parameter**: Select this option if you know how you want to configure the model, and provide a set of values as arguments.

    + **Parameter Range**: Use this option if you are not sure of the best parameters, and want to use a parameter sweep.

5. **Number of decision trees**: Type the maximum number of decision trees that can be created in the ensemble. By creating more decision trees, you can potentially get better coverage, but training time might increase.

    This value also controls the number of trees displayed in the results, when visualizing the trained model. To see or print a single tree, you can set the value to 1; however, this means that only one tree can be produced (the tree with the initial set of parameters), and no further iterations are performed.

6. **Maximum depth of the decision trees**: Type a number to limit the maximum depth of any decision tree. Increasing the depth of the tree might increase precision, at the risk of some overfitting and increased training time.

7. **Number of random splits per node**: Type the number of splits to use when building each node of the tree. A *split* means that features in each level of the tree (node) are randomly divided.

8. **Minimum number of samples per leaf node**: Indicate the minimum number of cases that are required to create any terminal node (leaf) in a tree. By increasing this value, you increase the threshold for creating new rules.

    For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.

9. **Allow unknown values for categorical features**: Select this option to create a group for unknown values in the training or validation sets.  The model might be less precise for known values, but it can provide better predictions for new (unknown) values.

    If you deselect this option, the model can accept only the values that are present in the training data.

10. Connect a labeled datset, and one of the training modules:

    + If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.

    + If you set **Create trainer mode** option to **Parameter Range**, use the  [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  With this option, the trainer can iterate over multiple combinations of the settings and determine the parameter values that produce the best model.

    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.

11. Run the experiment.

### Results

After training is complete:

+ To see the tree that was created on each iteration, right-click [Train Model](train-model.md) module and select **Trained model** to visualize. If you use [Tune Model Hyperparameters](tune-model-hyperparameters.md), right click the module and select **Trained best model** to visualize the best model. 
    To see the rules for each node, click each tree to drill down into the splits.

## Examples

For examples of how decision forests are used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Compare Multiclass Classifiers sample](https://go.microsoft.com/fwlink/?LinkId=525730): Uses several algorithms and discusses their pros and cons.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

Each tree in a classification decision forest outputs an un-normalized frequency histogram of labels. The aggregation is to sum these histograms and normalize to get the “probabilities” for each label. In this manner, the trees that have high prediction confidence have a greater weight in the final decision of the ensemble.

### Related research

For more information about the training process with the **Replicate** option, see:

+  [Decision forests for computer vision and medical image analysis. Criminisi and Shotton. Springer 2013.](https://research.microsoft.com/projects/decisionforests/)

### <a name="tips"></a> How to Configure a Multiclass Decision Forest Model

You can change the way the module is configured to accommodate scenarios such as too little data, or limited time for training.

**Limited training time**

If the training set contains a large number of instances, but the time you have available for training the model is limited, try using these options:

+ Create a decision forest that uses a smaller number of decision trees (for example, 5-10).
+ Use the **Replicate** option for resampling.
+ Specify a smaller number of random splits per node (for example, less than 100).

**Limited training set**

If the training set contains a limited number of instances, try using these options:

+ Create a decision forest that uses a large number of decision trees (for example, more than 20).
+ Use the **Bagging** option for resampling.
+ Specify a large number of random splits per node (for example, more than 1,000).

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method:  **Bagging** or **Replicate**|  
|Number of decision trees|>=1|Integer|8|Specify the number of decision trees to create in the ensemble|  
|Maximum depth of the decision trees|>=1|Integer|32|Specify the maximum depth of any decision tree that can be created|  
|Number of random splits per node|>=1|Integer|128|Specify the number of splits generated per node, from which the optimal split is selected|  
|Minimum number of samples per leaf node|>=1|Integer|1|Specify the minimum number of training samples required to generate a leaf node|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification model|  

## See also

 [Classification](machine-learning-initialize-model-classification.md)   
 [Two-Class Decision Forest](two-class-decision-forest.md)   
 [Decision Forest Regression](decision-forest-regression.md)   
 [A-Z Module List](a-z-module-list.md)
