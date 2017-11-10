---
title: "Two-Class Neural Network | Microsoft Docs"
ms.custom: ""
ms.date: 06/09/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ebc29f52-719d-4d0f-b66a-2ce85f527c7d
caps.latest.revision: 25
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Two-Class Neural Network
*Creates a binary classifier using a neural network algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Two-Class Neural Network** module to create a neural network model that can be used to predict a target that has only two values. For example, neural networks could be used for predictions in medical scenarios, such as determining whether a patient has a certain disease.  
  
 Classification using neural networks is a supervised learning method, and therefore requires a *tagged dataset*, which includes a label column.  
  
 You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or to [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  
  
## Understanding Neural Networks  
 A neural network is a set of interconnected layers, in which the inputs lead to outputs by a series of weighted edges and nodes.  
  
 The weights on the edges are learned when training the neural network on the input data. The direction of the graph proceeds from the inputs through the hidden layer, with all nodes of the graph connected by the weighted edges to nodes in the next layer.  
  
 Most predictive tasks can be accomplished easily with only one or a few hidden layers. Recent research has shown that deep neural networks (DNN) can be very effective in complex tasks such as image or speech recognition, in which successive layers are used to model increasing levels of semantic depth.  
  
 To compute the output of the network for any given input, a value is calculated for each node in the hidden layers and in the output layer. For each node, the value is set by calculating the weighted sum of the values of the nodes in the previous layer and applying an activation function to that weighted sum.  
  
## How to Configure a Neural Network Model  
  
1.  Add the **Two-Class Neural Network** module to the experiment.  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                   If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer will iterate over multiple combinations of the settings you provided and determine the combination of values that produces the best model.  
  
3.  For **Hidden layer specification**, select the type of network architecture to create.  
  
    -   **Fully-connected case**. Choose this option to use the default neural network architecture. The default two-class neural network model is defined as follows:  
  
        -   The default structure has one hidden layer.  
  
        -   The output layer is fully connected to the hidden layer, and the hidden layer is fully connected to the input layer.  
  
        -   The number of nodes in the input layer is determined by the number of features in the training data.  
  
        -   The number of nodes in the hidden layer is determined by the user (with a default value of 100).  
  
        -   The number of nodes in the output layer depends on the number of classes.  
  
    -   **Custom definition script**. Choose this option to create a custom neural network architecture, using the Net# language.  
  
         You can define the number of hidden layers, their connections, and advanced options such as specifying the mappings between layers.  For an introduction to Net#, see   [More About Net#](#bkmk_Customizing) later in this topic.  
  
         After selecting the custom script  option, use the **Neural network definition** text box to type  or paste in statements written in the Net# language. For additional script examples, see [Guide to the Net# Neural Networks Specification Language](http://go.microsoft.com/fwlink/?LinkId=402867).  
  
4.  For **Number of hidden nodes**, type the number of hidden nodes.  
  
     By default, there is one hidden layer with 100 nodes.  
  
5.  For **Learning rate**, define the size of the step taken at each iteration, before correction.  
  
     A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.  
  
6.  For **Number of learning iterations**, specify  the maximum number of times the algorithm should process the training cases.  
  
7.  For **The initial learning weights diameter**, specify the node weights at the start of the learning process.  
  
8.  For **The momentum**, specify a weight to apply during learning to nodes from previous iterations  
  
9. In **The type of normalizer**, select a method to use for feature normalization. The following normalization methods are supported:  
  
    -   **Binning normalizer**. The binning normalizer creates bins of equal size, and then normalizes every value in each bin to be divided by the total number of bins.  
  
    -   **Gaussian normalizer**. The Gaussian normalizer rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature, and then, for each instance, subtracting the mean value and dividing by the square root of the variance (the standard deviation).  
  
    -   **Min-max normalizer**.  The min-max normalizer linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize**. No normalization is performed.  
  
10. Select the **Shuffle examples** option to shuffle cases between iterations.  
  
     If you deselect this option, cases are processed in exactly the same order each time you run the experiment.  
  
11. For **Random number seed**, type a value to use as the seed.  
  
     Specifying a seed value is useful when you want to ensure repeatability across runs of the same experiment.  
  
12. Select the **Allow unknown categorical levels** option to create a grouping for Unknown values in the training and validation sets.  
  
     If you deselect it, the model can accept only the values contained in the training data. In the former case, the model might be less precise on known values but provide better predictions for new (unknown) values.  
  
13. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, connect a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, connect a tagged dataset and train the model by using [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    > [!NOTE]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
14. When the model is trained, right-click the output of the [Train Model](train-model.md) module (or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module) and select **Visualize** to see a summary of the model's parameters, together with the feature weights learned from training, and other parameters of the neural network.  
  
##  <a name="bkmk_Customizing"></a> More About Net#  
 In Azure Machine Learning, you can customize the architecture of the neural network model by using the Net# language.  Customizations supported by the Net# language include:  
  
-   Creating hidden layers and controlling the number of nodes in each layer  
  
-   Specifying how layers are to be connected to each other  
  
-   Defining special connectivity structures, such as convolutions and weight-sharing bundles  
  
-   Specifying activation functions  
  
 A neural network model is defined by the structure of its graph, which includes these attributes:  
  
-   Number of hidden layers  
  
-   Number of nodes in each hidden layer  
  
-   Connections between the layers  
  
-   Choice of activation functions  
  
-   Weights on the graph edges  
  
 The structure of the graph and the activation function are determined by the user. The weights on the edges are learned when training the neural network on the input data.  
  
-   The first layer is always the input layer.  
  
-   The last layer is always the output layer. The number of nodes in the output layer should be equal to the number of classes.  
  
-   You can define any number of intermediate layers (sometimes called hidden layers, because they are contained within the model, and they are not directly exposed as endpoints).  
  
 The Net# reference guide explains the syntax and provides sample network definitions. It explains how you can use Net# to add hidden layers and define the way that the different layers interact with each other.  
  
 For more information, see: [Guide to the Net# Neural Networks Specification Language](http://go.microsoft.com/fwlink/?LinkId=402867)  
  
## Examples  
 For examples of how this learning algorithm is used, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/). The experiments are related and described in a single document that progresses from basic to advanced configurations:  
  
-   [Deep Neural networks sample (part A)](http://go.microsoft.com/fwlink/?LinkId=525278)  
  
-   [Deep Neural networks sample (part B)](http://go.microsoft.com/fwlink/?LinkId=525279)  
  
-   [Deep Neural networks sample (part C)](http://go.microsoft.com/fwlink/?LinkId=525280)  
  
-   [Deep Neural networks sample (part D)](http://go.microsoft.com/fwlink/?LinkId=525281)  
  
##  <a name="Notes"></a> Technical Notes  
 A neural network can be thought of as a weighted and directed acyclic graph. The nodes of the graph are arranged in layers, and they are connected by weighted edges to nodes in the next layer. To compute the output of the network given a certain input, a value is calculated for each node in the hidden layers and in the output layer. For each node, the value is set by calculating the weighted sum of the values of the nodes in the previous layer and applying an activation function to that weighted sum.  
  
 Neural networks can be computationally expensive, due to a number of hyperparameters and the introduction of custom network topologies. Although in many cases neural networks produce better results than other algorithms, obtaining such results may involve fair amount of sweeping (iterations) over hyperparameters.  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Hidden layer specification|List|Neural Network Topology|Fully-connected case|Specify the architecture of the hidden layer or layers|  
|The initial learning weights diameter|>=double.Epsilon|Float|0.1|Specify the node weights at the start of the learning process|  
|Learning rate|[double.Epsilon;1.0]|Float|0.1|Specify the size of each step in the learning process|  
|The momentum|[0.0;1.0]|Float|0.0|Specify a weight to apply during learning to nodes from previous iterations|  
|Neural network definition|Any|StreamReader||When you select **Custom definition script**, type a valid script expression on each line to define the layers, nodes, and behavior of a custom neural network|  
|The type of normalizer|List|Normalization Method|Min-Max normalizer|Select the type of normalization to apply to learning examples|  
|Number of learning iterations|>=1|Integer|100|Specify the number of iterations performed during learning|  
|Shuffle examples|Any|Boolean|true|Select this option to change the order of instances between learning iterations|  
|Random number seed|Any|Integer||Specify a numeric seed to use for random number generation. Leave it blank to use the default seed.|  
|Allow unknown categorical levels|Any|Boolean|True|Indicated whether an additional level should be created for unknown categories. If the test dataset contains categories that are not present in the training dataset, they are mapped to this unknown level.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  
  
## See Also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [Neural Network Regression](neural-network-regression.md)   
 [Multiclass Neural Network](multiclass-neural-network.md)   
 [A-Z Module List](a-z-module-list.md)