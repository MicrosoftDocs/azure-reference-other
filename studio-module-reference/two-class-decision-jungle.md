---
title: "ML Studio (classic): Two-Class Decision Jungle - Azure"
description: Learn how to use the Two-Class Decision Jungle module to create a machine learning model that is based on a decision jungles supervised ensemble learning algorithm.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Decision Jungle
*Creates a two-class classification model using the decision jungle algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md) 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)] 
  
## Module overview  

This article describes how to use the **Two-Class Decision Jungle** module in Machine Learning Studio (classic), to create a machine learning model that is based on a supervised ensemble learning algorithm called decision jungles.  
  
The **Two-Class Decision Jungle** module returns an untrained classifier. You then train this model on a labeled training data set, by using [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to make predictions. 
  
###  More about decision jungles

[Decision jungles](https://go.microsoft.com/fwlink/?LinkId=403675) are a recent extension to [decision forests](https://go.microsoft.com/fwlink/?LinkId=403677). A decision jungle consists of an ensemble of decision directed acyclic graphs (DAGs).  
  
Decision jungles have the following advantages:  
  
-   By allowing tree branches to merge, a decision DAG typically has a lower memory footprint and better generalization performance than a decision tree, albeit at the cost of somewhat longer training time.  
  
-   Decision jungles are non-parametric models that can represent non-linear decision boundaries.  
  
-   They perform integrated feature selection and classification and are resilient in the presence of noisy features.  
  
> [!TIP]
>  For more information about the research behind this machine learning algorithm, see [Decision Jungles: Compact and Rich Models for Classification](https://research.microsoft.com/pubs/205439/DecisionJunglesNIPS2013.pdf) (downloadable PDF).  
  
## How to configure Two-Class Decision Jungle

1.  Add the **Two-Class Decision Jungle** module to your experiment in Studio (classic).  
  
2.  For **Resampling method**, choose the method used to create the individual trees.  You can choose from **Bagging** or **Replicate**.  
  
    -   **Bagging**: Select this option to use bagging, also called bootstrap aggregating.  
  
         Each tree in a decision jungle outputs a Gaussian distribution as prediction. The aggregation is to find a Gaussian whose first two moments match the moments of the mixture of Gaussians given by combining all Gaussians returned by individual trees.  
  
    -   **Replicate**: In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random and the trees will be diverse.  
  
        For more information, see [Decision Forests for Computer Vision and Medical Image Analysis. Criminisi and J. Shotton. Springer 2013.](https://research.microsoft.com/en-us/projects/decisionforests/)  
  
3.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**: If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer will iterate over multiple combinations of the settings you provided and determine the combination of values that produces the best model.  
  
4.  For **Number of decision DAGs**, indicate the maximum number of graphs that can be created in the ensemble.  
  
5.  For **Maximum depth of the decision DAGs**, indicate the maximum depth of each graph.  
  
6.  For **Maximum width of the decision DAGs**, indicate the maximum width of each graph.  
  
7.  In **Number of optimization steps per decision DAG layer**, indicate  how many iterations over the data to perform when building each DAG.  
  
8.  Select the **Allow unknown values for categorical features** option to create a group for unknown values in testing or validation data.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
9. Add a tagged dataset to the experiment, and connect one of the [training modules](machine-learning-train.md).  
  
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

+ To use the model for scoring, connect it to [Score Model](score-model.md), to predict values for new input examples.
 
## Examples

For examples of how decision jungles are used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Compare Binary Classifiers](https://gallery.azureml.net/Experiment/b2bfde196e604c0aa2f7cba916fc45c8): Uses several algorithms and discusses their pros and cons.  
  
##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

If you have limited data, or want to minimize the time spent training the model, try these settings.

**Limited training set**

If your training set is small:

+ Create the decision jungle by using a large number of decision DAGs (for example, more than 20).  
+ Use the **Bagging** option for resampling.  
+ Specify a large number of optimization steps per DAG layer (for example, more than 10,000).  

**Limited training time**

If the training set is large but training time is limited:  
  
+ Create the decision jungle using a fewer number of decision DAGs (for example, 5-10).  
+ Use the **Replicate** option for resampling.  
+ Specify a smaller number of optimization steps per DAG layer (for example, less than 2000).  

##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method|  
|Number of decision DAGs|>=1|Integer|8|Specify the number of decision graphs to build in the ensemble|  
|Maximum depth of the decision DAGs|>=1|Integer|32|Specify the maximum depth of the decision graphs in the ensemble|  
|Maximum width of the decision DAGs|>=8|Integer|128|Specify the maximum width of the decision graphs in the ensemble|  
|Number of optimization steps per decision DAG layer|>=1000|Integer|2048|Specify the number of steps to use to optimize each level of the decision graphs|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [Multiclass Decision Jungle](multiclass-decision-jungle.md)   
 [A-Z Module List](a-z-module-list.md)
