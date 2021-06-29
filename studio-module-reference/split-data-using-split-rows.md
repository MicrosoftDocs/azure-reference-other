---
title: "ML Studio (classic): Split Data using Split Rows - Azure"
description: Learn how to divide into training and testing datasets using a numerical expression with the the Split Rows option in the Split Data module.
ms.date: 03/05/2020
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Split Data using Split Rows

This article describes how to use the **Split Rows** option in the [Split Data](split-data.md) module of Machine Learning Studio (classic). This option is particularly useful when you need to divide datasets used for training and testing, either randomly or by some criteria.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The  **Split Rows** option supports both random and stratified splits. For example, you can specify a 70-30 split, or a 10-90 split with your target variable equally represented in both datasets.

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md).

## Related tasks

Other options in the **Split Data** module support different ways to divide the data:

+ [Split data using regular expressions](split-data-using-regular-expression.md): Apply a regular expression to  a single text column, and divide the dataset based on the results.

+ [Split data using relative expressions](split-data-using-relative-expression.md): Apply an expression to a numeric column, and divide the dataset based on the results

+ [Split recommender datasets](split-data-using-recommender-split.md): Divide datasets that are used in recommendation models. The dataset should have three columns: items, users, and ratings.

## Divide a dataset into two groups

1. Add the [Split Data](split-data.md) module to your experiment in Studio (classic), and connect the dataset you want to split.
  
2. For **Splitting mode**, choose **Split rows**.

3. **Fraction of rows in the first output dataset**. Use this option to determine how many rows go into the first (left-hand) output. All other rows will go to the second (right-hand) output.

    The ratio represents the percentage of rows sent to the first output dataset, so you must type a decimal number between 0 and 1.

     For example, if you type 0.75 as the value, the dataset would be split by using a 75:25 ratio, with 75% of the rows sent to the first output dataset, and 25% sent to the second output dataset.
  
4. Select the **Randomized split** option if you want to randomize selection of data into the two groups. This is the preferred option when creating training and test datasets.

5. **Random Seed**: Type a non-negative integer value to initialize the pseudorandom sequence of instances to be used. This default seed is used in all modules that generate random numbers.

     Specifying a seed makes the results generally reproducible. If you need to repeat the results of a split operation, you should specify a seed for the random number generator. Otherwise the random seed is set by default to 0, which means the initial seed value is obtained from the system clock. As a result, the distribution of data might be slightly different each time you perform a split.

6. **Stratified split**: Set this option to **True** to ensure that the two output datasets contain a representative sample of the values in the *strata column* or *stratification key column*.

    With stratified sampling, the data is divided such that each output dataset gets roughly the same percentage of each target value. For example, you might want to ensure that your training and testing sets are roughly balanced with regard to the outcome, or with regard to some other column such as gender.

7. Run the experiment, or right-click the module and select **Run selected**.

## Examples

The following examples demonstrate how to perform simple splits using **Split Rows** mode.

### Split into two equal parts

Add the [Split Data](split-data.md) module after the dataset without no other changes. By default, the module splits the dataset in two equal parts. For data with an odd number of rows, the second output gets the remainder.

### Split into thirds

Assume that you want to split a dataset into two parts, with a third of the data used for training and the remainder for testing or additional splits.

To do this, add a [Split Data](split-data.md) module, and set the **Fraction of rows in the first output** to 0.33. The second output contains the remaining two-thirds.

To divide the second output into equal parts, add another instance of the **Split Data** module, and this time use the default for a 50-50 split.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

+ This module requires that the dataset contain at least two rows; otherwise, an error is raised.

+ If you use the option to specify the desired number of rows, the specified number must be a positive integer, and the number must be less than the total number of rows in the dataset.

+ All percentage values must be within the range 0 and 1.

+ If you specify a number or percentage as a floating point number less than one, and you do not use the percent symbol (%), the number is interpreted as a proportional value.

### Additional requirements for stratified sampling

+ The strata column can contain only nominal or categorical data. If the column contains continuous numeric data, an error message is raised.

+ A column with too many unique values is not a good candidate for stratification. You might try collapsing some categories or grouping values beforehand.

## See also

 [Sample and Split](data-transformation-sample-and-split.md)
 [Partition and Sample](partition-and-sample.md)
