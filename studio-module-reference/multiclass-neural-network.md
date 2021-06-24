---
title: "ML Studio (classic): Multiclass Neural Network - Azure"
description: Learn  how to use the Multiclass Neural Network module to create a neural network model to predict a target that has multiple values. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Multiclass Neural Network

*Creates a multiclass classification model using a neural network algorithm*

Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Multiclass Neural Network** module in Machine Learning Studio (classic), to create a neural network model that can be used to predict a target that has multiple values. 

For example, neural networks of this kind might be used in complex computer vision tasks, such as digit or letter recognition, document classification, and pattern recognition.

Classification using neural networks is a supervised learning method, and therefore requires a *tagged dataset* that includes a label column.

You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or to [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  

### More about neural networks

A neural network is a set of interconnected layers. The inputs are the first layer, and are connected to an output layer by an acyclic graph comprised of weighted edges and nodes.

Between the input and output layers you can insert multiple hidden layers. Most predictive tasks can be accomplished easily with only one or a few hidden layers. However, recent research has shown that deep neural networks (DNN) with many layers can be very effective in complex tasks such as image or speech recognition. The successive layers are used to model increasing levels of semantic depth.

The relationship between inputs and outputs is learned from training the neural network on the input data. The direction of the graph proceeds from the inputs through the hidden layer and to the output layer. All nodes in a layer are connected by the weighted edges to nodes in the next layer.

To compute the output of the network for a particular input, a value is calculated at each node in the hidden layers and in the output layer. The value is set by calculating the weighted sum of the values of the nodes from the previous layer. An activation function is then applied to that weighted sum.

## How to configure Multiclass Neural Network

1. Add the **MultiClass Neural Network** module to your experiment in Studio (classic). You can find this module under **Machine Learning**, **Initialize**, in the **Classification** category.

2. **Create trainer mode**: Use this option to specify how you want the model to be trained:

    - **Single Parameter**: Choose this option if you already know how you want to configure the model.

    - **Parameter Range**: Choose this option if you are not sure of the best parameters, and want to use a parameter sweep. You then specify a range of values and use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to iterate over the combinations and find the optimal configuration.

3. **Hidden layer specification**: Select the type of network architecture to create.

    - **Fully-connected case**: Select this option to create a model using the default neural network architecture. For multiclass neural network models, the defaults are as follows:

        - One hidden layer
        - The output layer is fully connected to the hidden layer.
        - The hidden layer is fully connected to the input layer.
        - The number of nodes in the input layer is determined by the number of features in the training data.
        - The number of nodes in the hidden layer can be set by the user. The default is 100.
        - The number of nodes in the output layer depends on the number of classes.
  
    - **Custom definition script**. Choose this option to create a custom neural network architecture, using the Net# language. You can define the number of hidden layers, their connections, and advanced options such as specifying the mappings between layers. For an introduction to Net#, see [More About Net#](#bkmk_Customizing) later in this topic.

4. **Neural network definition**: If you selected the custom architecture option, use the text box to type or paste in statements written in the Net# language. For additional script examples, see [Guide to the Net# Neural Networks Specification Language](/azure/machine-learning/classic/azure-ml-netsharp-reference-guide).  

5. **Number of hidden nodes**: This option lets you customize the number of hidden nodes in the default architecture. Type the number of hidden nodes. The default is one hidden layer with 100 nodes.

6. **The learning rate**: Define the size of the step taken at each iteration, before correction.A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.

7. **Number of learning iterations**: Specify  the maximum number of times the algorithm should process the training cases.

8. **The initial learning weights diameter**: Specify the node weights at the start of the learning process.

9. **The momentum**: Specify a weight to apply during learning to nodes from previous iterations.

10. **The type of normalizer**: Select the method to use for feature normalization. The following normalization methods are supported:

    - **Binning normalizer**: The binning normalizer creates bins of equal size, and then normalizes every value in each bin, by dividing by the total number of bins.
  
    - **Gaussian normalizer**: The Gaussian normalizer rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature. For each instance, the mean value is subtracted, and the result divided by the square root of the variance (the standard deviation).

    - **Min-max normalizer**:  The min-max normalizer linearly rescales every feature to the [0,1] interval.
    
      Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    - **Do not normalize**: No normalization is performed.
  
11. **Shuffle examples**: Select this option to shuffle cases between iterations.

    If you deselect this option, cases are processed in exactly the same order each time you run the experiment.

12. **Random number seed**: Type a value to use as the seed, if you want to ensure repeatability across runs of the same experiment.

13. **Allow unknown categorical levels**: Select this option to create a grouping for unknown values in the training and validation sets. The model might be less precise on known values but provide better predictions for new (unknown) values.

    If you deselect this option, the model can accept only the values contained in the training data.  

14. Connect a training dataset and one of the [training modules](machine-learning-train.md): 

    - If you set **Create trainer mode** to **Single Parameter**, use [Train Model](train-model.md).  
  
    - If you set **Create trainer mode** to **Parameter Range**, use [Tune Model Hyperparameters](tune-model-hyperparameters.md).
  
    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.

### Results

After training is complete:

- To see a summary of the model's parameters, together with the feature weights learned from training, and other parameters of the neural network, right-click the output of [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md), and select **Visualize**.  

- To save a snapshot of the trained model, right-click the **Trained model** output and select **Save As Trained Model**. This model is not updated on successive runs of the same experiment.

- To perform cross-validation against a labeled data set, connect the untrained model to [Cross-Validate Model](cross-validate-model.md).

## Examples

For examples of how this learning algorithm is used, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/). The experiments are related and described in a single document that progresses from basic to advanced configurations:

