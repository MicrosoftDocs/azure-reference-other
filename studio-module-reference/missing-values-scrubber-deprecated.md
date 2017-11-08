---
title: "Missing Values Scrubber (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 07/01/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ba668ff5-8720-4676-a0a5-ff14f5133da7
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Missing Values Scrubber (deprecated)
*Specifies how to handle values that are missing from a dataset*  
  
 Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)  
  
##  <a name="Remarks"></a> Module Overview  
 The **Missing Values Scrubber** module provides some basic methods for handling missing values. It expects a dataset as input, and it returns a dataset with missing values that are substituted by a method that you select.  
  
> [!WARNING]
>  This module is provided for backward compatibility with experiments created using the pre-release version of Azure Machine Learning Studio, and will soon be deprecated. We recommend that you modify your experiments to use [Clean Missing Data](clean-missing-data.md) instead.  
  
## How to Use Missing Values Scrubber  
 There are multiple ways to handle missing values. However, whichever method you choose, it applies to the entire set of columns you have selected. If you need to treat missing values differently in some columns, use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of data before applying **Missing Values Scrubber**.  
  
1.  ***For missing values...***  
  
     Use this drop-down list to select which method to use to handle missing values.  
  
2.  ***Replace with value...***  
  
     Type a replacement value. This is only needed if you choose to substitute missing values with a custom value. If you specify a floating-point value to replace missing values in a column of integers, the value substituted for the missing value will be this value converted to the nearest integer.  
  
3.  ***Columns with all MV (missing values)...***  
  
     Choose whether to keep or remove columns with all values missing.  
  
4.  ***MV (missing values) indicator column***  
  
     Choose whether to generate missing value indicator columns.  
  
### Options  
 You can select from the following substitution methods to replace missing values:  
  
 ***Replace using MICE***  
 Replaces missing values by using "Multiple Imputation by Chained Equations" (MICE), a method broadly used in the statistics literature since work by Donald Rubin in the 1970s. This method initializes the missing entries with a default value. Then it updates each column by using an appropriate regression or classification algorithm. These updates are repeated a number of times, as specified by the Number of Iterations parameter.  
  
 ***Replace with value***  
 Assigns the replacement value to any missing value in every column with a data type of Integer, Double, Boolean, or Date. For date columns, the replacement value can also be entered as the number of 100-nanosecond ticks since 1/1/0001 12:00 AM.  
  
 ***Replace with mean***  
 Assigns the replacement value to any missing value in every column with a data type of Integer, Double, or Boolean  
  
 ***Replace with median***  
 Assigns the median of a column to any missing value in every column with a data type of Integer or Double.  
  
 ***Replace with mode***  
 Assigns the mode of a column to any missing value in every    column with a data type of Integer, Double, Boolean, or Categorical.  
  
 ***Remove row***  
 Removes all rows in the dataset with one or more missing values. This is useful if the missing value can be considered as missing at random.  
  
 ***Do nothing***  
 Leave the missing value.  
  
 ***Replace using probabilistic PCA***  
 Replaces the missing values by using a linear model that analyzes the correlations between the columns and estimates a low-dimensional approximation of the data, from which the full data is reconstructed. The underlying dimensionality reduction is a probabilistic form of Principal Component Analysis (PCA). It implements a variant of the model proposed in the Journal of the Royal Statistical Society, Series B 21(3), 611–622 by Tipping and  Bishop.  
  
 Compared to other options (such as MICE), this option has the advantage of not requiring the application of predictors for each column. Instead, it immediately approximates the covariance of the full dataset. It may therefore offer a better performance for datasets that have missing values in many columns.  
  
 The key limitations of this method are:  
  
-   It expands categorical columns into numerical indicators and computes a dense covariance matrix of the resulting data.  
  
-   It is not optimized for sparse representations.  
  
 For these reasons, datasets with large numbers of columns and/or large categorical domains (tens of thousands) are not supported due to prohibitive space consumption.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset with missing values|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|For missing values|List (subset)|Handling policy|Custom substitution value|Choose the method for handling missing values.|  
|Co lumns with allvalues missing|Any|ColumnsWithAllValuesMissing|KeepColumns|Indicate if columns with all values missing should be preserved in the output.|  
|Missing values indicator column|Any|GenerateMissingValueIndicatorColumns|DoNotGenerate|Select this option to add a column to the   dataset that indicatesss wwwhetheeer that describes missing value handling should be added to the dataset.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Scrubbed dataset|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0002](error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type into the required by target method type.|  
|[Error 0003](error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0008](error-0008.md)|An exception occurs if the parameter is not in range.|  
|[Error 0013](error-0013.md)|An exception occurs if passed to module learner has invalid type.|  
|[Error 0018](error-0018.md)|An exception occurs if the input dataset is not valid.|  
|[Error 0039](error-0039.md)|An exception occurs if the operation failed.|  
|[Error 0010](error-0010.md)|An exception occurs if input datasets have column names that should match, but they do not.|  
|[Error 0016](error-0016.md)|An exception occurs if input datasets that are passed to the module should have compatible column types, but they do not.|  
|[Error 0067](error-0067.md)|An exception occurs if a dataset has a different number of columns than expected.|  
|[Error 0017](error-0017.md)|An exception occurs if one or more specified columns have a type that is unsupported by the current module.|  
  
## See Also  
 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Clean Missing Data](clean-missing-data.md)