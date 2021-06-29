---
title: "ML Studio (classic): Two-Class Locally Deep SVM - Azure"
description: Learn how to use the Two-Class Locally Deep Support Vector Machine module to create a two-class, non-linear support vector machines (SVM) classifier optimized for efficient prediction.  
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Locally Deep Support Vector Machine
*Creates a binary classification model using the locally deep Support Vector Machine algorithm*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
##  Module overview  

This article describes how to use the **Two-Class Locally Deep Support Vector Machine** module in Machine Learning Studio (classic), to create a two-class, non-linear support vector machines (SVM) classifier that is optimized for efficient prediction.  

Support vector machines (SVMs) are an extremely popular and well-researched class of supervised learning models, which can be used in linear and non-linear classification tasks. Recent research has focused on ways to optimize these models to efficiently scale to larger training sets. In this implementation from Microsoft Research, the kernel function that is used for mapping data points to feature space is specifically designed to reduce the time needed for training while maintaining most of the classification accuracy.  

This model is a supervised learning method, and therefore requires a *tagged dataset*, which includes a label column.  

After you define the model parameters, train it by providing the model and a tagged dataset as input to [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for new inputs.

## How to configure Two-Class Locally Deep Support Vector Machine
  
1.  Add the **Two-Class Locally-Deep Support Vector Machine** module to your experiment in Studio (classic).  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, provide a specific set of values as arguments.  
  
    -   **Parameter Range**: If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer iterates over multiple combinations of the settings you provided and determines the combination of values that produces the best model.
  
3.  For **Depth of the tree**, specify the maximum depth of the tree that can be created by the local deep kernel learning SVM (LD-SVM) model.  
  
     The cost of training increases linearly with tree depth; therefore, choose an appropriate depth, depending on how much time you can afford to spend when building the model.  
  
    Training time should roughly double as the depth is increased by one.
  
    Prediction accuracy should increase, reach a peak, and then decrease with increasing depth.  
  
4.  For **Lambda W**, specify the weight that should be given to the regularization term.  
  
     Regularization restricts large value components in the trained classifier. When the number of samples is insufficient given the number of features, you can use L2 regularization to avoid overfitting. Larger values for **Lambda W** mean that more emphasis is placed on regularizing the classifier weights and less on the training-set classification error.  
  
     If the default value (0.1) doesn’t work well, you should also try {0.0001, 0.001 and 0.01}.  
  
5.  For **Lambda Theta**, specify how much space should be left between a region boundary and the closest data point.  
  
     This model works by partitioning the data space and feature space into regions. When **Lambda Theta** is minimized in such a way that region boundaries in the trained model are too close to the training data points, the model might yield a low training error, but a high test error, due to overfitting.
  
     To reduce the number of parameters that need to be validated, a good rule of thumb is to set **Lambda Theta** to one-tenth of the value that is used for **Lambda W**. Larger values mean that more emphasis is put on preventing overfitting than on minimizing classification errors in the training set.  
  
     If the default value (0.01) doesn’t work well, you should also try {0.0001, 0.001 and 0.1}.  
  
6.  For **Lambda Theta Prime**, type a value to control the amount of curvature that is allowed in decision boundaries in the model.  
  
     Larger values give the model the flexibility to learn curved decision boundaries, while smaller values might constrain the decision boundaries to more of a stepwise linear pattern.  
  
     This parameter works in conjunction with the **Sigma** parameter. To reduce the number of parameters that need to be validated, a good rule of thumb is to set **Lambda Theta Prime** to one-tenth the value of **Lambda W**.  
  
     If the default value (0.01) doesn’t work well, you should also try {0.0001, 0.001 and 0.1,}.  
  
7.  For **Sigmoid sharpness**, type a value to use for the scaling parameter σ.  
  
     Larger values mean that the **tanh** in local kernel Θ (theta) is saturated, whereas a smaller value implies a more linear operating range for theta. You can find the full optimization formula in the [Technical Notes](#bkmk_Notes) section.  
  
     If the default value (1) does not work well, you can also try {0.1, 0.01, 0.001}.  
  
8.  In **Number of iterations**, indicate how many times the algorithm should update the classifier parameters with a random subset of examples.  
  
9. For **Feature normalizer**, choose a method to use in normalizing feature values. The following  methods are supported:  
  
    -   **Binning normalizer**: The binning normalizer creates bins of equal size, and then normalizes every value in each bin to be divided by the total number of bins.  
  
    -   **Gaussian normalizer**: The Gaussian normalizer rescales the values of each feature to have a mean of 0 and a variance of 1. This is done by computing the mean and the variance of each feature. Then, for each instance, the mean value is subtracted, and the result divided by the square root of the variance (the standard deviation).
  
    -   **Min-Max normalizer**: The min-max normalizer linearly rescales every feature to the [0,1] interval.  
  
         Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).  
  
    -   **Do not normalize**: No normalization is performed.  
  
10. In **Random number seed**, type a value to use as a seed if you want to ensure reproducibility across runs.  
  
11. Select the **Allow unknown categorical levels** option to create a group for unknown values in the testing or validation sets.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. In the former case, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.
  
12. Connect a tagged dataset and one of the [training modules](machine-learning-train.md):   
  
    -   If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!NOTE]
    >  
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.  

