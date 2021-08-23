---
title: "ML Studio (classic): Decision Forest Regression - Azure"
description: Learn how to use the Decision Forest Regression module to create a regression model based on an ensemble of decision trees.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Decision Forest Regression

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a regression model using the decision forest algorithm*

Category: [Initialize Model - Regression](machine-learning-initialize-model-regression.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Decision Forest Regression** module in Machine Learning Studio (classic), to create a regression model based on an ensemble of decision trees.

After you have configured the model, you must train the model using a labeled dataset and the [Train Model](train-model.md) module.  The trained model can then be used to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.

## How decision forests work in regression tasks

Decision trees are non-parametric models that perform a sequence of simple tests for each instance, traversing a binary tree data structure until a leaf node (decision) is reached.

Decision trees have these advantages:

- They are efficient in both computation and memory usage during training and prediction.

- They can represent non-linear decision boundaries.

- They perform integrated feature selection and classification and are resilient in the presence of noisy features.

This regression model consists of an ensemble of decision trees. Each tree in a regression decision forest outputs a Gaussian distribution as a prediction. An aggregation is performed over the ensemble of trees to find a Gaussian distribution closest to the combined distribution for all trees in the model.

For more information about the theoretical framework for this algorithm and its implementation, see this article: [Decision Forests: A Unified Framework for Classification, Regression, Density Estimation, Manifold Learning and Semi-Supervised Learning ](https://www.microsoft.com/en-us/research/publication/decision-forests-a-unified-framework-for-classification-regression-density-estimation-manifold-learning-and-semi-supervised-learning/?from=http%3A%2F%2Fresearch.microsoft.com%2Fapps%2Fpubs%2Fdefault.aspx%3Fid%3D158806#)

## How to configure Decision Forest Regression Model

1. Add the **Decision Forest Regression** module to the experiment. You can find the module in Studio (classic) under **Machine Learning**, **Initialize Model**, and **Regression**.

2. Open the module properties, and for **Resampling method**, choose the method used to create the individual trees.  You can choose from **Bagging** or **Replicate**.

    - **Bagging**: Bagging is also called *bootstrap aggregating*. Each tree in a regression decision forest outputs a Gaussian distribution by way of prediction. The aggregation is to find a Gaussian whose first two moments match the moments of the mixture of Gaussians given by combining all Gaussians returned by individual trees.

         For more information, see the Wikipedia entry for [Bootstrap aggregating](https://wikipedia.org/wiki/Bootstrap_aggregating).

    - **Replicate**: In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random and the trees will be diverse.

         For more information about the training process with the **Replicate** option, see [Decision Forests for Computer Vision and Medical Image Analysis. Criminisi and J. Shotton. Springer 2013.](https://research.microsoft.com/projects/decisionforests/).

3. Specify how you want the model to be trained, by setting the **Create trainer mode** option.

    - **Single Parameter**

      If you know how you want to configure the model, you can provide a specific set of values as arguments. You might have learned these values by experimentation or received them as guidance.

    - **Parameter Range**

      If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using a parameter sweep to find the optimal configuration.

       [Tune Model Hyperparameters](tune-model-hyperparameters.md) will iterate over all possible combinations of the settings you provided and determine the combination of settings that produces the optimal results.

4. For **Number of decision trees**, indicate the total number of decision trees to create in the ensemble. By creating more decision trees, you can potentially get better coverage, but training time will increase.

    > [!TIP]
    > This value also controls the number of trees displayed when visualizing the trained model. if you want to see or print a single tree, you can set the value to 1; however, this means that only one tree will be produced (the tree with the initial set of parameters) and no further iterations will be performed.

5. For **Maximum depth of the decision trees**, type a number to limit the maximum depth of any decision tree. Increasing the depth of the tree might increase precision, at the risk of some overfitting and increased training time.

6. For **Number of random splits per node**, type the number of splits to use when building each node of the tree. A *split* means that features in each level of the tree (node) are randomly divided.

7. For **Minimum number of samples per leaf node**, indicate the minimum number of cases that are required to create any terminal node (leaf) in a tree.

     By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.

8. Select the **Allow unknown values for categorical features** option to create a group for unknown values in the training or validation sets.

     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.

9. Connect a labeled dataset, select a single label column containing no more than two outcomes, and connect either [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md).

    - If you set **Create trainer mode** option to **Single Parameter**, train the model by using the [Train Model](train-model.md) module.

    - If you set **Create trainer mode** option to **Parameter Range**, train the model by using [Tune Model Hyperparameters](tune-model-hyperparameters.md).

10. Run the experiment.

### Results

After training is complete:

+ To see the tree that was created on each iteration, right-click the output of the training module, and select **Visualize**.

+ To see the rules for each node, click each tree and drill down into the splits.

+ To save a snapshot of the traind model, right-click the output of the training module, and select **Save As Trained Model**. This copy of the model is not updated on successive runs of the experiment. 

## Examples

For examples of regression models, see these sample experiments in the [Cortana Intelligence Gallery](https://gallery.azure.ai/):

- [Compare Regression Models sample](https://go.microsoft.com/fwlink/?LinkId=525731): Contrasts several different kinds of regression models.

- [Sentiment analysis sample](https://go.microsoft.com/fwlink/?LinkId=525274): Uses several different regression models to generate predicted ratings.

##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

- If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.

- If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.

- If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.

### Usage tips

If you have limited data or want to minimize the time spent training the model, try these settings:

**Limited training set.** If the training set contains a limited number of instances:

- Create the decision forest using a large number of decision trees (for example, more than 20)

- Use the **Bagging** option for resampling

- Specify a large number of random splits per node (for example, more than 1000) 

**Limited training time.** If the training set contains a large number of instances and training time is limited:

- Create the decision forest using fewer decision trees (for example, 5-10)

- Use the **Replicate** option for resampling

- Specify a small number of random splits per node (for example, less than 100)

##  Module parameters

|Name|Range|Type|Default|Description|
|----------|-----------|----------|-------------|-----------------|
|Resampling method|any|ResamplingMethod|Bagging|Choose a resampling method|
|Number of decision trees|>=1|Integer|8|Specify the number of decision trees to create in the ensemble|
|Maximum depth of the decision trees|>=1|Integer|32|Specify the maximum depth of any decision tree that can be created in the ensemble|
|Number of random splits per node|>=1|Integer|128|Specify the number of splits generated per node, from which the optimal split is selected|
|Minimum number of samples per leaf node|>=1|Integer|1|Specify the minimum number of training samples required to generate a leaf node|
|Allow unknown values for categorical features|any|Boolean|true|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|

##  Outputs

|Name|Type|Description|
|----------|----------|-----------------|
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|

## See also

[Regression](machine-learning-initialize-model-regression.md)

[A-Z Module List](a-z-module-list.md)
