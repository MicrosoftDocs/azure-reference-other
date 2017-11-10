---
title: "Neural Network Regression | Microsoft Docs"
ms.custom: ""
ms.date: 06/14/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d7ee222c-669f-4200-a576-a761a9c1a928
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Neural Network Regression
*Creates a regression model using a neural network algorithm*  
  
 Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Neural Network Regression** module to create a regression model using a customizable neural network algorithm.  
  
 Although neural networks are widely known for use in deep learning and modeling complex problems such as image recognition, they are easily adapted to regression problems. Any class of statistical models can be termed a neural network if they use adaptive weights and can approximate non-linear functions of their inputs. Thus neural network regression is suited to problems where a more traditional regression model cannot fit a solution.  
  
 Neural network regression is a supervised learning method, and therefore requires a *tagged dataset*, which includes a label column. Because a regression model predicts a numerical value, the label column must be a numerical data type.  
  
 You can train the model by providing the model and the tagged dataset as an input to [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for the new input examples.  
  
## How to Configure a Neural Network Model  
 Neural networks can be extensively customized:  
  
-   If you accept the default neural network architecture,  use the **Properties** pane to set parameters that control the behavior of the neural network, such as the number of nodes in the hidden layer, learning rate, and normalization.  
  
     [To create a neural network model using the default architecture](#bkmk_DefaultArchitecture)  
  
-   If you want to add more hidden layers, or fully customize the network architecture, its connections, and activation functions, use the [Net# language](#bkmk_NetSharp).  
  
     [To define a custom architecture for a neural network](#bkmk_CustomArchitecture)  
  
###  <a name="bkmk_DefaultArchitecture"></a> To create a neural network model using the default architecture  
  
1.  Add the **Neural Network Regression** module to your experiment.  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                    If you know how you want to configure the neural network, type a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using a [Tune Model Hyperparameters](tune-model-hyperparameters.md) to find the optimal configuration.                    Multiple combinations of the settings you provided are tested to determine the model with the optimal results.  
  
3.  In **Hidden layer specification**, select **Fully-connected case**. This option creates a model using the default neural network architecture, which for a neural network regression model, has these attributes:  
  
    -   The network has exactly one hidden layer.  
  
    -   The output layer is fully connected to the hidden layer and the hidden layer is fully connected to the input layer.  
  
    -   The number of nodes in the hidden layer can be set by the user (default value is 100).  
  
    -   Because the number of nodes in the input layer is determined by the number of features in the training data, in a regression model there can be only one node in the output layer.  
  
4.  For **Number of hidden nodes**, type the number of hidden nodes. The default is one hidden layer with 100 nodes.  
  
     This option is not available if you define a custom architecture using Net#.  
  
5.  For                  **Learning rate**, type a value that defines the step taken at each iteration, before correction.  
  
     A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.  
  
6.  For **Number of learning iterations**, specify the maximum number of times the algorithm processes the training cases.  
  
7.  For **The initial learning weights diameter** , type a value that determines the node weights at the start of the learning process.  
  
8.  For                  **The momentum**, type a value to apply during learning as a weight on nodes from previous iterations.  
  
9. For                  **The type of normalizer**, choose one of the following methods to use for feature normalization:  
  
    -   **Binning normalizer** : Binning creates groups of equal size, and then normalizes every value in each group to be divided by the total number of groups.  
  
    -   **Gaussian normalizer** :Gaussian normalization rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature, and then, for each instance, subtracting the mean value and dividing by the square root of the variance (the standard deviation).  
  
    -   **Min-Max normalizer** : Min-max normalization linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize** : No normalization is performed.  
  
10. Select the option, **Shuffle examples**, to change the order of cases between iterations.  
  
     If you deselect this option, cases are processed in exactly the same order each time you run the experiment.  
  
11. For **Random number seed**, you can optionally type a value to use as the seed.  
  
     Specifying a seed value is useful when you want to ensure repeatability across runs of the same experiment.  
  
12. Select the option **Allow unknown categorical levels** to create a grouping for unknown values. If you deselect it, the model can accept only the values contained in the training data.  
  
     In the former case, the model might be less precise on known values but provide better predictions for new (unknown) values.  
  
13. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, train the model by using a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, train the model by connecting a tagged dataset and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!WARNING]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
14. Run the experiment.  
  
     After the model is trained, you can view the model parameters by right-clicking the trainer output and selecting **Visualize**. You can also use the trained model for prediction.  
  
###  <a name="bkmk_CustomArchitecture"></a> To define  a custom architecture for a neural network  
  
1.  Add the **Neural Network Regression** module to your experiment.  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                    If you know how you want to configure the neural network, type a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using a [Tune Model Hyperparameters](tune-model-hyperparameters.md) to find the optimal configuration.                    Multiple combinations of the settings you provided are tested to determine the model with the optimal results.  
  
3.  In **Hidden layer specification**, select **Custom definition script**. You must choose this option if you want to define a custom neural network architecture by using the **Net#** language.  
  
4.  After you select the **Custom definition script** option, the **Neural network definition** text box is displayed. You can paste in Net# script to define a custom architecture for the neural network, including the number of hidden layers, their connections, and advanced options such as specifying the mappings between layers.  
  
     For example, the following script uses the `auto` keyword, which sets the number of features automatically for input and output layers, and uses the default values for the hidden layer.  
  
    ```  
    input Data auto;  
    hidden Hidden auto from Data all;  
    output Result auto from Hidden all;   
    ```  
  
     For script examples, see [Guide to the Net# Neural Networks Specification Language](http://go.microsoft.com/fwlink/?LinkId=402867).  
  
5.  For                  **Learning rate**, type a value that defines the step taken at each iteration, before correction.  
  
     A larger value for learning rate can cause the model to converge faster, but it can overshoot local minima.  
  
6.  For **Number of learning iterations**, specify the maximum number of times the algorithm processes the training cases.  
  
7.  For **The initial learning weights diameter** , type a value that determines the node weights at the start of the learning process.  
  
8.  For                  **The momentum**, type a value to apply during learning as a weight on nodes from previous iterations.  
  
9. For                  **The type of normalizer**, choose one of the following methods to use for feature normalization:  
  
    -   **Binning normalizer** : Binning creates groups of equal size, and then normalizes every value in each group to be divided by the total number of groups.  
  
    -   **Gaussian normalizer** :Gaussian normalization rescales the values of each feature to have mean 0 and variance 1. This is done by computing the mean and the variance of each feature, and then, for each instance, subtracting the mean value and dividing by the square root of the variance (the standard deviation).  
  
    -   **Min-Max** : Min-max normalization linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize** : No normalization is performed.  
  
10. Select the option, **Shuffle examples**, to change the order of cases between iterations.  
  
     If you deselect this option, cases are processed in exactly the same order each time you run the experiment.  
  
11. For **Random number seed**, you can optionally type a value to use as the seed.  
  
     Specifying a seed value is useful when you want to ensure repeatability across runs of the same experiment.  
  
12. Select the option **Allow unknown categorical levels** to create a grouping for unknown values. any unknown values in the test data set are mapped to this unknown category. Using this option might make the model slightly less precise on known values but provide better predictions for new (unknown) values.  
  
     If you deselect this option, the model can make predictions only for the values contained in the training data.  
  
13. Train the model.  
  
    -   If you set **Create trainer mode** to **Single Parameter**, train the model by using a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, train the model by connecting a tagged dataset and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!WARNING]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
14. Run the experiment.  
  
     After the model is trained, you can view the model parameters, including the Net# model definition, by right-clicking the trainer output and selecting **Visualize**. You can also use the trained model for prediction.  
  
###  <a name="bkmk_NetSharp"></a> More About Net#  
 A neural network model is defined by the structure of its graph, which includes these attributes:  
  
-   Number of hidden layers  
  
-   Number of nodes in each hidden layer  
  
-   Connections between the layers  
  
-   Choice of activation functions  
  
-   Weights on the graph edges  
  
 You can change the architecture of neural network models that you create by using the Net# language:  
  
-   Creating hidden layers and controlling the number of nodes in each layer.  
  
-   Specifying how layers are to be connected to each other.  
  
-   Defining special connectivity structures, such as convolutions and weight sharing bundles.  
  
-   Specifying different activation functions.  
  
 The Net# reference guide explains the syntax and provides sample network definitions. It explains how you can use Net# to add hidden layers and define the way that the layers interact with each other. For more information, see:  
  
 [Guide to the Net# Neural Networks Specification Language](http://go.microsoft.com/fwlink/?LinkId=402867)  
  
##  <a name="bkmk_Examples"></a> Examples  
 For examples of how this algorithm is used in experiments, see these samples in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Compare Multiple Regressors](http://go.microsoft.com/fwlink/?LinkId=525731) sample demonstrates the use of several regression algorithms and compares their results.  
  
##  <a name="bkmk_Notes"></a> Technical Notes  
 A neural network can be thought of as a weighted directed acyclic graph. The nodes of the graph are arranged in layers and are connected by weighted edges to nodes in the next layer. The first layer is called the input layer. The last layer is called the output layer. In the case of a regression model, the output layer contains a single node.  
  
 The remaining layers are called hidden layers. To compute the output of the network on a given input example, a value is calculated for each node in the hidden layers and in the output layer. For each node, the value is set by calculating the weighted sum of the values of the nodes in the previous layer and applying an activation function to that weighted sum.  
  
 A neural network model is defined by the structure of its graph, which includes these attributes:  
  
-   Number of hidden layers  
  
-   Number of nodes in each hidden layer  
  
-   Connections between the layers  
  
-   Choice of activation functions  
  
-   Weights on the graph edges  
  
 The structure of the graph and the activation function are determined by the user. The weights on the edges are learned when training the neural network on the input data.  
  
 Neural networks can be computationally expensive, due to a number of hyperparameters and the introduction of custom network topologies. Although in many cases neural networks produce better results than other algorithms, obtaining such results may involve fair amount of sweeping (iterations) over hyperparameters.  
  
##  <a name="parameters"></a> Module Parameters  
  
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
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  
  
## See Also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [A-Z Module List](a-z-module-list.md)