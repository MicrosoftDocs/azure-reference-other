---
title: "Error 0003 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 06/14/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0003  
 Exception occurs if one or more of inputs are null or empty.  
  
 You will receive this error in Azure Machine Learning if any inputs or parameters to a module are null or empty.  This might occur, for example, when you did not type in any value for a parameter. It can also happen if you chose a dataset that has missing values, or an empty dataset.  
  
## Resolution  
 
+ Open the module that produced the exception and verify that all inputs have been specified. Ensure that all required inputs are specified. 
+ Make sure that data that is loaded from Azure storage is accessible, and that the account name or key has not changed.  
+ Check the input data for missing values, or nulls.
+ If using a query on a data source, verify that data is being returned in the format you expect. 
+ Check for typos or other changes in the specification of data.
  
|Exception Messages|  
|------------------------|  
|One or more of inputs are null or empty|  
|Input "{0}" is null or empty|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
