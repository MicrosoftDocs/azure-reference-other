---
title: "Split Data using Split Rows | Microsoft Docs"
ms.custom: ""
ms.date: 06/02/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0941c850-4833-44b5-83d1-5625564decf9
caps.latest.revision: 4
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Split Data using Split Rows

This topic describes how to use the **Split Rows** option in the [Split Data](split-data.md) module of Azure Machine Learning. Dividing datasets used for training and testing, either randomly or by some criteria, is an important task in many machine learning workflows.

The  **Split Rows** option is your best choice when you need to divide your data randomly into training and testing sets, or use stratified sampling. For example, you can specify a 70-30 split, or a 10-90 split with your target variable

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md). 

### Related Options

+ [Split data using regular expressions](split-data-using-regular-expression.md): Specify a condition to apply to a single text column, and divide the dataset based on that expression 

+ [Split data using relative expressions](split-data-using-relative-expression.md): Provide a value and operator to apply to a single numeric column, and split dataset based on that expression

+ [Split recommender datasets](split-data-using-recommender-split.md): Divide datasets that are used in recommendation models. The dataset should have three columns: items, users, and ratings 



##  <a name="HowSplitRows"></a> How to Use Split Rows


1.  Add the [Split Data](split-data.md) module to your experiment, and connect it as input to the dataset you want to split.  
  
2.  For **Splitting mode**, choose **Split rows**. 
3.  **Fraction of rows in the first output dataset**. Use this option to determine how many rows go into the first output. All other rows will go to the second output.

     The ratio should be typed as a decimal number between 0 and 1 to represent the percentage of rows sent to the first output dataset.  
     
     For example, if you type 0.75 as the value, the dataset would be split by using a 75:25 ratio, with 75% of the rows sent to the first output dataset, and 25% sent to the second output dataset.  
  
4. Select the **Randomized split** option is you want to randomize selection of data into the two groups. This is the preferred option when creating training and test datasets.  

5.  **Random Seed**:  Type a non-negative integer value to initialize the pseudorandom sequence of instances to be used. This default seed is used in all modules that generate random numbers. 

     Specifying a seed makes the results generally reproducible. If you need to repeat the results of a split operation, you should specify a **seed** for the random number generator. Otherwise the random seed is set by default to 0, which means the initial seed value is obtained from the system clock. As a result, the distribution of data might be slightly different each time you perform a split. 
     
     If you use the default value of 0, a seed value is generated based on the system clock.  

6. **Stratified split**: Set this option to True to ensure that the two output datasets contain a representative sample of the value in the *strata column* or *stratification key column*. You can then select which column has the values to stratify on.  
  
     With stratified sampling, the data is divided in such a way that a percentage of each target column value is put in each output dataset. This option is useful if the column you choose as the strata has categories that should be balanced. For example, you might want to balance by income, gender, etc.  
  
     To use stratified sampling, the strata column must contain nominal or categorical data. If the strata column you specify has continuous numeric data, an error message appears.  
  
     If your strata column has too many unique values, the column is not a good candidate for splitting over strata. 

4. Run the experiment, or right-click the module and select **Run selected**.


##  <a name="bkmk_SplitRowsExamples"></a> Examples  
 The following examples demonstrate how to perform simple splits using **Split Rows** mode:  
  
-   To split a dataset into two equal parts, just add the [Split Data](split-data.md) module after the dataset without no other changes. By default, the module splits the dataset in two equal parts. For data with an odd number of rows, the second output gets the remainder.  

-   Assume that you want to split a dataset into two parts, with a third of the data used for training and the remainder for testing or additional splits.  
  
     To do this, add a [Split Data](split-data.md) module, and set the **Fraction of rows in the first output** to 0.33. The second output contains the remaining two-thirds.  

##  <a name="Notes"></a> Technical Notes  
 
- This module requires a dataset that contains at least two rows as input.  
  
- If you use the option to specify the desired number of rows, the specified number must be a positive integer, and the number must be less than the total number of rows in the dataset.  
  
- All percentage values must be within the range 0 and 1.  
  
- If you specify a number or percentage that is a floating point number less than one, and you do not use the percent symbol (%), the number is interpreted as a proportional value.  
  
- If you use the option for a stratified split, the output datasets can be further divided by subgroups, by selecting a strata column.  

## See Also  
  
 [Split Data using Regular Expression](split-data-using-regular-expression.md)  
 [Split Data using Relative Expression](split-data-using-relative-expression.md)  
 [Split Data using Recommender Split](split-data-using-recommender-split.md)  
 [A-Z Module List](a-z-module-list.md)  