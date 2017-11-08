---
title: "Multiclass Decision Jungle | Microsoft Docs"
ms.custom: ""
ms.date: 06/14/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5780aca0-de56-4e83-9db0-06e97d03eb4e
caps.latest.revision: 27
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Multiclass Decision Jungle
*Creates a multiclass classification model using the decision jungle algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
## Module Overview  
 You can use the **Multiclass Decision Jungle** module to create a machine learning model that is based on a supervised learning algorithm called *decision jungles*. The model can be used to predict a target that has multiple values.  
  
 The module returns an untrained classifier that can be passed to another module, such as [Train Model](train-model.md) to [Tune Model Hyperparameters](tune-model-hyperparameters.md), for training on a labeled training data set. The trained model can then be used to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
## Understanding Decision Jungles  
 [Decision jungles](http://go.microsoft.com/fwlink/?LinkId=403675) are a recent extension to [decision forests](http://go.microsoft.com/fwlink/?LinkId=403677). A decision jungle consists of an ensemble of decision directed acyclic graphs (DAGs).  
  
 Decision jungles have the following advantages:  
  
-   By allowing tree branches to merge, a decision DAG typically has a lower memory footprint and a better generalization performance than a decision tree, albeit at the cost of a somewhat higher training time.  
  
-   Decision jungles are non-parametric models, which can represent non-linear decision boundaries.  
  
-   They perform integrated feature selection and classification and are resilient in the presence of noisy features.  
  
> [!TIP]
>  For more information about the research behind this machine learning algorithm, see [Decision Jungles: Compact and Rich Models for Classification](http://research.microsoft.com/pubs/205439/DecisionJunglesNIPS2013.pdf) (downloadable PDF).  
  
## How to Configure a Decision Jungle Model  
  
1.  Add the **Multiclass Decision Jungle** module to the experiment.  
  
2.  For **Resampling method**, choose the method for creating multiple trees..  You can choose from **Bagging** or **Replicate**.  
  
    -   **Bagging**. Select this option to use bagging, also called bootstrap aggregating.  
  
         Each tree in a decision forest outputs a Gaussian distribution by way of prediction. The aggregation is to find a Gaussian whose first two moments match the moments of the mixture of Gaussians given by combining all Gaussians returned by individual trees.  
  
    -   ***Replicate*** .   In replication, each tree is trained on exactly the same input data. The determination of which split predicate is used for each tree node remains random and the trees will be diverse.  
  
         For more information about the training process with the **Replicate** option, see [Decision Forests for Computer Vision and Medical Image Analysis. Criminisi and J. Shotton. Springer 2013.](http://research.microsoft.com/en-us/projects/decisionforests/)  
  
3.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                   If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer will iterate over multiple combinations of the settings you provided and determine the combination of values that produces the best model.  
  
4.  For **Number of decision DAGs**, indicate the maximum number of graphs that can be created in the ensemble.  
  
5.  For **Maximum depth of the decision DAGs**, indicate the maximum depth of each graph.  
  
6.  For **Maximum width of the decision DAGs**, indicate the maximum width of each graph.  
  
7.  In **Number of optimization steps per decision DAG layer**, indicate  how many iterations over the data to perform when building each DAG.  
  
8.  Select the **Allow unknown values for categorical features** option to create a group for unknown values in testing or validation data.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
9. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, connect a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, connect a tagged dataset and train the model by using [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    > [!NOTE]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
10. Run the experiment.  
  
11. When the model is trained, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize** to see the tree that was created on each iteration.  
  
     You can click on each tree to drill down into the splits and see the rules for each node.  
  
## Example  
 For examples of how decision forests are used in machine learning, see this sample experiment in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Compare Multiclass Classifiers sample](http://go.microsoft.com/fwlink/?LinkId=525730) uses several algorithms and discusses their pros and cons.  
  
## Technical Notes  
 If you have limited data or want to minimize the time spent training the model, try these recommendations:  
  
-   **Limited training set.** If the training set contains a limited number of instances:  
  
     Create the decision jungle using a large number of decision DAGs (for example, more than 20)  
  
     Use the **Bagging** option for resampling.  
  
     Specify a large number of optimization steps per DAG layer (for example, more than 10,000).  
  
-   **Limited training time.** If the training set contains a large number of instances and training time is limited:  
  
     Create the decision jungle that uses a smaller number of decision DAGs (for example, 5-10).  
  
     Use the **Replicate** option for resampling.  
  
     Specify a smaller number of optimization steps per DAG layer (for example, less than 2000).  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Resampling method|Any|ResamplingMethod|Bagging|Choose a resampling method|  
|Number of decision DAGs|>=1|Integer|8|Specify the number of decision graphs that can be created in the ensemble|  
|Maximum depth of the decision DAGs|>=1|Integer|32|Specify the maximum depth of the decision graphs to create in the ensemble|  
|Maximum width of the decision DAGs|>=8|Integer|128|Specify the maximum width of the decision graphs to create in the ensemble|  
|Number of optimization steps per decision DAG layer|>=1000|Integer|2048|Specify the number of steps to use to optimize each level of the decision graphs|  
|Allow unknown values for categorical features|Any|Boolean|True|Indicate whether unknown values of existing categorical features can be mapped to a new, additional feature|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification model|  
  
## See Also  
 [Two-Class Decision Jungle](two-class-decision-jungle.md)   
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)