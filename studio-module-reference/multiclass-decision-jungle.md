---
title: "ML Studio (classic): Multiclass Decision Jungle - Azure"
description: Learn how to use the Multiclass Decision Jungle module to create a machine learning model that is based on athe *decision jungles* supervised learning algorithm.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Multiclass Decision Jungle

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a multiclass classification model using the decision jungle algorithm*

Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Multiclass Decision Jungle** module in Machine Learning Studio (classic), to create a machine learning model that is based on a supervised learning algorithm called *decision jungles*.

You define the model and its parameters using this module, and then connect a labeled training data set to train the model using one of the [training modules](machine-learning-train.md). The trained model can be used to predict a target that has multiple values.

## More about decision jungles

[Decision jungles](https://go.microsoft.com/fwlink/?LinkId=403675) are a recent extension to [decision forests](https://go.microsoft.com/fwlink/?LinkId=403677). A decision jungle consists of an ensemble of decision directed acyclic graphs (DAGs).

Decision jungles have the following advantages:

+ By allowing tree branches to merge, a decision DAG typically has a lower memory footprint and a better generalization performance than a decision tree, albeit at the cost of a somewhat higher training time.

+ Decision jungles are non-parametric models, which can represent non-linear decision boundaries.

+ They perform integrated feature selection and classification and are resilient in the presence of noisy features.

For more information about the research behind this machine learning algorithm, see [Decision Jungles: Compact and Rich Models for Classification](https://research.microsoft.com/pubs/205439/DecisionJunglesNIPS2013.pdf) (downloadable PDF).

## How to configure Multiclass Decision Jungle Model

1. Add the **Multiclass Decision Jungle** module to your experiment in Studio (classic). You can find this module under **Machine Learning**, **Initialize Model**, and **Classification**.

2. Double-click the module to open the **Properties** pane.

3. **Resampling method**, choose the method for creating multiple trees, either bagging or replication.

    - **Bagging**: Select this option to use bagging, also called bootstrap aggregating.

      Each tree in a decision forest outputs a Gaussian distribution by way of prediction. The aggregation is to find a Gaussian whose first two moments match the moments of the mixture of Gaussians given by combining all Gaussians returned by individual trees.

    - **Replicate**: Select this option to use replication. In this method, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random, so diverse trees are created.

4. Specify how you want the model to be trained, by setting the **Create trainer mode** option.

    - **Single Parameter**: Use this option when you know how you want to configure the model.

    - **Parameter Range**: Use this option if you are not sure of the best parameters, and want to use a parameter sweep.

5. **Number of decision DAGs**: Indicate the maximum number of graphs that can be created in the ensemble.

6. **Maximum depth of the decision DAGs**: Specify the maximum depth of each graph.

7. **Maximum width of the decision DAGs**: Specify the maximum width of each graph.

8. **Number of optimization steps per decision DAG layer**: Indicate how many iterations over the data to perform when building each DAG.

9. **Allow unknown values for categorical features**:  Select this option to create a group for unknown values in testing or validation data. The model might be less precise for known values, but it can provide better predictions for new (unknown) values.

    If you deselect this option, the model can accept only values that were present in the training data.

10. Connect a labeled dataset, and one of the training modules:

    + If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.

    + If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module. With this option, the algorithm iterates over multiple combinations of the settings you provided and determines the combination of values that produces the best model.

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

+ To use the model for scoring, connect it to [Score Model](score-model.md), to predict values for new input examples.

## Examples

For examples of how decision forests are used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Compare Multiclass Classifiers sample](https://go.microsoft.com/fwlink/?LinkId=525730): Uses several algorithms and discusses their pros and cons.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Related research

For more information about the training process with the **Replicate** option, see:

+ [Decision forests for computer vision and medical image analysis. Criminisi and Shotton. Springer 2013](https://research.microsoft.com/projects/decisionforests/)

### Usage tips

If you have limited data or want to minimize the time spent training the model, try these recommendations:

**Limited training set**

If the training set contains a limited number of instances:

+ Create the decision jungle using a large number of decision DAGs (for example, more than 20)
+ Use the **Bagging** option for resampling.
+ Specify a large number of optimization steps per DAG layer (for example, more than 10,000).

**Limited training time**

If the training set contains a large number of instances and training time is limited:

+ Create the decision jungle that uses a smaller number of decision DAGs (for example, 5-10).
+ Use the **Replicate** option for resampling.
+ Specify a smaller number of optimization steps per DAG layer (for example, less than 2000).

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method|  
|Number of decision DAGs|>=1|Integer|8|Specify the number of decision graphs that can be created in the ensemble|  
|Maximum depth of the decision DAGs|>=1|Integer|32|Specify the maximum depth of the decision graphs to create in the ensemble|  
|Maximum width of the decision DAGs|>=8|Integer|128|Specify the maximum width of the decision graphs to create in the ensemble|  
|Number of optimization steps per decision DAG layer|>=1000|Integer|2048|Specify the number of steps to use to optimize each level of the decision graphs|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification model|  
  
## See also

 [Two-Class Decision Jungle](two-class-decision-jungle.md)   
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)
