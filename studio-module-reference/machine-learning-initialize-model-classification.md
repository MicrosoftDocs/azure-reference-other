---
title: "Machine Learning - Initialize Model - Classification | Microsoft Docs"
ms.custom: ""
ms.date: 10/06/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0d90dcab-08e1-4a66-9ea1-b571c22ae74d
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning - Initialize Model - Classification
This article lists the classification modules that are provided in Azure Machine Learning Studio. You can use these modules to build a binary or multiclass classification model.

## What is classification?  
  
 Classification is a method in machine learning of using data to determine the category, type, or class of an item or row of data. For example, these are all uses for classification:
 
+ Classify email filters as spam, junk, or good. 
+ Detemrine whether a cytoscopy specimem is potentially cancerous or not
+ Categorize customers by their propensity to respond to a sales campaign
+ Identify sentiment as positive or negative

To create a classification model, or classifier, you configure a classification algorithm using the modules in this section, and then train the model on labeled data. Classification is a supervised machine learning method and therefore always requires labeled training data.

Classification tasks are frequently organized as to whether classification is binary (either A or B) or multiclass (multiple categories can be predicted using a single model). 

Azure Machine Learning Studio provides multiple classification algorithms of both types. The [One vs All](one-vs-all-multiclass.md) algorithm even lets you apply a binary classifier to a multi-class problem.
  
For guidance on how to pick a classification algorithm, see these articles:  
  
-   [Machine learning algorithm cheat sheet for Azure ML](https://docs.microsoft.com/azure/machine-learning/studio/algorithm-cheat-sheet)  
  
     Provides a graphical decision chart to guide you through the selection process.  
  
-   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://docs.microsoft.com/azure/machine-learning/studio/algorithm-choice)  
  
     Explains in greater detail the different types of machine learning algorithms and how they're used.  
  
##  <a name="modules"></a> List of Modules  

 This category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Multiclass Decision Forest](multiclass-decision-forest.md)|Creates a multiclass classification model using the decision forest algorithm|  
|[Multiclass Decision Jungle](multiclass-decision-jungle.md)|Creates a multiclass classification model using the decision jungle algorithm|  
|[Multiclass Logistic Regression](multiclass-logistic-regression.md)|Creates a multiclass logistic regression classification model|  
|[Multiclass Neural Network](multiclass-neural-network.md)|Creates a multiclass classification model using a neural network algorithm|  
|[One-vs-All Multiclass](one-vs-all-multiclass.md)|Creates a multiclass classification model from an ensemble of binary classification models|  
|[Two-Class Averaged Perceptron](two-class-averaged-perceptron.md)|Creates an averaged perceptron binary classification model|  
|[Two-Class Bayes Point Machine](two-class-bayes-point-machine.md)|Creates a Bayes point machine binary classification model|  
|[Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md)|Creates a binary classifier using a boosted decision tree algorithm|  
|[Two-Class Decision Forest](two-class-decision-forest.md)|Creates a two-class classification model using the decision forest algorithm|  
|[Two-Class Decision Jungle](two-class-decision-jungle.md)|Creates a two-class classification model using the decision jungle algorithm|  
|[Two-Class Locally Deep Support Vector Machine](two-class-locally-deep-support-vector-machine.md)|Creates a binary classification model using the locally deep Support Vector Machine algorithm|  
|[Two-Class Logistic Regression](two-class-logistic-regression.md)|Creates a two-class logistic regression model|  
|[Two-Class Neural Network](two-class-neural-network.md)|Creates a binary classifier using a neural network algorithm|  
|[Two-Class Support Vector Machine](two-class-support-vector-machine.md)|Creates a binary classification model using the Support Vector Machine algorithm|  

  
## See Also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [Clustering](machine-learning-initialize-model-clustering.md)   
 [Text Analytics](text-analytics.md)   
 [Image classification](opencv-library-modules.md)   
 [A-Z Module List](a-z-module-list.md)