---
title: "Error 0049 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0049  
 Exception occurs in the case when it is not possible to parse a file.  
  
 This error in Azure Machine Learning occurs when it is not possible to parse a file. You will receive this error if the file format selected in the [Import Data](../import-data.md) module does not match the actual format of the file, or if the file contains an unrecognizable character.  
  
## Resolution  
 Revisit the module and correct the file format selection if it does not match the format of the file. If possible, inspect the file to confirm that it does not contain any illegal characters.  
  
|Exception Messages|  
|------------------------|  
|Unable to parse a file.|  
|Error while parsing the file: {0}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
