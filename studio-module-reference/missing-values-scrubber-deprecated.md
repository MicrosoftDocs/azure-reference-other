---
title: "Missing Values Scrubber (deprecated) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 01/24/2018
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Missing Values Scrubber (deprecated)

*Specifies how to handle values that are missing from a dataset*

Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)

## Module overview

This article describes how to use the **Missing Values Scrubber** module in Azure Machine Learning Studio, to handle missing values. 

> [!WARNING]
> This module is provided only for backward compatibility with experiments created using the pre-release version of Azure Machine Learning Studio, and will soon be deprecated. We recommend that you modify your experiments to use [Clean Missing Data](clean-missing-data.md) instead.

The module takes a dataset as input, and returns a dataset in which missing values have been replaced using the method you specify.

## How to use Missing Values Scrubber

There are multiple ways to handle missing values. However, whichever method you choose, it applies to the entire set of columns you have selected. If you need to treat missing values differently in some columns, use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of data before applying **Missing Values Scrubber**.  

1. Add the **Missing Values Scrubber** module to your experiment in Studio.

    > [!WARNING]
    > This module has been deprecated. Use [Clean Missing Data](clean-missing-data.md) instead. 

2. Open the **Properties** pane of the module, and connect the dataset you want to check for missing values.

3. **For missing values**: Use this drop-down list to select a specific method to use in removing or replacing missing values.
  
    - **Replace with value**: Type a replacement value, if you want to replace all missing values with a single custom value.
    
        If the column contains integers, and you specify a floating-point value, the replacement value is rounded to the nearest integer.
  
3. **Columns with all MV (missing values)**: Use this option to indicate whether you want to keep or remove empty columns: that is, columns with nothing but missing values.

4. **MV (missing values) indicator column**: Select this option to generate an indicator column that lags the presence of missing values.  

5. Choose one of the following options for creating a new substitute value:

    - **Replace using MICE**: Replaces missing values by using "Multiple Imputation by Chained Equations" (MICE), a method broadly used in the statistics literature since work by Donald Rubin in the 1970s. 
    
      This method initializes the missing entries with a default value. Then it updates each column by using an appropriate regression or classification algorithm. These updates are repeated a number of times, as specified by the Number of Iterations parameter.

    - **Replace with value**: For every column with a data type of Integer, Double, Boolean, or Date, replaces the missing value with a value you specify. In date columns, you can provide a specific date in one of the supported formats, or you can enter the number of 100-nanosecond ticks since 1/1/0001 12:00 AM.

    - **Replace with mean**:  For every column with a data type of Integer, Double, or Boolean, the mean of the column replaces the missing value.

    - **Replace with median**: For every column with a data type of Integer or Double, the column median replaces the missing value.
  
    - **Replace with mode**: For every column with a data type of Integer, Double, Boolean, or Categorical, replaces the missing value with the column mode.

    - **Remove row**: Removes all rows in the dataset that have at least one missing value. This is useful if the missing value can be considered as missing at random.

    - **Do nothing**: Leave the missing values in place.

    - **Replace using probabilistic PCA**: Replaces the missing values by using a statistical model.
    
      Probabilistic PCA implements a variant of the model proposed in the Journal of the Royal Statistical Society, Series B 21(3), 611–622 by Tipping and  Bishop. In this method, a linear model analyzes the correlations between the columns and estimates a low-dimensional approximation of the data, from which the full data is reconstructed. The underlying dimensionality reduction is a probabilistic form of Principal Component Analysis (PCA).

      Compared to other options (such as MICE), this option has the advantage of not requiring the application of predictors for each column. Instead, it immediately approximates the covariance of the full dataset. It may therefore offer a better performance for datasets that have missing values in many columns.

      The key limitations of this method are:

      - It expands categorical columns into numerical indicators and computes a dense covariance matrix of the resulting data.
      - It is not optimized for sparse representations.  

      For these reasons, datasets with large numbers of columns and/or large categorical domains (tens of thousands) are not supported due to prohibitive space consumption.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset with missing values|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|For missing values|List (subset)|Handling policy|Custom substitution value|Choose the method for handling missing values.|  
|Co lumns with allvalues missing|Any|ColumnsWithAllValuesMissing|KeepColumns|Indicate if columns with all values missing should be preserved in the output.|  
|Missing values indicator column|Any|GenerateMissingValueIndicatorColumns|DoNotGenerate|Select this option to add a column to the   dataset that indicatesss wwwhetheeer that describes missing value handling should be added to the dataset.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Scrubbed dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type into the required by target method type.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0008](errors/error-0008.md)|An exception occurs if the parameter is not in range.|  
|[Error 0013](errors/error-0013.md)|An exception occurs if passed to module learner has invalid type.|  
|[Error 0018](errors/error-0018.md)|An exception occurs if the input dataset is not valid.|  
|[Error 0039](errors/error-0039.md)|An exception occurs if the operation failed.|  
|[Error 0010](errors/error-0010.md)|An exception occurs if input datasets have column names that should match, but they do not.|  
|[Error 0016](errors/error-0016.md)|An exception occurs if input datasets that are passed to the module should have compatible column types, but they do not.|  
|[Error 0067](errors/error-0067.md)|An exception occurs if a dataset has a different number of columns than expected.|  
|[Error 0017](errors/error-0017.md)|An exception occurs if one or more specified columns have a type that is unsupported by the current module.|  

## See also

 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Clean Missing Data](clean-missing-data.md)
