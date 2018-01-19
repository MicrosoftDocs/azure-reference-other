---
title: "Data Transformation - Sample and Split | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 73a66797-d6e4-48a1-98c1-2d764ec5d2cd
caps.latest.revision: 19
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Data Transformation - Sample and Split

This article describes the modules in Azure Machine Learning Studio that you can use to partition or sample data.

Splitting and sampling datasets are both important tasks in machine learning. For example, it is a common practice to divide data into training and testing sets, so that you can evaluate a model on a holdout data set. Sampling is also increasingly important in the era of big data, to ensure that there is a fair distribution of classes in your training data, and that you are not processing more data than is needed.

You can use these modules to customize the way you split or sample datasets:  
  
- Filter training data based on some attribute in the data   
- Perform stratified sampling to divide the class variable equally among *n* number of groups
- Divide source data into a training and testing data set with a custom ratio
- Apply regular expressions to the data to filter out invalid values  
  
## Choosing the right operation - split or sampling?

Azure Machine Learning Studio provides two modules that encapulate tasks that sound similar, but actually have very different uses, and provide complementary functionality. It's likely that you'll use both modules in an experiment, to get the right amount and the right mix of data.

Let's compare them by seeing which tasks each module is commonly used for:

### Uses of the Split Data module 
 
 + Divide data into two groups:   Use [Split Data](split-data.md) module. It produces exactly two splits of the data. You can specify the condition on which the data is split, and the proportion of the data to put into each subset. [Split Data](split-data.md) always saves the subset of data that doesn’t meet the conditions.  
 
+ Allocate label values equally to datasets. The option for stratifying on a specified column is supported by both modules. However, if you want to create two datasets and mostly care about the label column, the Split module is a quick solution. 

### Examples of operations with the Split Data module

Suppose you imported a very large dataset from a CSV file that contains customer demographics. You want to create different models for customers in different countries, so you decide to split the data by using the value of the column `Country-Region`. 

1. Add the  [Split Data](split-data.md) module, and specify an expression on the `Country-Region` field. 
2. The remainder of the data is available on the secondary output.  Add another instance of [Split Data](split-data.md) module.
3. Repeat, specifying a different country in the expression each time.  

The **Split Data** module supports both **regular expressions**, for text data, and **relative expressions**, for numeric data. 

The **Split Data** module also provides sophisticated features for dividing the specialized datasets used for creating recommendation models, and for generating predictions.

### Uses of the Partition and Sample module
 
 + Sampling: Always use [Partition and Sample](partition-and-sample.md). This module provides multiple, customizable sampling methods, including several options for stratified sampling.

+ Assign cases to multiple groups. Use the **Assign to Fold** or **Pick Fold** options of the [Partition and Sample](partition-and-sample.md) module.
  
-   Return only a subset of the data: Use [Partition and Sample](partition-and-sample.md) module. It gives you the specified subset on the primary output. The remaining data is available on a secondary output.  

-   Get only the top 2000 rows of a dataset. Use [Partition and Sample](partition-and-sample.md) and select the **Head** option. This is particularly handy when you are testing a new experiment and want to run short trials of a workflow.  

### Examples of operations with the Partition and Sample module 

The [Partition and Sample](partition-and-sample.md) module can generate multiple partitions of the data, not just two. At the same time, it can perform various sampling operations.  

For example, suppose you need to get just 10 percent of your data, while ensuring that the distribution of the target attribute is the same as in the source data. 

1. Add the [Partition and Sample](partition-and-sample.md) module.
2. Choose the **Sampling** mode, and specify 10%.
3. Select the stratified sampling option, and pick the column that contains the target attribute. 

Whenever you don't need to keep all the data, use [Partition and Sample](partition-and-sample.md).  The remaining data is still present in the workspace but doesn't need to be processed further as part of the experiment. 

## Related tasks and modules

+ [SMOTE](smote.md): Increase the number of rare cases in a sample, or rebalances the cases for some target value.  

+ [Principal Component Analysis](principal-component-analysis.md):  Perform dimensionality reduction by finding the combination of features that best represents the data space.

+ [Learning with Counts](data-transformation-learning-with-counts.md): Create compact features based on an analysis of features and counts.

+ [Select Columns in a dataset](select-columns-in-dataset.md) and [Apply SQL Transformation](apply-sql-transformation.md): Create a view or projection using only specified columns. Remove or hide columns in a dataset.

+ [Execute R Script](execute-r-script.md) and [Apply SQL Transformation](apply-sql-transformation.md): Apply more complex data filters, groupings, or transformations. 

##  <a name="modules"></a> List of modules

This category includes the following modules:  

|Module|Description|  
|------------|-----------------|  
|[Partition and Sample](partition-and-sample.md)|Creates multiple partitions of a dataset based on sampling|  
|[Split Data](split-data.md)|Partitions the rows of a dataset into two distinct sets|

## See also  
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)