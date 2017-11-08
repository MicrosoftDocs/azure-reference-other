---
title: "Error 0007 | Microsoft Docs"
ms.custom: ""
ms.date: 06/14/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0007-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0007
**Error 0007**  
  
 Exception occurs if parameter is greater than a specific value.  
  
 You will receive this error in Azure Machine Learning if, in the properties for the module, you specified a value that is greater than is allowed. For example, you might specify a data that is outside the range of supported dates, or you might indicate that 5 columns be used when only 3 columns are available. 
 
 You might also see this error if you are specifying two sets of data that need to match in some way. For example, if you are renaming columns, and specify the columns by index, the number of names you supply must match the number of column indices. Another example might be a math operation that uses two columns, where the columns must have the same number of rows. 
  
## Resolution  
 
 + Open the module in question and review any numeric property settings.
 + Ensure that any parameter values fall within the supported range of values for that property.
 + If the module takes multiple inputs, ensure that inputs are of the same size.
 + If the modules has multiple properties that can be set, ensure that related properties have appropriate values. For example, when using [Group Data into Bins](group-data-into-bins.md), if you use the option to specify custom bin edges, the number of bins must match the number of values you provide as bin boundaries.
 + Check whether the dataset or data source has changed. Sometimes a value that worked with a previous version of the data will fail after the number of columns, the column data types, or the size of the data has changed.  
  
|Exception Messages|  
|------------------------|  
|Parameters mismatch. One of the parameters should be less than or equal to another.|  
|Parameter "{0}" value should be less than or equal to parameter "{1}" value.|  
|Parameter "{0}" has value "{1}" which should be less than or equal to {2}.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)