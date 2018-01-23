---
title: "Machine Learning - Initialize Model - Classification | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0d90dcab-08e1-4a66-9ea1-b571c22ae74d
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Machine Learning - Initialize Model - Classification

This article describes the modules in Azure Machine Learning Studio that support creation of classification models. You can use these modules to build a binary or multiclass classification model.

For general information about modules in Azure Machine Learning Studio, and how they can be combined to create complete machine learning experiments, see [Machine learning modules](machine-learning-modules.md).

## More about classification  

Classification is a method in machine learning of using data to determine the category, type, or class of an item or row of data. For example, classification can be used to:
 
+ Classify email filters as spam, junk, or good. 
+ Determine whether a patient's lab sample is cancerous or not
+ Categorize customers by their propensity to respond to a sales campaign
+ Identify sentiment as positive or negative



Classification tasks are frequently organized as to whether classification is binary (either A or B) or multiclass (multiple categories can be predicted using a single model). 

### How to create a classification model

To create a classification model, or classifier, first you must select an appropriate algorithm.

+ How many classes or different outcomes do you want to predict?
+ What is the distribution of the data?
+ How much time can you allow for training?

Azure Machine Learning Studio provides multiple classification algorithms. The [One vs All](one-vs-all-multiclass.md) algorithm even lets you apply a binary classifier to a multi-class problem.

After you have chosen an algorithm and set the parameters using the modules in this section, you must train the model on labeled data. Classification is a supervised machine learning method and therefore always requires labeled training data.

After training is complete, you can [evaluate](machine-learning-evaluate.md) and tune the model. After you are satisfied with the model, use the trained model for [scoring](machine-learning-score.md) on new data.

##  <a name="modules"></a> List of modules  

This classification category includes the following modules:  

+ [Multiclass Decision Forest](multiclass-decision-forest.md): Creates a multiclass classification model using the decision forest algorithm 
+ [Multiclass Decision Jungle](multiclass-decision-jungle.md): Creates a multiclass classification model using the decision jungle algorithm 
+ [Multiclass Logistic Regression](multiclass-logistic-regression.md): Creates a multiclass logistic regression classification model 
+ [Multiclass Neural Network](multiclass-neural-network.md): Creates a multiclass classification model using a neural network algorithm 
+ [One-vs-All Multiclass](one-vs-all-multiclass.md): Creates a multiclass classification model from an ensemble of binary classification models 
+ [Two-Class Averaged Perceptron](two-class-averaged-perceptron.md): Creates an averaged perceptron binary classification model 
+ [Two-Class Bayes Point Machine](two-class-bayes-point-machine.md): Creates a Bayes point machine binary classification model 
+ [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md): Creates a binary classifier using a boosted decision tree algorithm 
+ [Two-Class Decision Forest](two-class-decision-forest.md): Creates a two-class classification model using the decision forest algorithm 
+ [Two-Class Decision Jungle](two-class-decision-jungle.md): Creates a two-class classification model using the decision jungle algorithm 
+ [Two-Class Locally Deep Support Vector Machine](two-class-locally-deep-support-vector-machine.md): Creates a binary classification model using the locally deep Support Vector Machine algorithm 
+ [Two-Class Logistic Regression](two-class-logistic-regression.md): Creates a two-class logistic regression model 
+ [Two-Class Neural Network](two-class-neural-network.md): Creates a binary classifier using a neural network algorithm 
+ [Two-Class Support Vector Machine](two-class-support-vector-machine.md): Creates a binary classification model using the Support Vector Machine algorithm

## Examples

For examples of classification in action, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/)

See these articles for help choosing an algorithm:  

-   [Machine learning algorithm cheat sheet for Azure ML](https://azure.microsoft.com/en-us/documentation/articles/machine-learning-algorithm-cheat-sheet/)  
  
     Provides a graphical decision chart to guide you through the selection process  
  
-   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
  
     Explains in greater detail the different types of machine learning algorithms and how they're used  

## See also
 [Regression](machine-learning-initialize-model-regression.md)   
 [Clustering](machine-learning-initialize-model-clustering.md)   
 [Text Analytics](text-analytics.md)   
 [Image classification](opencv-library-modules.md)   
 [A-Z Module List](a-z-module-list.md)