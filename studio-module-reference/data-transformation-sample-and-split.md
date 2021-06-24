---
title: "ML Studio (classic): Data Transformation: Sample and Split - Azure"
description: "Learn about the modules you can use to partition or sample data."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Transformation - Sample and Split

This article describes the modules in Machine Learning Studio (classic) that you can use to partition or sample data.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Splitting and sampling datasets are both important tasks in machine learning. For example, it's a common practice to divide data into training and testing sets to help you evaluate a model on a holdout dataset. Sampling is also increasingly important in the era of big data, to ensure that there's a fair distribution of classes in your training data. Sampling also helps ensure that you're not processing more data than is needed.

You can use Machine Learning Studio (classic) modules to customize the way you split or sample datasets:

- Filter training data based on an attribute in the data.
- Perform stratified sampling to divide the class variable equally among *n* number of groups.
- Divide source data into a training and testing data set by using a custom ratio.
- Apply regular expressions to the data to filter out invalid values.

## Choosing the right operation: Split or sampling

Machine Learning Studio (classic) provides two modules that encapsulate tasks. The modules sound similar, but they have different uses, and provide complementary functionality. It's likely that you'll use both modules in an experiment, to get the right amount and the right mix of data.

Next, we compare the **Split Data** module and the **Partition and Sample** module by seeing which tasks each module is commonly used for.

### Uses of the Split Data module
 
- **Divide data into two groups**. Use the [Split Data](split-data.md) module. The module produces exactly two splits of the data. You can specify the condition on which the data is split, and the proportion of the data to put into each subset. [Split Data](split-data.md) always saves the subset of data that doesn’t meet the conditions.
- **Allocate label values equally to datasets**. The option to stratify on a specified column is supported by both modules. However, if you want to create two datasets and are mostly interested in the label column, the **Split Data** module is a quick solution.

### Example of using the Split Data module

Suppose you imported a very large dataset from a CSV file. The dataset contains customer demographics. You want to create different models for customers in different countries, so you decide to split the data by using the value of the `Country-Region` column. Here are the steps you take to complete this task:

1. Add the [Split Data](split-data.md) module, and then specify an expression on the `Country-Region` field. The remainder of the data is available on the secondary output. 
2. Add another instance of the [Split Data](split-data.md) module.
3. Repeat steps 1 and 2. Specify a different country in the expression for each iteration.

The **Split Data** module supports both *regular expressions*, for text data, and *relative expressions*, for numeric data.

The **Split Data** module also provides sophisticated functionality that you can use to divide specialized datasets. Use the functionality to create recommendation models, and to generate predictions.

### Uses of the Partition and Sample module
 
- **Sampling**. Always use the [Partition and Sample](partition-and-sample.md) module. The module provides multiple customizable sampling methods, including several options for stratified sampling.
- **Assign cases to multiple groups**. Use the **Assign to Fold** or **Pick Fold** options in the [Partition and Sample](partition-and-sample.md) module.
- **Return only a subset of the data**. Use the [Partition and Sample](partition-and-sample.md) module. The module gives you the specified subset on the primary output. The remaining data is available on a secondary output.
- **Get only the top 2,000 rows of a dataset**. Use the [Partition and Sample](partition-and-sample.md) module. Select the **Head** option. This is particularly handy when you are testing a new experiment and want to run short trials of a workflow.

### Example of using the Partition and Sample module

The [Partition and Sample](partition-and-sample.md) module can generate multiple partitions of the data, not just two. At the same time, it can perform various sampling operations.

For example, suppose you need to get just 10 percent of your data, while ensuring that the distribution of the target attribute is the same as in the source data. Here are the steps you take to complete this task:

1. Add the [Partition and Sample](partition-and-sample.md) module.
2. Choose the **Sampling** mode, and then specify **10%**.
3. Select the stratified sampling option, and then pick the column that contains the target attribute.

If you don't need to keep all the data, use the [Partition and Sample](partition-and-sample.md) module. The remaining data is still present in the workspace, but it doesn't need to be processed further as part of the experiment.

## Related tasks

- Increase the number of rare cases in a sample, or rebalance the cases for a target value: Use the [SMOTE](smote.md) module.
- Perform dimensionality reduction by finding the combination of features that best represents the data space: Use the [Principal Component Analysis](principal-component-analysis.md) module.
- Create compact features based on an analysis of features and counts: Use the [Learning with Counts](data-transformation-learning-with-counts.md) module.
- Create a view or projection by using only the specified columns; remove or hide columns in a dataset: Use the [Select Columns in Dataset](select-columns-in-dataset.md) and [Apply SQL Transformation](apply-sql-transformation.md) modules.
- Apply more complex data filters, groupings, or transformations: Use the [Execute R Script](execute-r-script.md) and [Apply SQL Transformation](apply-sql-transformation.md) modules.

## List of modules

This category includes the following modules:

- [Partition and Sample](partition-and-sample.md): Creates multiple partitions of a dataset based on sampling.
- [Split Data](split-data.md): Partitions the rows of a dataset into two distinct sets.

## See also

- [Data Transformation](data-transformation.md)
- [A-Z module list](a-z-module-list.md)
