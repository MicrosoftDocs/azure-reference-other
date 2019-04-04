---
title: "Error 0042 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 06/14/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0042  
 Exception occurs when it is not possible to convert column to another type.  
  
 This error in Azure Machine Learning occurs when it is not possible to convert column to the specified type.  You will receive this error if a module requires a particular data type, such as datetime, text, a floating point number, or integer, but it is not possible to convert an existing column to the required type.  
 
For example, you might select a column and try to convert it to a numeric data type for use in a math operation, and get this error if the column contained invalid data. 

Another reason you might get this error if you try to use a column containing floating point numbers or many unique values as a categorical column. 
  
**Resolution :**

+ Open the help page for the module that generated the error, and verify the data type requirements.
+ Review the data types of the columns in the input dataset.
+ Inspect data originating in so-called schema-less data sources.
+ Check the dataset for missing values or special characters that might block conversion to the desired data type. 
    + Numeric data types should be consistent: for example, check for floating point numbers in a column of integers.
    + Look for text strings or NA values in a number column. 
    + Boolean values can be converted to an appropriate representation depending on the required data type.
    + Examine text columns for non Unicode characters, tab characters, or control characters
    + Datetime data should be consistent to avoid modeling errors, but cleanup can be complex owing to the many formats. Consider using the [Execute R Script](../execute-r-script.md) or [Execute Python Script](../execute-python-script.md) modules to perform cleanup.  
+ If necessary, modify the values in the input dataset so that the column can be converted successfully. Modification might include binning, truncation or rounding operations, elimination of outliers, or imputation of missing values. See the following articles for some common data transformation scenarios in machine learning:
    + [Clip Values](../clip-values.md) 
    + [Clean Missing Data](../clean-missing-data.md)
    + [Normalize Data](../normalize-data.md)
    + [Group Data Into Bins](../group-data-into-bins.md)
  
 
> [!TIP]
> Resolution unclear, or not applicable to your case? You are welcome to send feedback on this article and provide information about the scenario, including the module and the data type of the column. We will use this information to provide more detailed troubleshooting steps in future.  
  
|Exception Messages|  
|------------------------|  
|Not allowed conversion.|  
|Could not convert column of type {0} to column of type {1}.|  
|Could not convert column "{2}" of type {0} to column of type {1}.|  
|Could not convert column "{2}" of type {0} to column "{3}" of type {1}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
