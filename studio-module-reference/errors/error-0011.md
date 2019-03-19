---
title: "Error 0011 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0011  
 Exception occurs if passed column set argument does not apply to any of dataset columns.  
  
 You will receive this error in Azure Machine Learning if the specified column selection does not match any of the columns in the given dataset.  
  
 You can also get this error if you haven't selected a column and at least one column is required for the module to work.  
  
## Resolution  
 Modify the column selection in the module so that it will apply to the columns in the dataset.  
  
 If the module requires that you select a specific column, such as a label column, verify that the right column is selected.  
  
 If inappropriate columns are selected, remove them and re-run the experiment.  
  
|Exception Messages|  
|------------------------|  
|Specified column set does not apply to any of dataset columns.|  
|Specified column set "{0}" does not apply to any of dataset columns.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
