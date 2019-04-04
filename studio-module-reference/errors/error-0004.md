---
title: "Error 0004 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0004  
 Exception occurs if parameter is less than or equal to specific value.  
  
 You will receive this error in Azure Machine Learning if the parameter in the message is below a boundary value required for the module to process the data.  
  
**Resolution:**
 Revisit the module throwing the exception and modify the parameter to be greater than the specified value.  
  
|Exception Messages|  
|------------------------|  
|Parameter should be greater than boundary value.|  
|Parameter "{0}" value should be greater than {1}.|  
|Parameter "{0}" has value "{1}" which should be greater than {2}|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 
