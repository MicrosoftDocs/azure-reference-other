---
title: "ML Studio (classic): Compute Linear Correlation - Azure"
description: Learn how to use the Compute Linear Correlation module to compute Pearson correlation coefficients for each possible pair of variables in the input dataset.
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Compute Linear Correlation

*Calculates the linear correlation between column values in a dataset*  

Category: [Statistical Functions](statistical-functions.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Compute Linear Correlation](compute-linear-correlation.md) module in Azure Machine Learning Studio (classic), to compute a set of Pearson correlation coefficients for each possible pair of variables in the input dataset.  
  
The Pearson correlation coefficient, sometimes called Pearson’s R test, is a statistical value that measures the linear relationship between two variables. By examining the coefficient values, you can infer something about the strength of the relationship between the two variables, and whether they are positively correlated or negatively correlated.

## How to configure Linear Correlation

Before calculating the correlation coefficient, there are some prerequisites, such as cleaning your data and verifying that the relationship between the variables is appropriate for this module. You must also remove or impute missing values. 

The following restrictions apply when using this module:  
  
-   The [Compute Linear Correlation](compute-linear-correlation.md) module can process only numeric values. All other types of values, including missing values, non-numeric values, and categorical values, are treated as NaNs.      

-   Pearson’s correlation is calculated for all numeric columns in the dataset that are passed as input. Be sure to exclude any columns that are in appropriate for this analysis.

- [Compute Linear Correlation](compute-linear-correlation.md) cannot be used with data that has missing values.  

### Step 1: Determine linearity

If the columns you are testing are not expected to have some kind of linear relationship, there is no point in generating this coefficient. So it is a good idea to test the columns first, to see if they have the right kind of data and the right kind of distribution in general.

There are various ways that you can determine whether the relationship between the columns is roughly linear:

+ Create a scatter plot of the variables in Studio (classic), by using the **Visualize** option on the dataset. Click one of the numeric variable columns, expand **Visualizations**, and click **compare to**.  Select a different variable, and a scatter plot is automatically generated. If a different type of plot is generated, it means at least one column has a different (non-numeric) data type. 

+ Calculate a regression equation for the two variables.  There are many R packages that support this, which you can load and use in the [Execute R Script](execute-r-script.md) module. 

### Step 2: Clean data

You must remove or fill in missing values, remove or clip outliers, and ensure that the columns have the proper data type.

Be sure to check for placeholders and replace such value with other appropriate values before using this module. If NaNs were inserted for missing values when the dataset was loaded from the source, it could cause an error. Placeholder values such as <code>999</code> or <code>-1</code> can also cause bad results.  

To prepare your data, you can use these modules:

+ [Clean Missing Data](clean-missing-data.md)
+ [Clip Values](clip-values.md)
+ [Apply SQL Transformation](apply-sql-transformation.md)

You can adjust the data type of the columns by using [Edit Metadata](edit-metadata.md). Make sure that the columns you want to analyze are marked as feature columns.

### Step 3: Generate the coefficient

1. Add the [Compute Linear Correlation](compute-linear-correlation.md) module to your experiment. You can find this module in the [Statistical Functions](statistical-functions.md) category in Azure Machine Learning Studio (classic).

2. Add the dataset that you want to analyze.

3. We recommend that you add a [Select Columns in Dataset](select-columns-in-dataset.md) module between your dataset and the [Compute Linear Correlation](compute-linear-correlation.md) module, to remove unnecessary columns. Configure the [Select Columns in Dataset](select-columns-in-dataset.md) module to get only the two numeric columns for which you want to compute coefficients. 

    Otherwise, the [Compute Linear Correlation](compute-linear-correlation.md) module might generate many columns of NaNs.    

4. There are no parameters to set for this module. However, it will fail if the columns you pass as inputs do not meet the requirements.

5. Run the experiment.  

### Results for two columns 

Given two feature columns, the [Compute Linear Correlation](compute-linear-correlation.md) module returns the scalar Pearson product moment (sample) correlation coefficient.  The Pearson correlation coefficient (often denoted as r) ranges in value from +1 to -1.
  
- `+1` indicates a strong positive linear relationship

- `-1` indicates a strong negative linear correlation

- `0` denotes no linear relationship between the two variables.  

The interpretation of the coefficients depends very much on the problem you are modeling and the variables you are studying. Thus it is important to understand the context of the data when reporting and interpreting Pearson's correlation coefficient. 
  
- If you are certain the variables are unrelated and yet the Pearson’s correlation coefficient is strongly positive (r > .5 or so), you should investigate further.  
  
- If you use linear correlation on two variables that you know to be perfectly correlated, and the coefficient values are not what you expect, it might indicate a problem in the data.   

### Results for more than two columns

Given a matrix (that is, more than two feature columns), the [Compute Linear Correlation](compute-linear-correlation.md) module returns a set of Pearson product moment correlations between each pair of feature columns.  
 
Therefore, the result is an *n x n* table containing the coefficients for each combination of the *n* columns. If any columns do not meet the criteria, a NaN ("not a number" value) is returned. 

For example, assume you passed in the two numeric columns `wheel-base` and `curb-weight` plus one categorical column, `make` (from the Automobile price dataset). The result is a 3x3 table of coefficients for all possible combinations of the input columns:

| `make`|`wheel-base`|`curb-weight`|
|----|----|----|
|Nan|Nan|Nan|
|Nan|1|0.776386|
|Nan|0.776386|1|

In this table, the rows are understood to represent each of the variables,`make`, `wheel-base`, and `curb-weight`, in that order. 

+ The r value for the correlation of `wheel-base` to itself is 1.
+ The r value for the correlation of `wheel-base` to `curb-weight` is 0.776386.
+ All correlations involving the column `make` result in NaN, including the correlation with itself, because `make` is a string feature.
 
We recommend that you remove non-numeric columns, to avoid complex tables with many meaningless values.  

## Examples  

To see how this module is used in machine learning experiments, see the [Azure AI Gallery](https://gallery.azure.ai/):
  
-   [Data Processing and Analysis](https://go.microsoft.com/fwlink/?LinkId=525733): This sample demonstrates multiple techniques for modifying your data. [Compute Linear Correlation](compute-linear-correlation.md) is used to identify potential feature columns.  
  
##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

If the column that is passed as input contains scalars, the input arrays (*x* and *y*) are treated as vectors and the Pearson product moment correlation is computed as follows:  
  
 ![linear correlation formula](media/aml-linearcorrelation1.png "AML_LinearCorrelation1")  
  
 In this formula, each array contains *n* elements and the means of the *x* and *y* samples are µx and µy respectively.  
  
For a matrix, a matrix of data (*X*) is input, in which each column represents a vector of values. The data matrix should be *n*-by-*m*. The output is the *m*-by-*m* matrix, *R* as defined by  
  
 ![formula for linear correlation](media/aml-linearcorrelation2.png "AML_LinearCorrelation2")  
  
In this formula, μx represents the mean value of the column *x*i. The elements at I,j always equal 1, as they represent the correlation of a vector with itself.  
  
## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
## Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Correlations matrix|  
  
## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if the number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if the number of rows in some of the datasets passed to the module is too small.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Statistical Functions](statistical-functions.md)   
 [A-Z Module List](a-z-module-list.md)
