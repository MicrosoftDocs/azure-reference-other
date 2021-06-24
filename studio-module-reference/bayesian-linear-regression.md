---
title: "ML Studio (classic): Bayesian Linear Regression - Azure"
description: Learn how to use the Bayesian Linear Regression module to define a regression model based on Bayesian statistics.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Bayesian Linear Regression

*Creates a Bayesian linear regression model*  


Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  
 
This article describes how to use the **Bayesian Linear Regression** module in Machine Learning Studio (classic), to define a regression model based on Bayesian statistics.  
  
After you have defined the model parameters, you must train the model using a tagged dataset and the [Train Model](train-model.md) module.  The trained model can then be used to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.
  
## More about Bayesian regression  

In statistics, the *Bayesian* approach to regression is often contrasted with the *frequentist* approach.  
  
The Bayesian approach uses linear regression supplemented by additional information in the form of a prior probability distribution. Prior information about the parameters is combined with a likelihood function to generate estimates for the parameters.  
  
In contrast, the frequentist approach, represented by standard least-square linear regression, assumes that the data contains sufficient measurements to create a meaningful model.  
 
For more information about the research behind this algorithm, see the links in the [Technical Notes](#bkmk_Notes) section.
  
## How to configure Bayesian Regression 
  
1.  Add the **Bayesian Linear Regression** module to your experiment.  You can find the this module  under **Machine Learning**, **Initialize**, in the **Regression** category. 

2. **Regularization weight**: Type a value to use for regularization. Regularization is used to prevent overfitting. This weight corresponds to L2. For more information, see the [Technical Notes](#bkmk_Notes) section.  
  
3. **Allow unknown categorical levels**: Select this option to create a grouping for unknown values.  The model can accept only the values contained in the training data. The model might be less precise on known values but provide better predictions for new (unknown) values.

4. Connect a training dataset, and one of the training modules. This model type has no parameters that can be changed in a parameter sweep, so although you can train the model using [Tune Model Hyperparameters](tune-model-hyperparameters.md), it cannot automatically optimize the model.

5. Select the single numeric column that you want to model or predict.  

6.  Run the experiment.  

### Results

After training is complete:

+ To see a summary of the model's parameters, right-click the output of the [Train Model](train-model.md) module and select **Visualize**.
+ To create predictions, use the trained model as an input to [Score Model](score-model.md).

## Examples

For examples of regression models, see the [Azure AI Gallery](https://gallery.azure.ai).
  
- [Compare Regression Models sample](https://go.microsoft.com/fwlink/?LinkId=525731): Contrasts several different kinds of regression models.  
  
## <a name="bkmk_Notes"></a>Technical notes

+ The use of the lambda coefficient is described in detail in this textbook on machine learning: [Pattern Recognition and Machine Learning](https://www.springer.com/gb/book/9780387310732), Christopher Bishop, Springer-Verlag, 2007. 

+ This article is available as a PDF download from the [Microsoft Research site](https://research.microsoft.com/en-us/um/people/cmbishop/PRML/):  [Bayesian Regression and Classification](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/bishop-nato-bayes.pdf)

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Regularization weight|>=double.Epsilon|Float|1.0|Type a constant to use in regularization. The constant represents the ratio of the precision of weight prior to the precision of noise.|  
|Allow unknown categorical levels|Any|Boolean|true|If true creates an additional level for each categorical column. Any levels in the test dataset not available in the training dataset are mapped to this additional level.|  
  
## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained Bayesian linear regression model|  

## See also

 [A-Z Module List](a-z-module-list.md)   
 [Regression](machine-learning-initialize-model-regression.md)
