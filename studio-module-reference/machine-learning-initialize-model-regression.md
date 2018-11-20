---
title: "Machine Learning - Initialize Model - Regression | Microsoft Docs"
description: Description of the modules in Azure Machine Learning Studio that support creation of regression models.
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 97f9510f-60ba-4d78-8a33-3078a6c7f260
caps.latest.revision: 11
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Machine Learning - Initialize Model - Regression

This article describes the modules in Azure Machine Learning Studio that support creation of regression models.

For general information about modules in Machine Learning Studio, and how they can be combined to create complete machine learning experiments, see [Machine learning modules](machine-learning-modules.md).

## More about regression

Regression is a methodology used widely in fields ranging from engineering to education. For example, you might use regression to predict the value of a house based on regional data, or to create projections about future enrollment.

Regression tasks are supported in many tools: for example, Excel provides "What If" analysis, forecasting over time, and the Analysis ToolPak for traditional regression.

The modules for regression in Machine Learning Studio each incorporate a different method, or algorithm, for regression. In general, a regression algorithm tries to learn the value of a function for a particular instance of data. You might predict someone's height by using a height function, or predict the probability of hospital admission based on medical test values.

Regression algorithms can incorporate input from multiple features, by determining the contribution of each feature of the data to the regression function.

### How to create a regression model

First, select the regression algorithm that meets your needs and suits your data. For help, see these topics:  
  
-   [Machine learning algorithm cheat sheet for Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/studio/algorithm-cheat-sheet)  

    Provides a graphical decision chart to guide you through the selection process.  
  
-   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://docs.microsoft.com/azure/machine-learning/studio/algorithm-choice)  
  
     Explains in greater detail the different types of machine learning algorithms, and how they're used.  

Add training data. Be sure to consult the module reference for each algorithm in advance, to determine if the training data has any special requirements, other than a numeric outcome. 

To train the model, run the experiment. After the regression algorithm has learned from the labeled data, you can use the function it learned to make predictions on new data.

##  List of modules

+ [Bayesian Linear Regression](bayesian-linear-regression.md): Creates a Bayesian linear regression model.
+ [Boosted Decision Tree Regression](boosted-decision-tree-regression.md): Creates a regression model by using the Boosted Decision Tree algorithm.
+ [Decision Forest Regression](decision-forest-regression.md): Creates a regression model by using the decision forest algorithm.
+ [Fast Forest Quantile Regression](fast-forest-quantile-regression.md): Creates a quantile regression model.
+ [Linear Regression](linear-regression.md): Creates a linear regression model.
+ [Neural Network Regression](neural-network-regression.md): Creates a regression model by using a neural network algorithm.
+ [Ordinal Regression](ordinal-regression.md): Creates an ordinal regression model.
+ [Poisson Regression](poisson-regression.md): Creates a regression model that assumes data has a Poisson distribution.

## Examples

For examples of regression in action, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/).


## See also  
- [Regression](machine-learning-initialize-model-regression.md)   
- [Classification](machine-learning-initialize-model-classification.md)   
- [Clustering](machine-learning-initialize-model-clustering.md)   
- [Text Analytics](text-analytics.md)   
- [OpenCV Library Modules](opencv-library-modules.md)