---
title: "ML Studio (classic): Neural Network Regression - Azure"
description: Learn how to use the Neural Network Regression module to create a regression model using a customizable neural network algorithm.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Neural Network Regression

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a regression model using a neural network algorithm*  
  
 Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Neural Network Regression** module in Machine Learning Studio (classic), to create a regression model using a customizable neural network algorithm.
  
 Although neural networks are widely known for use in deep learning and modeling complex problems such as image recognition, they are easily adapted to regression problems. Any class of statistical models can be termed a neural network if they use adaptive weights and can approximate non-linear functions of their inputs. Thus neural network regression is suited to problems where a more traditional regression model cannot fit a solution.
  
 Neural network regression is a supervised learning method, and therefore requires a *tagged dataset*, which includes a label column. Because a regression model predicts a numerical value, the label column must be a numerical data type.  
  
 You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  
  
## How to configure Neural Network Regression 

Neural networks can be extensively customized. This section describes how to create a model using two methods:
  
+ [Create a neural network model using the default architecture](#bkmk_DefaultArchitecture)  
  
    If you accept the default neural network architecture,  use the **Properties** pane to set parameters that control the behavior of the neural network, such as the number of nodes in the hidden layer, learning rate, and normalization.

    Start here if you are new to neural networks. The module supports many customizations, as well as model tuning, without deep knowledge of neural networks. 

+ [Define a custom architecture for a neural network](#bkmk_CustomArchitecture)  

    Use this option if you want to add extra hidden layers, or fully customize the network architecture, its connections, and activation functions.
    
    This option is best if you are already somewhat familiar with neural networks. You use the [Net# language](#bkmk_Customizing) to define the network architecture.  

###  <a name="bkmk_DefaultArchitecture"></a> Create a neural network model using the default architecture
  
1.  Add the **Neural Network Regression** module to your experiment in Studio (classic). You can find this module under **Machine Learning**, **Initialize**, in the **Regression** category. 
  
2. Indicate how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: Choose this option if you already know how you want to configure the model.  
  
    -   **Parameter Range**: Choose this option if you are not sure of the best parameters. Then, specify a range of values and use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to iterate over the combinations and find the optimal configuration.
  
3.  In **Hidden layer specification**, select **Fully-connected case**. This option creates a model using the default neural network architecture, which for a neural network regression model, has these attributes:  
  
    + The network has exactly one hidden layer.
    + The output layer is fully connected to the hidden layer and the hidden layer is fully connected to the input layer.
    + The number of nodes in the hidden layer can be set by the user (default value is 100).  
  
    Because the number of nodes in the input layer is determined by the number of features in the training data, in a regression model there can be only one node in the output layer.  
  
4. For **Number of hidden nodes**, type the number of hidden nodes. The default is one hidden layer with 100 nodes. (This option is not available if you define a custom architecture using Net#.)
  
5.  For **Learning rate**, type a value that defines the step taken at each iteration, before correction. A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.

6.  For **Number of learning iterations**, specify the maximum number of times the algorithm processes the training cases.

7.  For **The initial learning weights diameter** , type a value that determines the node weights at the start of the learning process.

8.  For **The momentum**, type a value to apply during learning as a weight on nodes from previous iterations.

9. For **The type of normalizer**, choose one of the following methods to use for feature normalization:  
  
    -   **Binning normalizer**: Binning creates groups of equal size, and then normalizes every value in each group to be divided by the total number of groups.  
  
    -   **Gaussian normalizer**: Gaussian normalization rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature, and then, for each instance, subtracting the mean value and dividing by the square root of the variance (the standard deviation).
  
    -   **Min-Max normalizer**: Min-max normalization linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize**: No normalization is performed.  
  
10. Select the option, **Shuffle examples**, to change the order of cases between iterations. If you deselect this option, cases are processed in exactly the same order each time you run the experiment.
  
11. For **Random number seed**, you can optionally type a value to use as the seed. Specifying a seed value is useful when you want to ensure repeatability across runs of the same experiment.
  
12. Select the option **Allow unknown categorical levels** to create a grouping for unknown values. The model might be less precise on known values but provide better predictions for new (unknown) values.

    If you deselect this option, the model can accept only the values contained in the training data.  
  
13. Connect a training datset and one of the [training modules](machine-learning-train.md): 
  
    -   If you set **Create trainer mode** to **Single Parameter**, use [Train Model](train-model.md).  
  
    -   If you set **Create trainer mode** to **Parameter Range**, use [Tune Model Hyperparameters](tune-model-hyperparameters.md).

    > [!WARNING]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.

14. Run the experiment.  

### <a name="bkmk_CustomArchitecture"></a> Define a custom architecture
  
1. Add the **Neural Network Regression** module to your experiment.  

2. Indicate how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: Choose this option if you already know how you want to configure the model.  
  
    -   **Parameter Range**: Choose this option if you are not sure of the best parameters. Then, specify a range of values and use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to iterate over the combinations and find the optimal configuration.

3.  In **Hidden layer specification**, select **Custom definition script**. You must choose this option if you want to define a custom neural network architecture by using the **Net#** language.  
  
4.  After you select the **Custom definition script** option, the **Neural network definition** text box is displayed. You can paste in Net# script to define a custom architecture for the neural network, including the number of hidden layers, their connections, and advanced options such as specifying the mappings between layers.

5.  For **Learning rate**, type a value that defines the step taken at each iteration, before correction. A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.
  
6.  For **Number of learning iterations**, specify the maximum number of times the algorithm processes the training cases.  

7.  For **The initial learning weights diameter** , type a value that determines the node weights at the start of the learning process.

8.  For **The momentum**, type a value to apply during learning as a weight on nodes from previous iterations.  

9. For **The type of normalizer**, choose one of the following methods to use for feature normalization:  
  
    -  **Binning normalizer**: Binning creates groups of equal size, and then normalizes every value in each group, by dividing by the total number of groups.
  
    -   **Gaussian normalizer**: Gaussian normalization rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature, and then, for each instance, subtracting the mean value and dividing by the square root of the variance (the standard deviation).
  
    -   **Min-Max**: Min-max normalization linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize**: No normalization is performed.  
  
10. Select the option, **Shuffle examples**, to change the order of cases between iterations. If you deselect this option, cases are processed in exactly the same order each time you run the experiment.
  
11. For **Random number seed**, you can optionally type a value to use as the seed. Specifying a seed value is useful when you want to ensure repeatability across runs of the same experiment.  
  
12. Select the option **Allow unknown categorical levels** to create a grouping for unknown values. Any unknown values in the test data set are mapped to this unknown category. Using this option might make the model slightly less precise on known values but provide better predictions for new (unknown) values.
  
     If you deselect this option, the model can make predictions only for the values contained in the training data.  
  
13. Connect a training datset and one of the [training modules](machine-learning-train.md): 
  
    -   If you set **Create trainer mode** to **Single Parameter**, use [Train Model](train-model.md).  
  
    -   If you set **Create trainer mode** to **Parameter Range**, use [Tune Model Hyperparameters](tune-model-hyperparameters.md).
  
    > [!WARNING]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  

14. Run the experiment.

### Results

After training is complete:

+ To see a summary of the model's parameters, together with the feature weights learned from training, and other parameters of the neural network, right-click the output of [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md), and select **Visualize**.  

+ To save a snapshot of the trained model, right-click the **Trained model** output and select **Save As Trained Model**. This model is not updated on successive runs of the same experiment.

+  To perform cross-validation against a labeled data set, connect the untrained model to [Cross-Validate Model](cross-validate-model.md).

##  Examples  

For examples of how this algorithm is used in experiments, see these samples in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Compare Multiple Regressors](https://go.microsoft.com/fwlink/?LinkId=525731): Demonstrates the use of several regression algorithms and compares their results.  

The experiments provide more help on Net#. The experiments are related and progress from basic to advanced configurations:

+ [Deep Neural networks example (part A)](https://go.microsoft.com/fwlink/?LinkId=525278)  
+ [Deep Neural networks example (part B)](https://go.microsoft.com/fwlink/?LinkId=525279)  
+ [Deep Neural networks example (part C)](https://go.microsoft.com/fwlink/?LinkId=525280)  
+ [Deep Neural networks example (part D)](https://go.microsoft.com/fwlink/?LinkId=525281)  

##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

###  <a name="bkmk_Customizing"></a> More about Net#  

In Machine Learning Studio (classic), you can customize the architecture of a neural network model by using the Net# language.  Customizations supported by the Net# language include:  

+ Specifying the number of hidden layers and the number of nodes in each layer  
+ Specifying mappings between layers
+ Defining convolutions and weight-sharing bundles  
+ Choosing the activation function  

A neural network model is defined by the structure of its graph, which includes these attributes:  

+ The number of hidden layers
+ The number of nodes in each hidden layer
+ How the layers are connected
+ Which activation function is used
+ Weights on the graph edges

> [!IMPORTANT]
> 
> The overall structure of the graph, as well as the activation function, can be specified by the user. However, the weights on the edges cannot be specified, and must be learned when training the neural network on the input data.

In general, the network has these defaults:

+ The first layer is always the input layer.
+ The last layer is always the output layer.
+ The number of nodes in the output layer should be equal to the number of classes.  

You can define any number of intermediate layers (sometimes called hidden layers, because they are contained within the model, and they are not directly exposed as endpoints).  

The Net# reference guide explains the syntax and provides sample network definitions. It explains how you can use Net# to add hidden layers and define the way that the different layers interact with each other. 

For example, the following script uses the `auto` keyword, which sets the number of features automatically for input and output layers, and uses the default values for the hidden layer.  

```text
input Data auto;  
hidden Hidden auto from Data all;  
output Result auto from Hidden all;   
```

For additional script examples, see [Guide to the Net# Neural Networks Specification Language](/azure/machine-learning/studio/azure-ml-netsharp-reference-guide).

> [!TIP]
> Neural networks can be computationally expensive, due to a number of hyperparameters and the introduction of custom network topologies. Although in many cases neural networks produce better results than other algorithms, obtaining such results may involve fair amount of sweeping (iterations) over hyperparameters.  

##  Module parameters  

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Hidden layer specification|List|Neural Network Topology|Fully-connected case|Specify the architecture of the hidden layer or layers|  
|The initial learning weights diameter|>=double.Epsilon|Float|0.1|Specify the node weights at the start of the learning process|  
|Learning rate|[double.Epsilon;0.01]|Float|0.005|Specify the size of each step in the learning process|  
|The momentum|[0.0;1.0]|Float|0.0|Specify a weight to apply during learning to nodes from previous iterations|  
|Neural network definition|Any|StreamReader||When you select "Custom definition script", type a valid script expression on each line to define the layers, nodes, and behavior of a custom neural network|  
|The type of normalizer|List|Normalization Method|Min-Max normalizer|Select the type of normalization to apply to learning examples|  
|Number of hidden nodes|Any|String|100|Type the number of nodes in the hidden layer. For multiple hidden layers, type a comma-separated list.|  
|Number of learning iterations|>=1|Integer|100|Specify the number of iterations while learning|  
|Shuffle examples|Any|Boolean|true|Select this option to change the order of instances between learning iterations|  
|Random number seed|Any|Integer||Specify a numeric seed to use for random number generation. Leave blank to use the default seed.<br /><br /> This parameter is optional|  
|Allow unknown categorical levels|Any|Boolean|true|Indicate whether an additional level should be created for unknown categories. If the test dataset contains categories not present in the training dataset they are mapped to this unknown level.|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  
  
## See also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [A-Z Module List](a-z-module-list.md)
