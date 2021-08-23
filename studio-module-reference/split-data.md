---
title: "ML Studio (classic): Split Data - Azure"
description: Learn how to use the Split Data module to divide a dataset into two distinct sets.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Split Data

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Partitions the rows of a dataset into two distinct sets*

Category: [Data Transformation / Sample and Split](data-transformation-sample-and-split.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This topic describes how to use the [Split Data](split-data.md) module in Machine Learning Studio (classic), to divide a dataset into two distinct sets.

This module is particularly useful when you need to separate data into training and testing sets. You can customize the way that data is divided as well. Some options support randomization of data; others are tailored for a certain data type or model type.

## How to configure Split Data

> [!TIP]
> Before choosing the splitting mode, read all options to determine the type of split you need.
> If you change the splitting mode, all other options could be reset.

1. Add the **Split Data** module to your experiment in studio. You can find this module under **Data Transformation**, in the **Sample and Split** category.

2. **Splitting mode**: Choose one of the following modes, depending on the type of data you have, and how you want to divide it. Each splitting mode has different options. Click the following topics for detailed instructions and examples. 

    - [Split Rows](split-data-using-split-rows.md): Use this option if you just want to divide the data into two parts. You can specify the percentage of data to put in each split, but by default, the data is divided 50-50.

        You can also randomize the selection of rows in each group, and use stratified sampling. In stratified sampling, you must select a single column of data for which you want values to be apportioned equally among the two result datasets.  

    - [Recommender Split](split-data-using-recommender-split.md):  Always choose this option if you are preparing data for use in a recommender system. It helps you divide data sets into training and testing groups while ensuring that important values such as user-item pairs or ratings are evenly divided among the groups.

    - [Regular Expression Split](split-data-using-regular-expression.md):  Choose this option when you want to divide your dataset by testing a single column for a value.

        For example, if you are analyzing sentiment, you could check for the presence of a particular product name in a text field, and then divide the dataset into rows with the target product name, and those without.

    - [Relative Expression Split](split-data-using-relative-expression.md):  Use this option whenever you want to apply a condition to a number column. The number could be a date/time field, a column containing age or dollar amounts, or even a percentage. For example, you might want to divide your data set depending on the cost of the items, group people by age ranges, or separate data by a calendar date.

## Requirements

- **Split Data** can create a maximum of two datasets sets at a time, and those sets must be exclusive. 

    Therefore, if you have a complex split with multiple conditions and outputs, you might need to chain together multiple [Split Data](split-data.md) modules.

    Alternatively, you can use a CASE statement and the [Apply SQL Transformation](apply-sql-transformation.md) module.

- This module doesn't delete data or remove it from the dataset; it just divides the data as specified among the first and second outputs of the module.

- Splitting data for a recommender system entails some additional requirements. In general, the dataset can only consist of user-item pairs or user-item-rating triples. Therefore, the [Split Data](split-data.md) module cannot work on datasets that have more than three columns, to avoid confusion with feature-type data. If your dataset contains too many columns, you might get this error:

    Error 0022: Number of selected columns in input dataset does not equal to x  

    As a workaround, you can use [Select Columns in Dataset](select-columns-in-dataset.md) to remove some columns, and then add the columns later using [Add Columns](add-columns.md). Alternatively, if your dataset has many features that you want to use in the model, divide the dataset using a different option, and train the model using [Train Model](train-model.md) rather than [Train Matchbox Recommender](train-matchbox-recommender.md). 

## Examples  

For examples of how the [Split Data](split-data.md) module is used, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Cross Validation for Binary Classification: Adult Dataset](https://go.microsoft.com/fwlink/?LinkId=525734): A 20% sampling rate is applied to create a smaller randomly sampled dataset. (The original census dataset had over 30,000 rows; the training dataset has around 6500). The dataset is cleaned for missing values and then passed to five different models for training and cross-validation.

## Technical notes

The following requirements apply to all uses of [Split Data](split-data.md):  

- The input dataset must contains at least two rows, or an error is raised.
- If you use the option to specify the desired number of rows, the specified number must be a positive integer, and the number must be less than the total number of rows in the dataset.
- If you specify a number as a percentage, or if you use a string that contains the "%" character, the value is interpreted as a percentage. All percentage values must be within the range (0, 100), not including the values 0 and 100. 
- If you specify a number or percentage that is a floating point number less than one, and you do not use the percent symbol (%), the number is interpreted as a proportional value.
- If you use the option for a stratified split, the output datasets can be further divided by subgroups, by selecting a strata column.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset to split|  

## Module parameters

|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Splitting mode|Split mode|Split Rows, Recommender Split, Regular Expression, or Relative Expression|Required|Split Rows|Choose the method for splitting the dataset|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset1|[Data Table](data-table.md)|Dataset that contains selected rows|  
|Results dataset2|[Data Table](data-table.md)|Dataset that contains all other rows|  

## See also

 [Sample and Split](data-transformation-sample-and-split.md)   
 [Partition and Sample](partition-and-sample.md)   
 [A-Z Module List](a-z-module-list.md)
