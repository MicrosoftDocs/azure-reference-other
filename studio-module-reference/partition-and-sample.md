---
title: "Partition and Sample | Microsoft Docs"
ms.custom: ""
ms.date: 06/21/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a8726e34-1b3e-4515-b59a-3e4a475654b8
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Partition and Sample
*Creates multiple partitions of a dataset based on sampling*  
  
 Category: [Data Transformation / Sample and Split](data-transformation-sample-and-split.md)  
  
## Module Overview  
 You can use the **Partition and Sample** module to perform sampling on a dataset or to create partitions from your dataset. Sampling is an important tool in machine learning because it lets you reduce the size of a dataset while maintaining the same ratio of values.  
  
 This module supports several important machine learning scenarios:  
  
-   **Dividing your data into multiple subsections of the same size.**  
  
     The goal might be to use the partitions for cross-validation or to assign cases to random groups.  
  
-   **Separating data into groups and then working with data from a specific group.**  
  
     You might need to randomly assigned cases to different groups, and then modify the features that are associated with only one group. You do this in the **Partition and Sample** module by splitting data into folds and then choosing a fold on which to perform further operations.  
  
-   **Sampling.**  
  
     You can extract a percentage of the data, apply random sampling, or choose a column to use for balancing the dataset and perform stratified sampling on its values.  
  
-   **Creating a smaller dataset for testing.**  
  
     If you a have a lot of data, you might want to use only the first *n* rows while setting up the experiment, and then switch to using the full dataset when you build your model. You can also use sampling to create s smaller dataset for use in development.  
  
## How to Configure Partition and Sample  
  
#### To get some number of first rows from a dataset  
  
1.  Add the **Partition and Sample** module to your experiment, and connect the dataset to the input.  
  
2.  For **Partition or sample mode**, select **Head**.  
  
     Use this mode to get only the first *n* rows. This option is useful if you want to test an experiment on a small number of rows, and don't need the data to be balanced or sampled in any way.  
  
3.  For **Number of rows to select**, type the number of rows you want to return.  
  
     The number of rows you specify must be a non-negative integer. If the number of selected rows is larger than the number of rows in the dataset then the entire dataset is returned.  
  
4.  Run the experiment.  
  
5.  The module outputs a single dataset containing only the specified number of rows. The rows are always read from the top of the dataset.  
  
#### To create a sample of data  
  
1.  Add the **Partition and Sample** module to your experiment, and connect the dataset to the input.  
  
2.  For **Partition or sample mode**, select **Sampling**.  
  
     With this option, you can perform simple random sampling or stratified random sampling. This is useful if you want to create a smaller representative sample dataset for testing.  
  
3.  For **Rate of sampling**, type a value between 0 and 1 that indicates the percentage of rows from the source dataset that should be included in the output dataset.  
  
     For example, if you wanted only half of the original sample, you could type `0.5` to indicate that the sampling rate should be 50%.  
  
     The rows of the input dataset are shuffled and selectively put into the output dataset, according to the specified ratio.  
  
4.  For **Random seed for sampling**, optionally type an integer to use as a seed value.  
  
     This option is important if you want the rows to be divided the same way every time. Otherwise, the default value of 0 means that a random starting seed will be used.  
  