13. Run the experiment.

### Results

After training is complete:

+ To see a summary of the model's parameters, right-click the output of the [Train Model](train-model.md) module or [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, and select **Visualize**. 

+ To save a snapshpt of the trained model, right-click the **Trained model** output and select **Save As Trained Model**. This model is not updated on successive runs of the same experiment.

+  To perform cross-validation against a labeled data set, connect the untrained model to [Cross-Validate Model](cross-validate-model.md).

##  <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

This LD-SVM classifier is most useful under the following conditions:  
  
-   You have a binary classification issue, or you can reduce your issue to a binary classification task.  
  
-   You tried a linear classifier, but it did not perform well.  
  
-   You tried a non-linear SVM or other classifier, and got good classification accuracy, but it took too long to train the model.  
  
-   You can afford to sacrifice prediction accuracy to reduce training time.  
  
LD-SVM models are a good choice when your data is complicated enough that linear models (such as logistic regression) perform poorly. LD-SVM models are also small enough to be used in mobile devices or other scenarios where complex models (such as neural networks) are too big to be consumed efficiently.  
  
Conversely, this model should not be used if you don’t care about model size or if a linear model is required for simplicity or prediction speed. There is also no point to changing to LD-SVM if linear classifiers are already giving good results, or if you can get high classification accuracy by adding small amounts of non-linearity.  
  
### Implementation details

The LD-SVM model was developed by Microsoft Research as part of ongoing efforts to speed up non-linear SVM prediction. The work of Gonen and Alpaydin (2008) on the localized multiple kernel learning method was particularly valuable. Use of a local kernel function enables the model to learn arbitrary local feature embeddings, including high-dimensional, sparse, and computationally deep features that introduce non-linearities into the model.  
  
LD-SVM is faster than most other classifiers for several reasons:  
  
-   The model learns decision boundaries that are locally linear. Therefore, a test point can be efficiently classified by testing it against its local decision boundary, rather than testing against the entire set of decision boundaries all over feature space.  
  
-   The model uses efficient primal-based routines to optimize the space of tree-structured local feature embeddings that scale to large training sets with more than half a million training points.  
  
-   The cost of testing a point against its local decision boundary is logarithmic in the number of training points.  
  
As a consequence of these optimizations, training the LD-SVM model is exponentially faster than training traditional SVM models.  
  
**Optimization formula**  
  
 ![optimization formula](media/aml-ldsvm-optimization.png "AML_LDSVM_optimization")  
  
### Research

For more information about the algorithm and underlying research, see [Local Deep Kernel Learning for Efficient Non-linear SVM Prediction](https://go.microsoft.com/fwlink/?LinkId=511662).  

##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Create trainer mode|List|Learner parameter option|Single Parameter|Advanced learner options:<br /><br /> 1.  Create learner using a single parameter<br />2.  Create learner using a parameter range|  
|Depth of the tree|>=1|Integer|3|The depth of the locally deep SVM tree.|  
|Lambda W|>=1.401298E-45|Float|0.1|Regularization weight for the classifier parameter Lambda W.|  
|Lambda Theta|>=1.401298E-45|Float|0.01|Regularization weight for the classifier parameter Lambda Theta.|  
|Lambda Theta Prime|>=1.401298E-45|Float|0.01|Regularization weight for the classifier parameter Lambda Theta prime.|  
|Sigmoid sharpness|>=1.401298E-45|Float|1.0|The sigmoid sharpness.|  
|Depth of the tree|[1;int.MaxValue]|ParameterRangeSettings|1; 3; 5; 7|The range for the depth of the locally deep SVM tree.|  
|Lambda W|[1.401298E-45;3.40282347E+38]|ParameterRangeSettings|0.1; 0.01; 0.001|Range for the regularization weight for the classifier parameter Lambda W.|  
|Lambda Theta|[1.401298E-45;3.40282347E+38]|ParameterRangeSettings|0.1; 0.01; 0.001|Range for the regularization weight for the classifier parameter Lambda Theta.|  
|Lambda Theta Prime|[1.401298E-45;3.40282347E+38]|ParameterRangeSettings|0.1; 0.01; 0.001|Range for the regularization weight for the classifier parameter Lambda Theta prime'.|  
|Sigmoid sharpness|[1.401298E-45;3.40282347E+38]|ParameterRangeSettings|1.0; 0.1; 0.01|The range for the sigmoid sharpness.|  
|Feature normalizer|List|Normalizer type|Min-Max normalizer|The type of normalization to apply to learning examples.|  
|Number of iterations|>=1|Integer|15000|Number of learning iterations.|  
|Number of iterations|[1;int.MaxValue]|ParameterRangeSettings|10000; 15000; 20000|The range for the number of learning iterations.|  
|*Random number seed*|Any|Integer||The seed for the random number generator that is used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|If True, creates an additional level for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model.|  
  
## See also  
 [Classification](machine-learning-initialize-model-classification.md)   
 [A-Z Module List](a-z-module-list.md)
