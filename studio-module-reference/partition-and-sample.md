---
title: "ML Studio (classic): Partition and Sample - Azure"
description: Learn how to use the Partition and Sample module to perform sampling on a dataset or to create partitions from your dataset.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Partition and Sample

*Creates multiple partitions of a dataset based on sampling*

Category: [Data Transformation / Sample and Split](data-transformation-sample-and-split.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Partition and Sample** module in Machine Learning Studio (classic), to perform sampling on a dataset or to create partitions from your dataset.

Sampling is an important tool in machine learning because it lets you reduce the size of a dataset while maintaining the same ratio of values. This module supports several related tasks that are important in  machine learning: 

- Dividing your data into multiple subsections of the same size. 

    You might use the partitions for cross-validation, or to assign cases to random groups.

- Separating data into groups and then working with data from a specific group. 

    After randomly assigning cases to different groups, you might need to modify the features that are associated with only one group.

- Sampling. 

    You can extract a percentage of the data, apply random sampling, or choose a column to use for balancing the dataset and perform stratified sampling on its values.

- Creating a smaller dataset for testing. 

    If you have a lot of data, you might want to use only the first *n* rows while setting up the experiment, and then switch to using the full dataset when you build your model. You can also use sampling to create s smaller dataset for use in development.

## How to configure Partition and Sample

This module supports multiple methods for dividing your data into partitions or for sampling. Choose the method first, and then set additional options required by the method.

- Get the top number of rows

### Get TOP N rows from a dataset

Use this mode to get only the first *n* rows. This option is useful if you want to test an experiment on a small number of rows, and don't need the data to be balanced or sampled in any way.

1. Add the **Partition and Sample** module to your experiment in Studio (classic), and connect the dataset.  

2. **Partition or sample mode**: Set this option to **Head**.

3. **Number of rows to select**: Type the number of rows to return.

    The number of rows you specify must be a non-negative integer. If the number of selected rows is larger than the number of rows in the dataset, the entire dataset is returned.

4. Run the experiment.

The module outputs a single dataset containing only the specified number of rows. The rows are always read from the top of the dataset.

### Create a sample of data

This option supports simple random sampling or stratified random sampling. This is useful if you want to create a smaller representative sample dataset for testing.

1. Add the **Partition and Sample** module to your experiment in Studio (classic), and connect the dataset.

2. **Partition or sample mode**: Set this to  **Sampling**.

3. **Rate of sampling**: Type a value between 0 and 1. this value specifies the percentage of rows from the source dataset that should be included in the output dataset.

    For example, if you want only half of the original dataset, type `0.5` to indicate that the sampling rate should be 50%.

    The rows of the input dataset are shuffled and selectively put into the output dataset, according to the specified ratio.

4. **Random seed for sampling**: Optionally, type an integer to use as a seed value.

    This option is important if you want the rows to be divided the same way every time. The default value is 0, meaning that a starting seed is generated based on the system clock. This can lead to slightly different results each time you run the experiment.

5. **Stratified split for sampling**: Select this option if it is important that the rows in the dataset should be divided evenly by some key column before sampling.

    For **Stratification key column for sampling**, select a single *strata column* to use when dividing the dataset. The rows in the dataset are then divided as follows:

    1. All input rows are grouped (stratified) by the values in the specified strata column.

    2. Rows are shuffled within each group.

    3. Each group is selectively added to the output dataset to meet the specified ratio.

     For more information about stratified sampling, see the [Technical notes](#bkmk_StratifiedSampling) section.

6. Run the experiment.

    With this option, the module outputs a single dataset that contains a representative sampling of the data.

    The remaining, unsampled portion of the dataset is not output. However, you can create join on the datasets, using the [Apply SQL Transformation](apply-sql-transformation.md) module, to determine which rows were unused.

### Split data into partitions

Use this option when you want to divide the dataset into subsets of the data. This option is also useful when you want to create a custom number of folds for cross-validation, or to split rows into several groups.

1. Add the **Partition and Sample** module to your experiment in Studio (classic), and connect the dataset.

2. For **Partition or sample mode**, select **Assign to Folds**.

3. **Use replacement in the partitioning**: Select this option if you want the sampled row to be put back into the pool of rows for potential reuse. As a result, the same row might be assigned to several folds.

    If you do not use replacement (the default option), the sampled row is not put back into the pool of rows for potential reuse. As a result, each row can be assigned to only one fold.

4. **Randomized split**:  Select this option if you want rows to be randomly assigned to folds.

    If you do not select this option, rows are assigned to folds using the round-robin method.

5. **Random seed**: Optionally, type an integer to use as the seed value. This option is important if you want the rows to be divided the same way every time. Otherwise, the default value of 0 means that a random starting seed will be used.

6. **Specify the partitioner method**: Indicate how you want data to be apportioned to each partition, using these options:

    - **Partition evenly**: Use this option to place an equal number of rows in each partition. To specify the number of output partitions, type a whole number in the **Specify number of folds to split evenly into** text box.

    - **Partition with customized proportions**: Use this option to specify the size of each partition as a comma-separated list.

        For example, if you want to create three partitions, with the first partition containing 50% of the data, and the remaining two partitions each containing 25% of the data, click the **List of proportions separated by comma** text box, and type these numbers: `.5, .25, .25`

        The sum of all partition sizes must add up to exactly 1.

        - If you enter numbers that add up to **less than 1**, an extra partition is created to hold the remaining rows. For example, if you type the values .2 and .3, a third partition is created that holds the remaining 50 percent of all rows.

        - If you enter numbers that add up to **more than 1**, an error is raised when you run the experiment.

7. **Stratified split**: Select this option if you want the rows to be stratified when split, and then choose the _strata column_.

    For more information about stratified sampling, see the [Technical notes](#bkmk_StratifiedSampling) section.

8. Run the experiment.

    With this option, the module outputs multiple datasets, partitioned using the rules you specified.

### Use data from a predefined partition  

This option is used when you have divided a dataset into multiple partitions and now want to load each partition in turn for further analysis or processing.

1. Add the **Partition and Sample** module to the experiment in Studio (classic).

2. Connect it to the output of a previous instance of **Partition and Sample**. That instance must have used the **Assign to Folds** option to generate some number of partitions.

3. **Partition or sample mode**: Select **Pick Fold**.

4. **Specify which fold to be sampled from**: Select a partition to use by typing its index. Partition indices are 1-based. For example, if you divided the dataset into three parts, the partitions would have the indices 1, 2, and 3.

    If you type an invalid index value, a design-time error is raised: "Error 0018: Dataset contains invalid data."

    In addition to grouping the dataset by folds, you can separate the dataset into two groups: a target fold, and everything else. To do this, type the index of a single fold, and then select the option, **Pick complement of the selected fold**, to get everything but the data in the specified fold.

5. If you are working with multiple partitions, you must add additional instances of the **Partition and Sample** module to handle each partition.

    For example, let's say previously partitioned patients into five folds using age. To work with each individual fold, you need five copies of the **Partition and Sample** module, and in each, you select a different fold.

    > [!TIP]
    > The sample experiment, [Split Partition and Sample](https://go.microsoft.com/fwlink/?LinkId=525948), demonstrates this technique.

5. Run the experiment.

    With this option, the module outputs a single dataset containing only the rows assigned to that fold.

> [!NOTE]
>  You cannot view the fold designations directly; they are present only in the metadata.

## Examples

For examples of how this module is used, see the [Azure AI Gallery](https://gallery.azure.ai/):

- [Cross Validation for Binary Classification](https://go.microsoft.com/fwlink/?LinkId=525734): A 20% sampling rate is applied to create a smaller randomly sampled dataset. The original census dataset had over 30,000 rows; the sampled dataset has around 6500.

- [Cross Validation for Regression](https://go.microsoft.com/fwlink/?LinkId=525735): The data is randomly and evenly assigned to five folds, with no stratification, and the results are used for cross-validation.

- [Split Partition and Sample](https://go.microsoft.com/fwlink/?LinkId=525948): Demonstrates multiple ways to use partitioning and sampling. First, the **Assign to Folds** option is used to assign rows in the dataset to one of three evenly sized groups. Then, three more instances of [Partition and Sample](partition-and-sample.md) are added by using the **Pick Fold** mode to apply operations to subsets of the data

    - In the first fold (index of 1), rows are split randomly.
    - In the second fold (index of 2), rows are split by education.
    - In the third fold (index of 3), rows are split by age.

## Technical notes

- The stratification column must be categorical with discrete values. If the column is not already categorical and you get an error, use [Edit Metadata](edit-metadata.md) to change the column properties.

- The strata column you specify cannot contain continuous data: that is, numerical data with floating point values in each cell. Otherwise, the module cannot process the data and returns an error.

    The reason is that any column used for  stratification must have a finite set of possible values. If the specified strata column contains any floating point values, and the column is not of the type categorical, it potentially contains an infinite number of values.

- If the strata column contains Boolean values and you want them to be interpreted as categorical, you must use the [Edit Metadata](edit-metadata.md) module to change the metadata label.

- If your strata column contains string or numerical data with too many unique values, the column is not a good candidate for stratified sampling.

###  <a name="bkmk_StratifiedSampling"></a> More about stratified sampling

**Stratified sampling** ensures that subsets of the data have a representative sampling of the selected strata column. This technique is useful, for example, when you want to ensure that your training data contains the same distribution of age values that the test data has or vice versa. Or you might want to stratify a gender column in a health-care study to ensure that males and females are distributed evenly when the data is partitioned. Stratification ensures that the ratios of the selected values are preserved.

You specify values on which to separate the data by selecting a single column to serve as the **strata column**.

This module requires that the strata column is a categorical column. If you want to use a column of integer values for the strata, it is a best practice to assign a categorical type to this column. You can do this through the schema of the data before you add it to Machine Learning Studio (classic), or you can update the column’s metadata by using [Edit Metadata](edit-metadata.md).

Columns with continuous data (that is, numerical data with floating point values in each cell) cannot be used as strata columns. If you get an error, you can use [Group Data into Bins](group-data-into-bins.md) to bucket the values into discrete ranges, and then use [Edit Metadata](edit-metadata.md) to guarantee that the column will be treated as categorical.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset to be split|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Partition or sample mode|List|Sampling methods|Sampling|Select the partition or sampling mode|  
|Use replacement in the partitioning|Any|Boolean|False|Indicate if the folds should be disjoint (default - no replacement) or overlapping (true - use replacement)|  
|Randomized split|Any|Boolean|True|Indicate if the split is random|  
|Random seed|Any|Integer|0|Specify a seed for the random number generator|  
|Specify the partitioner method|List|Partition methods|Partition evenly|Select **Partition Evenly** to partition into folds of equal size, or **Partition with customized proportions** to partition into folds of customized size|  
|Specify number of folds to split evenly into|>=1|Integer|5|Select a number of partitions to split into|  
|Stratified split|List|True/False type|False|Indicate if the split is stratified|  
|Stratification key column|Any|ColumnSelection||Contains the stratification key|  
|List of proportions separated by comma|Any|String||List proportions,  separated by commas|  
|Stratified split for customized fold assignment|Any|True/False type|False|Indicate if the split is stratified for customized fold assignments|  
|Stratification key column for customized fold assignment|Any|ColumnSelection||Contains the stratification key for customized fold assignments|  
|Specify which fold to be sampled from|>=1|Integer|1|Contains index of the fold to be sampled|  
|Pick complement of the selected fold|Any|Boolean|False|Select the complement of the specified fold|  
|Rate of sampling|Any|Float|0.01|Choose a sampling rate|  
|Random seed for sampling|Any|Integer|0|Specify a seed for the random number generator for sampling|  
|Stratified split for sampling|Any|True/False|False|Indicate if the split is stratified for sampling|  
|Stratification key column for sampling|Any|ColumnSelection||Contains stratification key for sampling|  
|Number of rows to select|>=0|Integer|10|Select a maximum number of records that will be allowed to pass through to the next module|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|oDataset|[Data Table](data-table.md)|Dataset resulting from the split|  

## See also

 [Sample and Split](data-transformation-sample-and-split.md)   
 [Split Data](split-data.md)   
 [Edit Metadata](edit-metadata.md)   
 [Group Data into Bins](group-data-into-bins.md)   