- [Deep Neural networks example (part A)](https://go.microsoft.com/fwlink/?LinkId=525278)  
- [Deep Neural networks example (part B)](https://go.microsoft.com/fwlink/?LinkId=525279)  
- [Deep Neural networks example (part C)](https://go.microsoft.com/fwlink/?LinkId=525280)  
- [Deep Neural networks example (part D)](https://go.microsoft.com/fwlink/?LinkId=525281)  

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### <a name="bkmk_Customizing"></a> Customizing the neural network using script

In Machine Learning Studio (classic), you can customize the architecture of a neural network model by using the Net# language.  Customizations supported by the Net# language include:

- Specifying the number of hidden layers and the number of nodes in each layer
- Specifying mappings between layers
- Defining convolutions and weight-sharing bundles
- Choosing the activation function

A neural network model is defined by the structure of its graph, which includes these attributes:

- The number of hidden layers
- The number of nodes in each hidden layer
- How the layers are connected
- Which activation function is used
- Weights on the graph edges

> [!IMPORTANT]
> 
> The overall structure of the graph, as well as the activation function, can be specified by the user. However, the weights on the edges cannot be specified, and must be learned when training the neural network on the input data.

In general, the network has these defaults:

- The first layer is always the input layer.
- The last layer is always the output layer.
- The number of nodes in the output layer should be equal to the number of classes.

You can define any number of intermediate layers: these are sometimes called hidden layers, because they are contained within the model, and they are not directly exposed as endpoints.

The Net# reference guide explains the syntax and provides sample network definitions. It explains how you can use Net# to add hidden layers and define the way that the different layers interact with each other.

For example, the following script uses the `auto` keyword, which sets the number of features automatically for input and output layers, and uses the default values for the hidden layer.

```text
input Data auto;  
hidden Hidden auto from Data all;  
output Result auto from Hidden all;   
```

For additional script examples, see [Guide to the Net# Neural Networks Specification Language](/azure/machine-learning/classic/azure-ml-netsharp-reference-guide).

> [!TIP]
> Neural networks can be computationally expensive, due to a number of hyperparameters and the introduction of custom network topologies. Although in many cases neural networks produce better results than other algorithms, obtaining such results may involve fair amount of sweeping (iterations) over hyperparameters.

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Hidden layer specification|List|Neural Network Topology|Fully-connected case|Specify the architecture of the hidden layer or layers|  
|The initial learning weights diameter|>=double.Epsilon|Float|0.1|Specify the node weights at the start of the learning process|  
|The learning rate|[double.Epsilon;1.0]|Float|0.1|Specify the size of each step in the learning process|  
|The momentum|[0.0;1.0]|Float|0.0|Specify a weight to apply during learning to nodes from previous iterations|  
|Neural network definition|Any|StreamReader||When you select **Custom definition script**, type a valid script expression on each line to define the layers, nodes, and behavior of a custom neural network|  
|The type of normalizer|List|Normalization Method|Minimum-maximum normalizer|Select the type of normalization to apply to learning examples|  
|Number of learning iterations|>=1|Integer|100|Specify the number of iterations while learning|  
|Shuffle examples|Any|Boolean|True|Select this option to change the order of instances between learning iterations|  
|Random number seed|Any|Integer||Specify a numeric seed to use for random number generation. Leave blank to use the default seed.|  
|Allow unknown categorical levels|Any|Boolean|True|Indicate whether an additional level should be created for unknown categories. If the test dataset contains categories that are not present in the training dataset, they are mapped to this unknown level.|  

## Output

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained multiclass classification model|  

## See also

 [Classification](machine-learning-initialize-model-classification.md)   
 [Two-Class Neural Network](two-class-neural-network.md)   
 [Neural Network Regression](neural-network-regression.md)   
 [A-Z Module List](a-z-module-list.md)
