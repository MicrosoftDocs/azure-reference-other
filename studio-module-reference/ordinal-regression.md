---
title: "ML Studio (classic): Ordinal Regression - Azure"
description: Learn how to use the Ordinal Regression module to create a regression model that can be used to predict ranked values. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Ordinal Regression

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates an ordinal regression model*

Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Ordinal Regression** module in Machine Learning Studio (classic), to create a regression model that can be used to predict ranked values. 

Some examples of ranked values:

+ Survey responses that capture user’s preferred brands on a 1 to 5 scale
+ The order of finishers in a race
+ URLs in ranked search results

## More about ordinal regression

Ordinal regression is used when the label or target column contains numbers, but the numbers represent a ranking or order rather than a numeric measurement.

Predicting ordinal numbers requires a different algorithm than predicting the values of numbers on a continuous scale, because the numbers assigned to represent rank order do not have intrinsic scale.

For example, to predict students’ test scores, you would use a standard regression model, because students’ test scores vary on a continuous scale and can be measured. However, to predict their class ranking, you must use an ordinal regression model.

For more information about the research behind this algorithm, see this paper (downloadable PDF): [https://papers.nips.cc/paper/3125-ordinal-regression-by-extended-binary-classification.pdf](https://papers.nips.cc/paper/3125-ordinal-regression-by-extended-binary-classification.pdf)

## How to configure Ordinal Regression

This module solves a ranking problem as a series of related classification problems. Therefore, the algorithm creates a series of extended training examples using a binary model for each rank, and trains against that extended set. This operation can be computationally expensive.

1. Add the **Ordinal Regression Model** module to your experiment in Studio (classic). You can find this module under **Machine Learning - Initialize**, in the **Regression** category.

2. Add a module that supports binary classification, and configure the model. There are several two-class modules in the [classification](machine-learning-initialize-model-classification.md) category.

3. Connect the binary classification model as an input to the **Ordinal Regression Model** module.

4. Additional parameters are not required on the **Ordinal Regression Model**; the algorithm has been pre-configured with the most effective parameters for solving a ranking problem.

5. Connect a training dataset and the [Train Model](train-model.md) module.

6. In the [Train Model](train-model.md) module, select the column that contains the rank values.

    The rank values must be numerical values, but they need not be integers or positive numbers, as long as they represent a sequence.

    For purposes of processing, the ranks are assumed to have the order 1 to K, where 1 is lowest rank, and K is the highest rank. However, the [Train Model](train-model.md) module can work even if the semantics of your scale are reversed.

    For example, if in your original survey, 1 was the highest score and 5 is the lowest, it does not affect the processing of the model.

6. Run the experiment.

### Results

After training is complete:

+ To make predictions, connect the trained model, along with new data, to the [Score Model](score-model.md) module.

+ To perform cross-validation against a labeled data set, connect the **untrained model** to [Cross-Validate Model](cross-validate-model.md).

## Examples

For examples of how ordinal regression is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai).

- [Predictive Maintenance - Step C](https://gallery.azure.ai/Experiment/68b4a27dc53d426e902025e77a393702?r=legacy): In this sample, **Ordinal Regression** is used to rank values output by a classification model, on the assumption that the value reflects the severity of the failure classification.

## Technical notes

The ordinal regression algorithm used in this learner is implemented by extended binary classification, as described by the paper titled *Ordinal Regression by Extended Binary Classification*, by Ling Li and Hsuan-Tien Lin, in NIPS 2006.

### Restrictions on input data

You can use any numeric column as the target of an ordinal regression model, but in practice you should use only data that represents some sort of order or ranking.

The intervals between ranks are assumed to be unknown and the size of the interval does not matter to the model; however, the model assumes that the sequence of ranks follows the natural ordering of numbers.

The model itself does not assign any meaning to a particular scale. In other words, you might create one model in which 1 is a good rank and 10 is the worst, and in another model assume that 10 is the desired rank and 1 is the worst.

### Ranking algorithm

The training set (X,Y) consists of input vectors x and labels y. The labels represents ranks ranging from 1 to *k* in sequence:  1,2, … , *K*.  The ranks are assumed to be ordered such that  1 is the lowest or the worst rank, and K is the best or highest rank.

The crux of the algorithm lies in modifying the given input features X and labels Y to use extended examples, and then using a binary classifier to solve the ordinal regression problem. The binary classifier is trained to give a yes/no answer to the question, “Is the rank greater than r?”

For example, for each case in the training set there are *K-1* extended examples, and the maximum observed rank is *K*. The extended features are formed by appending the i<sup>th</sup> row of a K-1 x K-1 identity matrix to the input features for all i. The labels are given +1 for the first r-1 rows if its rank is r and -1 to the rest.

### Sample calculations  

To illustrate how it works, let x<sup>1</sup> be the training feature whose rank is 3, where the maximum observed rank is 5. The extended examples corresponding to this feature are as follows:

|Case|Test|Resulting label|  
|----------|----------|---------------------|  
|X11000|Is rank greater than 1?|Yes; therefore +1|  
|X10100|Is rank greater than 2?|Yes; therefore +1|  
|X10010|Is rank greater than 3?|No; therefore no additional feature|  
|X10001|Is rank greater than 4?|No; therefore no additional feature|  

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained binary classification model|[ILearner interface](ilearner-interface.md)|An untrained binary classification model|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained ordinal regression model|  

## See also

 [Regression](machine-learning-initialize-model-regression.md)   
