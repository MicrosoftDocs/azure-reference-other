---
title: "Replace Discrete Values | Microsoft Docs"
ms.custom: ""
ms.date: 03/02/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0de80e22-f74e-4e51-a080-e73806a6e00d
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Replace Discrete Values
*Replaces discrete values from one column with numeric values based on another column*  
  
 Category: [Statistical Functions](statistical-functions.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Replace Discrete Values** module to generate a probability score that can be used to represent a discrete value. This can be useful for understanding the information value of the discrete values.  
  
 You select a column that contains the discrete (or categorical) value, and then select another column to use for reference. Depending on whether the second column is categorical or non-categorical, the module computes one of the following values:  
  
-   The **conditional probability** for the second column given the values in the first column.  
  
-   The **mean** and **standard deviation** for each group of values in the first column.  
  
 The module outputs both a transformed dataset, and a function that you can save as a transform and apply to other datasets.  
  
## How to Configure Replace Discrete Values  

The module allows you to select more than one pair of columns to analyze. However, in practice, if you choose multiple columns, they are matched by an internal heuristic, not by order of selection. 

Therefore, to ensure that you get the right replacement values, we recommend that you select a single pair of columns each time, one for **Discrete columns** and one for **Replacement columns**. If you need to analyze multiple columns, use separate instances of **Replace Discrete Values**.  
  
1.  Add the **Replace Discrete Values** module to your experiment. You can find this module in the [Statistical Functions](statistical-functions.md) group in the **experiment items** list in Azure Machine Learning Studio.

2. Connect a dataset containing at least one column of categorical data.  
  
2.  For the **Discrete columns** option, click **Launch column selector** to choose one or more columns that contain discrete (or categorical) values. Any discrete columns that you select at this time must be categorical. If you get an error, use the [Edit Metadata](edit-metadata.md) module to change the column type.  

    > [!TIP] 
    > We recommend working with only one column at a time.
  
3.  For the **Replacement columns** option, click **Launch column selector** to choose the column that contains the values to use in computing a replacement score.  
  
     The number of replacement columns must be equal to the number of discrete columns from the previous step, and they cannot be the same columns.  
   
4.  Run the experiment, or select just this module and click **Run selected**.  
  
    > [!WARNING]
    >  You cannot choose the statistical function to apply. The module calculates the appropriate measure, based on the data type of the column selected for **Replacement column**.  
  
### Results

Depending on whether the second column is categorical or non-categorical, the module computes one of the following values:  
  
-   If the second column is a categorical value, it computes the **conditional probability** for the second column given the values in the first column.  
  
    For example, if you choose **occupation** (from the Census dataset) as the discrete column and choose **gender** as the replacement column. The module outputs:  
  
    `P(gender | occupation)`  
  
-   If the second column non-categorical values that can be converted to numbers (such as numeric or Boolean values **not** marked as categorical), it calculates the **mean** and **standard deviation** for each group of values in the first column.  
  
    For example, if you select **occupation** as the **Discrete column** and the numeric column **hours-per-week** as the **Replacement column**, the new value columns would have these headings:  
  
    `Mean(hours-per-week | occupation)`  
  
    `Std-Dev(hours-per-week | occupation)`  

The module also outputs a transformed dataset in which the columns you selected as the **Replacement columns** have been replaced with the computed scores. The headings of the new columns indicate the source columns and the operation.  
  
> [!TIP]
>  Although the original column values for the replacement columns are not included in the transformed dataset, the actual data columns in your dataset are not directly affected by the transformation; the new score columns are just added as metadata. You can always get the column values by using add columns and connecting the source dataset.  
  
## Examples  
 The usage of **Replace Discrete Values** can be illustrated by some simple examples.  
  
### Example 1 - Replace a categorical value with a probability score  
 The following table contains a categorical column X, and a column Y with True/False values that are treated as categorical values. When you use **Replace Discrete Values**, it calculates a conditional probability score for the probability of Y given X, as shown in the third column.  
  
| X | Y | P(Y&#124;X) |  
|-------|-------|-------------------|  
|Blue|0|<code>P(Y=0&#124;X=Blue) = 0.5</code>|  
|Blue|1|<code>P(Y=1&#124;X =Blue) = 0.5</code>|  
|Green|0|<code>P(Y=0&#124;X=Green) = 2/3</code>|  
|Green|0|<code>P(Y=0&#124;X=Green) = 2/3</code>|  
|Green|1|<code>P(Y=1&#124;X=Green) = 1/3</code>|  
|Red|0|<code>P(Y=0&#124;X=Red) = .75</code>|  
|Red|0|<code>P(Y=0&#124;X=Red) = .75</code>|  
|Red|1|<code>P(Y=1&#124;X=Red) = .25</code>|  
|Red|0|<code>P(Y=0&#124;X=Red) = .75</code>|  
  
### Example 2 - Calculate mean and standard deviation based on a noncategorical column  
 If the second column is numerical, **Replace Discrete Values** calculates Mean(Y&#124;X) and Std-Dev(Y&#124;X) instead of the conditional probability score. The following example is based on the sample Auto Prices dataset, simplified as follows:  
  
-   A small subset of columns was selected.  
  
-   Only the top 30 rows were extracted, by using the **Head** option of  the [Partition and Sample](partition-and-sample.md) module.  
  
-   The **Replace Discrete Values** module was used to compute the **mean** and **standard deviation** for vehicle curb weight. given the categorical column, num-of-doors.  
  
 The following table illustrates the results:  
  
|Body|Num-of-doors|Curb-weight|Mean(curb-weight&#124;num-of-doors)|Std-Dev(curb-weight&#124;num-of-doors)|  
|----------|--------------------|------------------|----------------------------------------------|--------------------------------------------------|  
|std|two|2548|2429.785714|507.45699|  
|std|four|2337|2625.6|493.409877|  
|std|two|2507|2429.785714|507.45699|  
|turbo|four|3086|2625.6 5|493.409877|  
|std|four|1989|2625.6|493.409877|  
|turbo||2191|||  
|std|four|2535|2625.6|493.409877|  
  
 You can verify the mean for each group of values by using the `AVERAGEIF` function in Excel.  
  
### Example 3 - Handling of missing values  
 This example demonstrates how missing values (nulls) propagate to the results when  conditional probability scores are calculated.  
  
-   If the discrete value column and the calculation lookup column contains any missing values, the missing values are propagated to the new column.  
  
-   If the discrete value column contains only missing values, the module cannot process the column and an error message appears.  
  
|X|Y|P(Y&#124;X)|  
|-------|-------|-------------------|  
|1|True|<code>P(Y=true&#124;X=1) = 1/2</code>|  
|1|False|<code>P(Y=false&#124;X=1) = 1/2</code>|  
|2|True|<code>P(Y=true&#124;X=2) = 1/3</code>|  
|2|False|<code>P(Y=false&#124;X=2) = 1/3</code>|  
|2|Null|<code>P(Y=null&#124;X=2) = null</code>|  
  
##  <a name="Notes"></a> Technical Notes  
  
-   You must ensure that any discrete columns you want to replace are categorical, or the module will return an error.  
  
     You can do this by using [Edit Metadata](edit-metadata.md).  
  
-   If the second column contains Boolean values, the True-False values are processed as numeric with FALSE and TRUE equivalent to 0 and 1 respectively.  
  
-   The formula for the standard deviation column calculates the population standard deviation. Therefore, N  is used in the denominator instead of (N - 1).  
  
-   If the second column contains noncategorical data (numeric or Boolean values), the module computes the mean and standard deviation of Y for the given value of X. 

    That is, for each row in the dataset indexed by *i*:  
  
     `Mean(Y│X)i= Mean(Y│X = Xi)`  
  
     `StdDev(Y│X)i = StdDev(Y│X = Xi)`  
  
-   If the second column contains categorical data or values that are neither numeric nor Boolean, the module computes the conditional probability of Y for the given value of X.  
  
-   Any Boolean values in the second column are processed as numeric data with FALSE and TRUE equivalent to 0 and 1 respectively.  
  
-   If there is a class in the discrete column, such that a row with a missing value is present in the second column, the sum of conditional probabilities within the class is less than one.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Discrete columns|Any|ColumnSelection||Selects the columns that contain discrete values|  
|Replacement columns|Any|ColumnSelection||Selects the columns that contain the data to use in place of the discrete values|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Supplemented dataset|[Data Table](data-table.md)|Dataset with replaced data|  
|Transform function|[ITransform interface](itransform-interface.md)|Definition of the transform function, which can be applied to other datasets|  
  
##  <a name="exceptions"></a> Exceptions  
 For a complete list of error messages, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](error-0001.md)|Exception occurs if one or more specified columns of the data set couldn't be found.|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0020](error-0020.md)|Exception occurs if the number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](error-0021.md)|Exception occurs if the number of rows in some of the datasets passed to the module is too small.|  
|[Error 0017](error-0017.md)|Exception occurs if one or more specified columns have a type that is unsupported by the current module.|  
|[Error 0026](error-0026.md)|Exception occurs when columns with the same name are not allowed.|  
|[Error 0022](error-0022.md)|Exception occurs if the number of selected columns in the input dataset does not equal the expected number.|  
  
## See Also  
 [Statistical Functions](statistical-functions.md)   
 [A-Z Module List](a-z-module-list.md)