5.  Select the **Stratified split for sampling** option if it is important that the rows in the dataset should be divided evenly by some key column before sampling.  
  
     If TRUE, for **Stratification key column for sampling**, select a single *strata column* to use when dividing the dataset.  
  
     If you do so, the rows in the dataset will be divided as follows:  
  
    1.  All the input rows are grouped (stratified) by the values in the specified strata column.  
  
    2.  Rows are shuffled within each group.  
  
    3.  Each group is selectively added to the output dataset to meet the specified ratio.  
  
     For more information about stratified sampling, see the [Technical Notes](#bkmk_StratifiedSampling) section.  
  
6.  Run the experiment.  
  
7.  The module outputs a single dataset that contains a representative sampling of the data.  
  
#### To split data into partitions  
  
1.  Add the **Partition and Sample** module to your experiment, and connect the dataset to the input.  
  
2.  For **Partition or sample mode**, select **Assign to Folds**.  
  
     Use this option when you want to divide the dataset into subsets of the data. Also use it if you want to create a custom number of folds for cross-validation or if you want to split rows into several groups.  
  
3.  Select the **Use replacement in the partitioning** option if you want the sampled row to be put back into the pool of rows for potential reuse. As a result, the same row might be assigned to several folds.  
  
     If you do not use replacement (the default option), the sampled row is not put back into the pool of rows for potential reuse. As a result, each row will be assigned to exactly one fold.  
  
4.  Select the option, **Randomized split**, if you want rows to be randomly chosen.  
  
     If you do not select this option, rows are assigned to folds using the round-robin method.  
  
5.  For **Random seed**, optionally type an integer to use as the seed value.  
  
     This option is important if you want the rows to be divided the same way every time. Otherwise, the default value of 0 means that a random starting seed will be used.  
  
6.  For **Specify the partitioner method**, indicate how you want data to be apportioned to the partitions:  
  
    -   **Partition evenly**  
  
         If you select this option, an equal number of rows are assigned to each partition.  
  
         Type the number of output partitions you want in the **Specify number of folds to split evenly into** text box.  
  
    -   **Partition with customized proportions**  
  
         If you use this option, provide a comma-separated list that indicates the size of each partition.  
  
         For example, if you want to create three partitions, with the first partition containing 50% of the data, and the remaining two partitions each containing 25% of the data, click the **List of proportions separated by comma** text box, and type these numbers:  
  
         `.5, .25, .25`  
  
        > [!NOTE]
        >  The sum of all partition sizes must add up to exactly 1.  
        >   
        >  -   If you enter numbers that add up to **less than 1**, an extra partition will be created to hold the remaining rows. For example, if you type the values .2 and .3, a third partition will be created that holds the remaining 50 percent of all rows.  
        > -   If you enter numbers that add up to **more than 1**, an error will be raised when you run the experiment.  
  
7.  Select the option, **Stratified split**, if you want the rows to be stratified when split. If you choose this option, you must select a strata column.  
  
     For more information about stratified sampling, see the [Technical Notes](#bkmk_StratifiedSampling) section.  
  
8.  Run the experiment.  
  
9. The module outputs multiple datasets, partitioned using the rules you specified.  
  
#### To use data from a predefined partition  
  
1.  Add the **Partition and Sample** module to the experiment, and connect it to the output of another instance of **Partition and Sample**.  
  
     The previous **Partition and Sample** module must have used the **Assign to Folds** option to generate some n number of partitions.  
  
2.  For **Partition or sample mode**, select **Pick Fold**.  
  
3.  In **Specify which fold to be sampled from**, select a partition to use by typing its index. Indexes are 1-based. For example, if you divided the dataset into three parts, the available indexes would be 1, 2, and 3.  
  
     You can also type the index of a certain fold, and then select the option, **Pick complement of the selected fold**, to get everything but the data in the specified fold.  
  
     If you type an invalid index value, you will get the error: Error 0018: Dataset contains invalid data.  
  
4.  If the previous instance of the **Partition and Sample** module created multiple partitions, you can connect additional copies of the **Partition and Sample** module to handle each partition.  
  
     For example, if you partitioned patients into five folds using age, you could add 5 copies of the **Partition and Sample** module and pick a different fold in each.  
  
    > [!TIP]
    >  The sample experiment, [Split Partition and Sample](http://go.microsoft.com/fwlink/?LinkId=525948), demonstrates this technique.  
  
5.  Run the experiment.  
  
6.  The module outputs a single dataset containing only the rows assigned to that fold.  
  
    > [!NOTE]
    >  You cannot view the fold designations directly; they are present only in the metadata.  
  
## Examples  
 You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   In the sample, [Cross Validation for Binary Classification](http://go.microsoft.com/fwlink/?LinkId=525734), a 20% sampling rate is applied to create a smaller randomly sampled dataset. (The original census dataset had over 30,000 rows; the training dataset has around 6500.)  
  
-   In the sample, [Cross Validation for Regression](http://go.microsoft.com/fwlink/?LinkId=525735), the data is randomly and evenly assigned to five folds (with no stratification), and the results are used for cross-validation.  
  
-   The sample, [Split Partition and Sample](http://go.microsoft.com/fwlink/?LinkId=525948), demonstrates multiple ways to use partitioning and sampling.  
  
     First, the **Assign to Folds** option is used to assign rows in the dataset to one of three evenly sized groups.  
  
     Then, three more instances of [Partition and Sample](partition-and-sample.md) are added by using the **Pick Fold** mode to apply operations to subsets of the data:  
  
    -   For the first fold (index of 1), rows are split randomly.  
  
    -   For the second fold (index of 2), rows are split by education.  
  
    -   For the third fold (index of 3), rows are split by age.  
  
## Technical Notes  
  
-   The stratification column must be categorical with discrete values. If the column is not already categorical and you get an error, use [Edit Metadata](edit-metadata.md) to change the column properties.  
  
-   The strata column you specify cannot contain continuous data: that is, numerical data with floating point values in each cell. Otherwise, the module will not complete its processing and will return an error.  
  
     The reason is that any column used for  stratification must have a finite set of possible values. If the specified strata column contains any floating point values, and the column is not of the type categorical, it potentially contains an infinite number of values.  
  
-   If the strata column contains Boolean values and you want them to be interpreted as categorical, you must use the [Edit Metadata](edit-metadata.md) module to change the metadata label.  
  
-   If your strata column contains string or numerical data with too many unique values, the column is not a good candidate for stratified sampling.  
  
###  <a name="bkmk_StratifiedSampling"></a> More about Stratified Sampling  
 **What is stratified sampling and why would I use it?**  
  
 Stratified sampling ensures that subsets of the data have a representative sampling of the selected strata column.  
  
 This technique is useful, for example, when you want to ensure that your training data contains the same distribution of age values that the test data has or vice versa. Or you might want to stratify a gender column in a health-care study to ensure that males and females are distributed evenly when the data is partitioned. Stratification ensures that the ratios of the selected values are preserved.  
  
 **What is a strata column? Which column should I use?**  
  
 You specify values on which to separate the data by selecting a single column to serve as the *strata column*.  
  
 This module requires that the strata column is a categorical column. If you want to use a column of integer values for the strata, it is a best practice to assign a categorical type to this column. You can do this through the schema of the data before you add it to Azure Machine Learning Studio, or you can update the column’s metadata by using [Edit Metadata](edit-metadata.md).  
  
 Columns with continuous data (that is, numerical data with floating point values in each cell) cannot be used as strata columns. If you get an error, you can use [Group Data into Bins](group-data-into-bins.md) to bucket the values into discrete ranges, and then use [Edit Metadata](edit-metadata.md) to guarantee that the column will be treated as categorical.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset to be split|  
  
##  <a name="parameters"></a> Module Parameters  
  
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
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|oDataset|[Data Table](data-table.md)|Dataset resulting from the split|  
  
## See Also  
 [Sample and Split](data-transformation-sample-and-split.md)   
 [Split Data](split-data.md)   
 [Edit Metadata](edit-metadata.md)   
 [Group Data into Bins](group-data-into-bins.md)   
 [A-Z Module List](a-z-module-list.md)